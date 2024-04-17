---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d2b2ebdbc6a3c0f20b8684ba5c1b4b89cefb8e5a
workflow-type: tm+mt
source-wordcount: '1211'
ht-degree: 52%

---

# Note sulla versione corrente di Adobe Analytics (aprile 2024)

**Ultimo aggiornamento**: giovedì 17 aprile 2024

Queste note sulla versione coprono il periodo dal 17 aprile 2024 a maggio. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Streaming Media: invia dati Roku all’Edge Network di Adobe Experience Platform** | Ora quando [installazione di Media Analytics con Experienci Platform Edge](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), puoi utilizzare Adobe Experience Platform Roku SDK per inviare dati multimediali in streaming a Adobe Experience Platform. |  | sabato 12 aprile 2024 |
| **Flusso di lavoro migliorato per la migrazione dell&#39;SDK per web** | La Raccolta dati di Adobe Experience Platform ora mappa automaticamente molti campi dall’oggetto dati direttamente su Adobe Analytics. Questo flusso di lavoro migliorato offre i seguenti vantaggi:<ul><li>Consente all’organizzazione di migrare all’SDK per web senza preoccuparsi di creare o aderire a un [!UICONTROL XDM schema]. Consulta [Mappatura variabile oggetto dati](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping) per ulteriori informazioni. (Seguono altri collegamenti alla documentazione)</li><li>Dopo la migrazione a Web SDK, la tua organizzazione è in una posizione migliore per migrare da Adobe Analytics a Customer Journey Analytics. Questo perché l’SDK per web consente una migrazione più fluida al Customer Journey Analytics.</li></ul> (Ulteriori informazioni su questa e altre opzioni di migrazione saranno presto disponibili.) |  | Aprile 2024 |
| **Miglioramento delle autorizzazioni per solo progetto [!UICONTROL Workspace] componenti** | In precedenza, se un utente (Utente A) condivideva un progetto con un altro utente (Utente B) e dava all’Utente B l’accesso in modifica al progetto, l’Utente B sarebbe stato in grado di modificare il progetto. Tuttavia, l’utente B non può modificare [!UICONTROL Quick Segments] incorporato nel progetto. Questa limitazione è ora rimossa - l’utente B può modificare [!UICONTROL Quick Segments] e altri componenti solo progetto incorporati nel progetto condiviso. |  | giovedì 17 aprile 2024 |
| **Utilizza gli stessi account cloud per [!UICONTROL Data Feeds], [!UICONTROL Data Warehouse], e[!UICONTROL Classification sets]** | Ora è possibile utilizzare gli account e le posizioni cloud creati per esportare i dati (con [!UICONTROL Data Feeds] e [!UICONTROL Data Warehouse]) e l&#39;importazione di dati (con [!UICONTROL Classification sets]).<p> **Modifiche durante la configurazione degli account:** Gli utenti possono [Configurare account di importazione ed esportazione cloud](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) e [Configurare i percorsi di importazione ed esportazione cloud](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations) che possono essere utilizzati per uno dei seguenti scopi:<ul><li>Importazione di dati con [!UICONTROL Classification sets]</li><li>Esportazione di dati con [!UICONTROL Data Feeds]</li><li>Esportazione di dati con [!UICONTROL Data Warehouse].</li></ul><p>**Modifiche durante la gestione degli account**: gli utenti possono utilizzare [Posizioni](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) pagina (sotto [!UICONTROL Components] > Locper visualizzare e gestire tutti gli account e le posizioni creati, indipendentemente da dove sono stati creati. <p>Precedentemente, il [!UICONTROL Locations] pagina applicata solo agli account creati per l&#39;importazione di dati con [!UICONTROL Classification sets].</p> | | giovedì 17 aprile 2024 |
| **Gli amministratori possono gestire tutte le posizioni e gli account all’interno dell’organizzazione** | Una nuova opzione nella scheda Posizioni (nella pagina Componenti > pagina Posizioni) consente agli amministratori di visualizzare e gestire tutte le posizioni dell’organizzazione.<p>Una nuova opzione sul [Posizione](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) La scheda account (nella pagina Componenti > Posizioni) consente agli amministratori di visualizzare e gestire tutti gli account dell’organizzazione.</p> <p>In precedenza, gli amministratori potevano visualizzare e gestire solo le posizioni e gli account che avevano creato.</p> |  | giovedì 17 aprile 2024 |
| **Aumento delle soglie predefinite per traffico ridotto** | Verso la **metà di aprile 2024**, Adobe inizierà ad aumentare le soglie di traffico ridotto della suite di rapporti predefinita come segue: ![soglie di traffico ridotto](assets/thresholds.png). Questo influisce solo sulle variabili attualmente impostate al di sotto delle nuove soglie. Queste modifiche saranno apportate in modo incrementale ed è previsto che il lavoro sia completato entro la **fine del mese di maggio**. Con l’introduzione di questi aumenti, potresti notare modifiche per le variabili ad alta cardinalità:<ul><li>Per il reporting possono essere disponibili più valori di dimensione.</li><li>Segmenti e metriche calcolate possono includere più dati.</li><li>Le suite di rapporti virtuali basate sui segmenti possono includere più dati.</li><li>Le esportazioni delle classificazioni possono includere più dati.</li></ul> | Metà aprile 2024 | sabato 31 maggio 2024 |
| **L’Activity Map utilizza un numero inferiore di chiamate server per Web SDK** | Attualmente, gli eventi di collegamento Activity Map vengono conteggiati come propri eventi e comportano costi aggiuntivi. <p>Questo miglioramento raccoglie alcuni eventi di collegamento e li inserisce nell’hit successivo, in modo simile a come gli eventi vengono gestiti da AppMeasurement.</p> |  | sabato 31 maggio 2024 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* Sono stati risolti i seguenti problemi di classificazione: AN-343439; AN-343503; AN-343504; AN-343986; AN-344262; AN-344564; AN-345204; AN-345234
* Sono stati risolti i seguenti problemi relativi al Generatore di regole di classificazione: AN-341488; AN-342501; AN-345751
* È stato risolto il seguente problema di avvisi intelligenti: AN-343466;
* È stato risolto il seguente problema relativo alla segmentazione: AN-342313
* È stato risolto il seguente problema di Data Warehouse: AN-344292
* Sono stati risolti i seguenti problemi relativi ai feed di dati: AN-339545; AN-340092; AN-342124; AN-342862; AN-343737; AN-344035; AN-344329; AN-344703; AN-344721; AN-344940; AN-345180; AN-345196; AN-345225; AN-345236; AN-345326; AN-345631; AN-345659
* È stato risolto il seguente problema di Origini dati: AN-343541
* Sono stati risolti i seguenti problemi di Analysis Workspace: AN-336303; AN-336472; AN-338422; AN-338556; AN-339718; AN-340147; AN-340301; AN-340421; AN-340951; AN-341172; AN-342905; AN-342909; AN-343448; AN-343570; AN-344050; AN-344182; AN-344763; AN-344768;
* Sono stati risolti i seguenti problemi relativi all’amministrazione di Analytics: AN-342519; AN-342523; AN-343623; AN-343882; AN-344237; AN-344829; AN-345235;
* Sono stati risolti i seguenti problemi di A4T: AN-341619; AN-344402
* È stato risolto il seguente problema relativo all’app mobile: AN-342010

