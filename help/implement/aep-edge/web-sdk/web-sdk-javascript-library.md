---
title: Inviare dati ad Adobe Analytics utilizzando la libreria JavaScript dell’SDK per web
description: Inizia con un’implementazione pulita di Web SDK per inviare dati ad Adobe Analytics utilizzando la libreria JavaScript.
exl-id: 593b63ac-e411-4f88-af7e-78f026269ec0
source-git-commit: 316ca1074de36db0d7c9545691e7c6d72a2ed2c4
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 2%

---

# Inviare dati ad Adobe Analytics utilizzando la libreria JavaScript dell’SDK per web

Questo percorso di implementazione comporta una nuova installazione di Web SDK utilizzando la libreria JavaScript di Web SDK. Altri percorsi di implementazione sono trattati in pagine separate:

* [Estensione tag Web SDK](web-sdk-tag-extension.md): nuova installazione di Web SDK tramite l’estensione tag Web SDK. Simile all’approccio per la libreria JavaScript dell’SDK web (questa pagina), tranne per il fatto che gestisci l’implementazione utilizzando i tag in Raccolta dati di Adobe Experience Platform. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.
* [Estensione Analytics per estensione Web SDK](analytics-extension-to-web-sdk.md): adotta un approccio fluido e sistematico per passare dall’estensione tag Adobe Analytics all’estensione tag Web SDK. Questo approccio elimina la necessità di utilizzare XDM fino a quando l’organizzazione non è pronta a utilizzare i servizi Adobe Experience Platform, come il Customer Journey Analytics. Utilizza il `data` oggetto invece del `xdm` oggetto per inviare dati ad Adobe.
* [AppMeasurement della libreria JavaScript di Web SDK](appmeasurement-to-web-sdk.md): approccio fluido e metodico per la migrazione all’SDK web, con la differenza che non utilizza i tag. È invece possibile rimuovere manualmente la libreria di raccolta dati di Adobe Analytics (`AppMeasurement.js`) e sostituirla con la libreria JavaScript di Web SDK (`alloy.js`).

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo della libreria JavaScript dell’SDK web per inviare dati ad Adobe Analytics presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Approccio diretto**: questo percorso di implementazione è più semplice degli approcci che spostano le implementazioni Adobe Analytics esistenti. Se non hai un’implementazione Adobe Analytics corrente da preoccupare, compila i campi XDM dell’SDK per web applicabili.</li><li>**Schema predefinito**: se per la tua organizzazione non è necessario un tuo schema, puoi semplicemente utilizzare lo schema orientato verso Adobe Analytics. Questo concetto si applica anche quando ci si sposta verso il Customer Journey Analytics; il concetto di prop e eVar non si applica al Customer Journey Analytics, ma puoi continuare a utilizzare prop ed eVar come semplici dimensioni personalizzate.</li></ul> | <ul><li>**Le modifiche all’implementazione richiedono l’intervento degli sviluppatori**: se desideri apportare modifiche all’implementazione dell’SDK web, devi collaborare con il team di sviluppo per modificare il codice sul sito. L&#39;approccio che utilizza [Estensione tag Web SDK](web-sdk-tag-extension.md) evita questo svantaggio.</li><li>**Bloccato in utilizzando uno schema specifico**: quando l’organizzazione passa al Customer Journey Analytics, devi scegliere di continuare a utilizzare lo schema Adobe Analytics o di eseguire la migrazione allo schema della tua organizzazione (che sarebbe un set di dati separato). Se la tua organizzazione desidera evitare sia lo schema Adobe Analytics che la migrazione a un set di dati separato durante il passaggio al Customer Journey Analytics, Adobe consiglia uno dei due metodi seguenti:</li><ul><li>Utilizza il `data` oggetto: `data` object consente di inviare dati ad Adobe Analytics senza essere conforme a uno schema XDM. Una volta creato lo schema dell’organizzazione, puoi utilizzare la mappatura dello stream di dati per eseguire la mappatura `data` campi oggetto in XDM. Entrambe [Estensione Analytics per estensione Web SDK](analytics-extension-to-web-sdk.md) e [AppMeasurement della libreria JavaScript di Web SDK](appmeasurement-to-web-sdk.md) utilizza questo `data` oggetto.</li><li>Ignora completamente Adobe Analytics: se implementi l’SDK web, puoi inviare tali dati a un set di dati in Adobe Experience Platform per l’utilizzo in Customer Journey Analytics. Puoi utilizzare qualsiasi schema desiderato; Adobe Analytics non è coinvolto in questo flusso di lavoro e pertanto non richiede il gruppo di campi Adobe Analytics ExperienceEvent. Questo metodo si assume la minore quantità di debito tecnico, ma lascia anche completamente fuori dal quadro generale Adobe Analytics.</li></ul></ul> |

