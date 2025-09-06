---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 33%

---

# Note sulla versione corrente di Adobe Analytics (versione di agosto 2025)

**Ultimo aggiornamento**: giovedì 13 agosto 2025

Queste note sulla versione coprono il periodo dal 13 agosto al 16 settembre 2025. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analizzare il traffico di IA con un nuovo elemento della dimensione Tipo referente** | A ottobre, sarà disponibile un nuovo elemento dimensione di tipo Referrer per aiutare ad analizzare il traffico proveniente da strumenti AI. <p>Questo nuovo elemento dimensione di tipo Referrer, denominato Strumenti di IA per la conversazione, raggrupperà i domini di riferimento dei principali strumenti di IA per la conversazione, consentendo di esaminare le tendenze per il gruppo nel suo insieme. L’elenco iniziale dei domini di riferimento in questa nuova categoria include (ma non è limitato a):</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>Il nuovo elemento dimensionale sarà disponibile in tutti gli strumenti relativi ad Adobe Analytics, inclusi Analysis Workspace, Report Builder, Data Warehouse, feed dati e così via.</p><p>Quando utilizzi questo nuovo elemento dimensione, tieni presente quanto segue:</p><ul><li>Non è sempre possibile distinguere il traffico del referente proveniente da risultati forniti in &quot;modalità IA&quot; in un motore di ricerca rispetto a quelli derivanti da click-through da risultati di ricerca tradizionali.</li><li>Il nuovo elemento dimensionale Strumenti di IA per la conversazione si concentra sui fornitori principali con il maggior traffico. Una nuova tendenza rivela un numero crescente di siti di impersonificazione con domini simili ai principali fornitori di strumenti di intelligenza artificiale. Ciò è probabilmente dovuto alla facilità con cui singoli utenti o gruppi possono creare i propri strumenti di intelligenza artificiale e ospitarli su Internet. Poiché si tratta di uno spazio in rapida evoluzione, se scopri che un sito popolare non è incluso, contatta il team di supporto Adobe.</li><li>La dimensione Tipo referente, che include il nuovo elemento dimensione Strumenti di IA per la conversione, è disponibile solo per i dati elaborati da Adobe Analytics. </li></ul><p>Il collegamento alla documentazione seguirà a breve.</p> |   | Ottobre 2025 |
| **I progetti scaricati come file PDF vengono scaricati nella workstation** | Durante il download di un progetto come file PDF, il PDF viene scaricato nella cartella dei download sulla workstation. <p>In precedenza, il download di un progetto come file PDF avviava il PDF in una nuova scheda del browser con un URL univoco.</p><p>Per ulteriori informazioni, consulta [Scaricare progetti e dati](/help/analyze/analysis-workspace/curate-share/download-send.md)</p> |  | 25 agosto 2025 |
| **I progetti eliminati non sono più immediatamente disponibili tramite URL e vengono rimossi dalle consegne pianificate** | I progetti eliminati vengono immediatamente rimossi dalle consegne pianificate e non sono più accessibili dal relativo URL.<p>In precedenza, i progetti venivano inclusi nelle consegne pianificate e potevano essere accessibili tramite il rispettivo URL per 60 giorni dopo l’eliminazione.</p><p>Per ulteriori informazioni sull’eliminazione dei progetti, consulta la sezione [Panoramica sui progetti](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Fine agosto 2025 |
| **Servizi multimediali in streaming: campi XDM aggiornati per la raccolta di dati multimediali in streaming in Adobe Experience Platform** | Durante la raccolta di dati multimediali in streaming in Adobe Experience Platform, i percorsi dei campi XDM mostrati nell’intestazione &quot;Percorso campo XDM&quot; della documentazione sui parametri dei contenuti multimediali in streaming non devono più essere utilizzati. Al contrario, i clienti che hanno implementato il connettore di origine di Analytics per raccogliere i dati multimediali in streaming in Platform prima del 9 maggio 2025 devono migrare le configurazioni esistenti ai percorsi dei campi mediaReporting, come illustrato nell’intestazione &quot;Percorso campo XDM per reporting&quot; della documentazione sui parametri dei contenuti multimediali in streaming.<p> I percorsi dei campi sono disponibili nelle pagine seguenti e sono contrassegnati come &quot;Obsoleti&quot;: [Parametri audio e video](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parametri annuncio](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/ad-parameters), [Parametri capitolo](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parametri stato lettore](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parametri qualità](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/variables/quality-parameters). Per la clientela che implementa il connettore di origine di Analytics dopo il 9 maggio 2025 e sta già utilizzando solo i percorsi XDM mediaReporting, non è richiesta alcuna azione.</p><p>L’acquisizione dei dati sui percorsi dei campi XDM obsoleti continuerà fino alla fine di ottobre 2025. Dopo tale periodo, i percorsi dei campi obsoleti verranno completamente rimossi e non saranno più visibili nell’interfaccia utente dello schema di Adobe Experience Platform e i dati verranno inviati solo utilizzando i percorsi dei campi mediaReporting.</p><p>Per ulteriori informazioni, consulta [Migrare un&#39;implementazione del connettore Source di Analytics ai campi multimediali in streaming XDM aggiornati](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Contatta i servizi Adobe Consulting o il team del tuo account per ricevere supporto alla migrazione. </p> |  | Ottobre 2025 |

## Correzioni in Adobe Analytics

**Activity Map**: AN-389205; AN-384186
**Analysis Workspace**: AN-390102; AN-389066; AN-388841; AN-388687; AN-388478; AN-387089; AN-387044; AN-384560; AN-379213; AN-351639
**Classificazioni**: AN-390442; AN-390385; AN-389953; AN-389703; AN-389321; AN-389116; AN-388833; AN-388717; AN-387987; AN-383329
**Raccolta dati**: AN-389320
**Feed dati e Data Warehouse**: AN-389702; AN-388136; AN-387779; AN-384369; AN-383075; AN-380307
**Privacy**:
**Report Builder**: AN-389336; AN-382775
**Generazione rapporti**: AN-390398
**Report pianificati**:
**Confronto segmenti**:
**Altro**: AN-388180; AN-383164; AN-366532


## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Report Builder legacy** | 18 giugno 2025 | Il componente aggiuntivo legacy di Report Builder verrà ritirato a giugno 2026. Tutti gli utenti devono iniziare ad aggiornare le cartelle di lavoro legacy al [nuovo Report Builder](/help/analyze/report-builder/rb-overview.md). Il nuovo Report Builder è disponibile per i clienti di Adobe Analytics e Customer Journey Analytics. Ha [parità di funzionalità](/help/analyze/report-builder/convert-workbooks.md#unsupported) oltre a numerose nuove funzioni convenienti e miglioramenti all&#39;interfaccia utente. Per facilitare il processo di aggiornamento, il nuovo Report Builder include una funzione di conversione della cartella di lavoro semplice. Il nuovo Report Builder è disponibile solo come componente aggiuntivo tramite Microsoft Store. Molte organizzazioni richiedono un processo di approvazione interno prima che il componente aggiuntivo possa essere reso disponibile agli utenti. Attendi l’ora per questo processo e inizia a lavorare con la tua organizzazione ora per assicurarti di disporre del tempo sufficiente per aggiornare le cartelle di lavoro prima della data di fine del ciclo di vita. |
| **Accesso tramite domini legacy o tramite SSO legacy** | venerdì 10 aprile 2025 | Adobe prevede di aggiornare il modo in cui gli utenti accedono ad Adobe Analytics per migliorare la sicurezza e semplificare l’esperienza di accesso. Come parte di questo impegno, l&#39;accesso tramite domini legacy o tramite SSO legacy, incluso `my.omniture.com`, verrà interrotto definitivamente il **2 gennaio 2026**. Dopo questa data, le credenziali di accesso legacy e l’SSO legacy non funzioneranno più. Tutti gli utenti dovranno effettuare l&#39;accesso tramite `experience.adobe.com` utilizzando i propri ID Adobe Experience Cloud. Se hai bisogno di assistenza con il tuo Experience Cloud ID, contatta l&#39;amministratore Adobe Analytics della tua organizzazione o l&#39;[Assistenza clienti Adobe](https://helpx.adobe.com/it/contact.html). |
| **API Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, fai riferimento alle [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Risorse correlate

* [Note sulle versioni precedenti 2025](/help/release-notes/2025.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Streaming Media Services](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