### Altre correzioni apportate ad Analytics

AN-336099; AN-337474; AN-337993; AN-339718; AN-339901; AN-340014; AN-341356; AN-343021; AN-343102; AN-343353; AN-343416; AN-340014; AN-344037; AN-344525; AN-345737

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza di 13 mesi di`cust_visids`** salvati | 20 marzo 2024 | Una prossima versione del motore di elaborazione degli hit di Analytics, prevista per aprile o maggio, inizierà ad applicare una scadenza di 13 mesi di `cust_visids` salvati. Se nella suite di rapporti è abilitato “Abilita unione visitatori”, questa impostazione viene utilizzata per trovare `cust_visid` per un `visid_high/visid_low value` senza `cust_visid` sull’hit. Attualmente, non vi è alcuna scadenza della mappatura di un `cust_visid` per un `visid_high/visid_low`. Con questa versione, se sono trascorsi 13 mesi o più da quando `visid_high/visid_low` ha avuto un `cust_visid` su un hit, la mappatura scadrà. |
| **Aggiunte di membri agli oggetti API di Adobe** | 17 gennaio 2024 | Adobe può aggiungere membri di richiesta e risposta facoltativi (coppie nome/valore) agli oggetti API esistenti in qualsiasi momento e senza preavviso, né modifiche nel controllo delle versioni. Adobe consiglia di fare riferimento alla documentazione API di qualsiasi strumento di terze parti integrato con le proprie API, in modo che tali aggiunte, se non comprese, vengano ignorate durante l’elaborazione. Se implementate correttamente, tali aggiunte rappresentano modifiche che non comportato interruzioni per l’implementazione. Adobe non rimuove né aggiunge parametri richiesti senza prima fornire una notifica standard tramite le note sulla versione. |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.26.0), fare riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2023](/help/release-notes/2023.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
