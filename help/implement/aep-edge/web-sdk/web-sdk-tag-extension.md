---
title: Inviare dati ad Adobe Analytics tramite l’estensione tag Web SDK
description: Inizia con un’implementazione pulita di Raccolta dati di Adobe Experience Platform per inviare dati ad Adobe Analytics utilizzando XDM e il gruppo di campi Adobe Analytics ExperienceEvent.
exl-id: 235b3d68-92dd-4ca4-8889-1e1f2d83f47e
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 3%

---

# Inviare dati ad Adobe Analytics tramite l’estensione tag Web SDK

Questo percorso di implementazione prevede una nuova installazione di Web SDK utilizzando i tag in Raccolta dati di Adobe Experience Platform. Altri percorsi di implementazione sono trattati in pagine separate:

* [Libreria Web SDK JavaScript](web-sdk-javascript-library.md): una nuova installazione di Web SDK utilizzando la libreria Web SDK JavaScript (`alloy.js`). Simile all’approccio di estensione tag di Web SDK (questa pagina), con la differenza che puoi gestire autonomamente l’implementazione anziché utilizzare l’interfaccia utente dei tag. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.
* [Estensione Analytics per estensione Web SDK](analytics-extension-to-web-sdk.md): adotta un approccio semplice e metodico per passare dall&#39;estensione tag Adobe Analytics all&#39;estensione tag Web SDK. Questo approccio elimina la necessità di utilizzare XDM fino a quando l’organizzazione non è pronta a utilizzare i servizi Adobe Experience Platform, come Customer Journey Analytics. Utilizzare l&#39;oggetto `data` invece dell&#39;oggetto `xdm` per inviare dati ad Adobe.
* [Libreria JavaScript da AppMeasurement a Web SDK](appmeasurement-to-web-sdk.md): approccio semplice e sistematico per la migrazione al Web SDK, ma senza l&#39;utilizzo di tag. È invece possibile rimuovere manualmente la raccolta dati di Adobe Analytics (`AppMeasurement.js`) e sostituirla con la raccolta JavaScript di Web SDK (`alloy.js`).

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo dell’estensione Web SDK per inviare dati ad Adobe Analytics presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Approccio più diretto**: questo percorso di implementazione è il più semplice e in genere il percorso consigliato per le nuove implementazioni di Web SDK. Se non hai un’implementazione Adobe Analytics corrente da preoccupare, compila i campi XDM di Web SDK applicabili.</li><li>**Schema predefinito**: se per la tua organizzazione non è necessario un tuo schema, puoi semplicemente utilizzare lo schema orientato verso Adobe Analytics. Questo concetto si applica anche quando ci si sposta verso Customer Journey Analytics; il concetto di prop ed eVar non si applica a Customer Journey Analytics, ma puoi continuare a utilizzare prop ed eVar come semplici dimensioni personalizzate.</li><li>**Gestione dei tag senza l&#39;intervento degli sviluppatori**: i tag consentono di gestire l&#39;implementazione senza richiedere agli sviluppatori di apportare modifiche al codice nell&#39;implementazione. I tuoi sviluppatori installano lo script del caricatore di tag e hai il controllo completo sulla modalità di raccolta dei dati.</li></ul> | <ul><li>**Bloccato per l&#39;utilizzo di uno schema specifico**: quando l&#39;organizzazione si sposta su Customer Journey Analytics, è necessario scegliere di continuare a utilizzare lo schema Adobe Analytics o di eseguire la migrazione allo schema della propria organizzazione (che sarebbe un set di dati separato). Se la tua organizzazione desidera evitare sia lo schema Adobe Analytics che la migrazione a un set di dati separato durante il trasferimento a Customer Journey Analytics, Adobe consiglia uno dei due metodi seguenti:<ul><li>Utilizzare l&#39;oggetto `data`: l&#39;oggetto `data` consente di inviare dati ad Adobe Analytics senza essere conforme a uno schema XDM. Una volta creato lo schema dell&#39;organizzazione, è possibile utilizzare la mappatura dello stream di dati per mappare i campi oggetto `data` su XDM. Sia l&#39;estensione [Analytics all&#39;estensione Web SDK](analytics-extension-to-web-sdk.md) che la [libreria AppMeasurement a Web SDK JavaScript](appmeasurement-to-web-sdk.md) utilizzano questo oggetto `data`.</li><li>Ignora completamente Adobe Analytics: se implementi il Web SDK, puoi inviare tali dati a un set di dati in Adobe Experience Platform per l’utilizzo in Customer Journey Analytics. Puoi utilizzare qualsiasi schema desiderato; Adobe Analytics non è coinvolto in questo flusso di lavoro e pertanto non richiede il gruppo di campi Adobe Analytics ExperienceEvent. Questo metodo si assume la minore quantità di debito tecnico, ma lascia anche completamente fuori dal quadro generale Adobe Analytics.</li></ul></ul> |