>[!IMPORTANT]
>
>Questo metodo di implementazione richiede l’utilizzo di uno schema configurato per Adobe Analytics. Se la tua organizzazione prevede di utilizzare il tuo schema con Customer Journey Analytics in futuro, l’utilizzo dello schema Adobe Analytics può creare confusione per gli amministratori di dati o gli architetti. Esistono diverse opzioni per attenuare questo ostacolo:
>
>* Puoi utilizzare lo schema Adobe Analytics in CJA. CJA non ha un concetto di proprietà o eVar; vengono trattate come qualsiasi altro campo schema. Inoltre, l’utilizzo dello schema Adobe Analytics in CJA può rendere più difficile l’utilizzo di altri servizi della piattaforma, come Adobe Journey Optimizer o Real-time Customer Data Platform.
>* Puoi utilizzare l’oggetto dati, in modo simile a un flusso di lavoro di migrazione. L’utilizzo dell’oggetto dati richiede la mappatura di ogni campo dell’oggetto dati su un campo dello schema XDM.
>* Puoi saltare completamente l’implementazione di Adobe Analytics e inviare dati a Adobe Experience Platform utilizzando il tuo schema. Questo approccio è ideale a lungo termine e consente all’organizzazione di iniziare a utilizzare il Customer Journey Analytics.

## Passaggi necessari per implementare la libreria JavaScript dell’SDK Web

Panoramica ad alto livello dei compiti di implementazione:

![Come implementare Adobe Analytics utilizzando il flusso di lavoro Web SDK, come descritto in questa sezione.](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Attività</b></th><th style="width:35%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td>1</td>
<td>Assicurati di avere <b>definizione di una suite di rapporti</b>.</td>
<td><a href="/help/admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurare gli schemi</b>. Per standardizzare la raccolta dati da utilizzare nelle applicazioni che sfruttano Adobe Experience Platform, Adobe ha creato lo standard aperto e pubblicamente documentato Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=it">Panoramica dell’interfaccia utente degli schemi</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Creare un livello di dati</b> per gestire il tracciamento dei dati sul sito web.</td>
<td><a href="../../prepare/data-layer.md">Creare un livello di dati</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>Installare la versione standalone predefinita</b>. Puoi fare riferimento alla libreria (<code>alloy.js</code>) sulla rete CDN direttamente sulla pagina oppure scaricala e ospitala sulla tua infrastruttura. In alternativa, è possibile utilizzare il pacchetto NPM.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/library.html">Installazione della versione standalone pregenerata</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/npm.html">Utilizzo del pacchetto NPM</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configurare uno stream di dati</b>. Un flusso di dati rappresenta la configurazione lato server durante l’implementazione di Adobe Experience Platform Web SDK.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html">Configurare uno stream di dati<a></td> 
</tr>

<td>6</td>
<td><b>Aggiungere un servizio Adobe Analytics</b> allo stream di dati. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics e a quali suite di rapporti in particolare.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Aggiungere il servizio Adobe Analytics a uno stream di dati</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configurare l’SDK per web</b>. Assicurati che la libreria installata nel passaggio 4 sia configurata correttamente con l’ID dello stream di dati (precedentemente noto come ID di configurazione edge )<code>edgeConfigId</code>)), id organizzazione (<code>orgId</code>) e altre opzioni disponibili. Assicurati che la mappatura delle variabili sia corretta. </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/configure/overview.html">Configurare l’SDK per web</a><br/><a href="../xdm-var-mapping.md">Mappatura variabile oggetto XDM</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Esegui comandi</b> e/o <b>tracciare gli eventi</b>. Una volta implementato il codice di base nella pagina web, puoi iniziare a eseguire comandi ed eventi di tracciamento con l’SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/sendevent/overview.html">Inviare eventi</a></td>
</tr>

<tr>
<td>9</td><td><b>Estendere e convalidare l’implementazione</b> prima di implementarlo in produzione.</td><td></td> 
</tr>
</table>