>[!IMPORTANT]
>
>Questo metodo di implementazione richiede l’utilizzo di uno schema configurato per Adobe Analytics. Se la tua organizzazione prevede di utilizzare lo schema personalizzato con Customer Journey Analytics in futuro, l’utilizzo dello schema Adobe Analytics può creare confusione per gli amministratori di dati o gli architetti. Esistono diverse opzioni per attenuare questo ostacolo:
>
>* Puoi utilizzare lo schema Adobe Analytics in CJA. CJA non ha un concetto di proprietà o eVar; vengono trattate come qualsiasi altro campo schema. Inoltre, l’utilizzo dello schema Adobe Analytics in CJA può rendere più difficile l’utilizzo di altri servizi di piattaforma, come Adobe Journey Optimizer o Real-Time Customer Data Platform.
>* Puoi utilizzare l’oggetto dati, in modo simile a un flusso di lavoro di migrazione. L’utilizzo dell’oggetto dati richiede la mappatura di ogni campo dell’oggetto dati su un campo dello schema XDM.
>* Puoi saltare completamente l’implementazione di Adobe Analytics e inviare dati a Adobe Experience Platform utilizzando il tuo schema. Si tratta di un approccio ideale a lungo termine che consente all’organizzazione di iniziare a utilizzare Customer Journey Analytics.

## Passaggi necessari per implementare l’estensione tag Web SDK

Panoramica ad alto livello dei compiti di implementazione:

![Come implementare Adobe Analytics utilizzando il flusso di lavoro dell&#39;estensione Web SDK, come descritto in questa sezione.](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Attività</b></th><th style="width:35%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td>1</td>
<td>Assicurati di aver <b>definito una suite di rapporti</b>.</td>
<td><a href="/help/admin/tools/manage-rs/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Imposta schemi</b>. Per standardizzare la raccolta dati da utilizzare nelle applicazioni che sfruttano Adobe Experience Platform, Adobe ha creato lo standard aperto e pubblicamente documentato Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=it">Panoramica dell’interfaccia utente degli schemi</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Crea un livello dati</b> per gestire il tracciamento dei dati sul tuo sito Web.</td>
<td><a href="../../prepare/data-layer.md">Creare un livello dati</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Configura uno stream di dati</b>. Un flusso di dati rappresenta la configurazione lato server durante l’implementazione di Adobe Experience Platform Web SDK.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=it">Configurare uno stream di dati<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>Aggiungi un servizio Adobe Analytics</b> allo stream di dati. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics e a quali suite di rapporti in particolare.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=it#analytics">Aggiungere il servizio Adobe Analytics a uno stream di dati</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Crea una proprietà tag</b>. Le proprietà sono contenitori generali utilizzati per fare riferimento ai dati di gestione dei tag.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=it#for-web">Creare o configurare una proprietà tag per il Web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Installa e configura l'estensione Web SDK</b> nella proprietà tag. Configura l’estensione Web SDK per inviare i dati allo stream di dati configurato nel passaggio 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=it">Panoramica dell’estensione Adobe Experience Platform Web SDK</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Iterare, convalidare e pubblicare</b> in produzione. Incorpora il codice per includere la proprietà tag nelle pagine del sito web. Quindi utilizza elementi dati, regole e così via, per personalizzare l’implementazione.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=it#embed-code">Codice di incorporamento</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=it">Panoramica sulla pubblicazione</a></td>
</tr>

</table>
