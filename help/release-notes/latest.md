---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7468463e2fe1de16221b4528919b6abd6c8aedcb
workflow-type: ht
source-wordcount: '1403'
ht-degree: 100%

---

# Note sulla versione corrente di Adobe Analytics (aprile 2024)

**Ultimo aggiornamento**: 17 aprile 2024

Queste note sulla versione coprono il periodo di rilascio compreso tra il 17 aprile 2024 e maggio 2024. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Contenuti in streaming: invio di dati Roku alla rete Edge di Adobe Experience Platform** | Ora quando si installa [Media Analytics con la rete Edge di Experience Platform](https://experienceleague.adobe.com/it/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), è possibile utilizzare l’SDK per Roku di Adobe Experience Platform per inviare dati di contenuti in streaming ad Adobe Experience Platform. |  | 12 aprile 2024 |
| **Flusso di lavoro migliorato per la migrazione di Web SDK** | Gli stream di dati ora mappano automaticamente i campi dall’oggetto dati del Web SDK direttamente in Adobe Analytics. La[mappatura degli oggetti dati](/help/implement/aep-edge/data-var-mapping.md) è simile alla [mappatura degli oggetti XDM](/help/implement/aep-edge/xdm-var-mapping.md), ma non richiede uno schema XDM. Questo flusso di lavoro migliorato offre i seguenti vantaggi:<ul><li>La richiesta di utilizzo di uno schema viene posticipata fino a quando non si è pronti ad inviare dati ad Adobe Experience Platform. Se in questa fase della migrazione di un’implementazione fosse necessario uno schema, bisognerebbe utilizzare uno schema basato sui campi di Adobe Analytics. I servizi di Adobe Experience Platform, come Customer Journey Analytics, non hanno un concetto di prop o eVar. Uno schema incentrato su Analytics può creare delle difficoltà se l’organizzazione desidera utilizzare il proprio schema in futuro.</li><li>Dopo aver apportato modifiche all’implementazione del Web SDK, l’organizzazione è in una posizione migliore per migrare da Adobe Analytics a Customer Journey Analytics. Se invii dati ad Adobe Analytics utilizzando Web SDK, non è necessario apportare ulteriori modifiche di implementazione per inviare dati ad Adobe Experience Platform. Puoi invece utilizzare la preparazione dati per mappare i campi dell’oggetto dati sullo schema XDM.</li></ul>Per ulteriori informazioni consulta [Migrare dall’estensione del tag di Adobe Analytics all’estensione del tag Web SDK](/help/implement/aep-edge/web-sdk/analytics-extension-to-web-sdk.md) e [Migrare da AppMeasurement a Web SDK](../implement/aep-edge/web-sdk/appmeasurement-to-web-sdk.md). |  | Aprile 2024 |
| **Miglioramento delle autorizzazioni per i [!UICONTROL Workspace] componenti** di solo progetto | In precedenza, se un utente (utente A) condivideva un progetto con un altro utente (utente B) e dava a questo l’accesso per la modifica al progetto, l’utente B sarebbe stato in grado di modificare il progetto. Tuttavia, l’utente B non poteva modificare i [!UICONTROL Quick Segments] incorporati nel progetto. Questa limitazione è ora rimossa - L’utente B può modificare i [!UICONTROL Quick Segments] e altri componenti di solo progetto incorporati nel progetto condiviso. |  | 17 aprile 2024 |
| **Utilizza gli stessi account cloud per [!UICONTROL Data Feeds], [!UICONTROL Data Warehouse], e[!UICONTROL Classification sets]** | Ora è possibile utilizzare gli account e le posizioni cloud creati per esportare i dati (tramite [!UICONTROL Data Feeds] e [!UICONTROL Data Warehouse]) e importare i dati (tramite [!UICONTROL Classification sets]).<p> **Modifiche durante la configurazione degli account:** gli utenti possono [configurare gli account cloud di importazione ed esportazione](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-accounts) e [configurare le posizioni cloud di importazione ed esportazione](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-locations) che possono essere utilizzate per uno dei seguenti scopi:<ul><li>Importazione di dati con [!UICONTROL Classification sets]</li><li>Esportazione di dati con [!UICONTROL Data Feeds]</li><li>Esportazione di dati con [!UICONTROL Data Warehouse].</li></ul><p>**Modifiche durante la gestione degli account e delle posizioni dalla pagina delle [!UICONTROL Locations]**: gli utenti possono utilizzare la pagina [Posizioni](https://experienceleague.adobe.com/it/docs/analytics/components/locations/locations-manager) (in [!UICONTROL Components] > Posizioni) per visualizzare e gestire tutti gli account e le posizioni creati, indipendentemente da dove sono stati creati. <p>In precedenza, la pagina delle [!UICONTROL Locations] si applicava solo agli account creati per l’importazione di dati con [!UICONTROL Classification sets].</p>**Modifiche durante la gestione delle posizioni da [!UICONTROL Data Warehouse] o[!UICONTROL Classification sets]**<p>Durante la gestione delle posizioni all’interno di una determinata area di applicazione ([!UICONTROL Data Warehouse] o [!UICONTROL Classification sets]), sono disponibili solo le posizioni create in quell’area di applicazione specifica. Ad esempio, quando si visualizza l’area di applicazione di [!UICONTROL Data Warehouse], sono disponibili solo le posizioni di [!UICONTROL Data Warehouse]. Tutti gli account sono ancora disponibili in ogni area di applicazione, indipendentemente dall’area in cui sono stati creati. In precedenza, tutti gli account e le posizioni erano disponibili in ogni area di applicazione, indipendentemente dall’area in cui erano stati creati. Questo è ancora vero quando si visualizza l’area di applicazione dei [!UICONTROL Data Feeds]. | | 17 aprile 2024 |
| **Gli amministratori possono gestire tutte le posizioni e gli account all’interno dell’organizzazione** | Una nuova opzione nella scheda Posizioni (nella pagina Componenti > pagina Posizioni) consente agli amministratori di visualizzare e gestire tutte le posizioni dell’organizzazione.<p>Una nuova opzione nella scheda degli account [Posizione](https://experienceleague.adobe.com/it/docs/analytics/components/locations/locations-manager) (nella pagina Componenti > pagina Posizioni) consente agli amministratori di visualizzare e gestire tutti gli account dell’organizzazione.</p> <p>In precedenza, gli amministratori potevano visualizzare e gestire solo le posizioni e gli account che avevano creato.</p> |  | 17 aprile 2024 |
| **Aumento delle soglie predefinite per traffico ridotto** | Verso la **metà di aprile 2024**, Adobe inizierà ad aumentare le soglie di traffico ridotto della suite di rapporti predefinita come segue: ![soglie di traffico ridotto](assets/thresholds.png). Questo influisce solo sulle variabili attualmente impostate al di sotto delle nuove soglie. Queste modifiche saranno apportate in modo incrementale ed è previsto che il lavoro sia completato entro la **fine del mese di maggio**. Con l’introduzione di questi aumenti, potresti notare modifiche per le variabili ad alta cardinalità:<ul><li>Per il reporting possono essere disponibili più valori di dimensione.</li><li>Segmenti e metriche calcolate possono includere più dati.</li><li>Le suite di rapporti virtuali basate sui segmenti possono includere più dati.</li><li>Le esportazioni delle classificazioni possono includere più dati.</li></ul> | Metà aprile 2024 | 31 maggio 2024 |
| **L’Activity Map utilizza un numero inferiore di chiamate server per Web SDK** | Attualmente, gli eventi di collegamento Activity Map vengono conteggiati come propri eventi e comportano costi aggiuntivi. <p>Questo miglioramento raccoglie alcuni eventi di collegamento e li inserisce nell’hit successivo, in modo simile a come gli eventi vengono gestiti da AppMeasurement.</p> |  | 31 maggio 2024 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* Sono stati risolti i seguenti problemi di classificazione: AN-343439; AN-343503; AN-343504; AN-343986; AN-344262; AN-344564; AN-345204; AN-345234
* Sono stati risolti i seguenti problemi relativi al generatore di regole di classificazione: AN-341488; AN-342501; AN-345751
* È stato risolto il seguente problema relativo al sistema di avvisi intelligenti: AN-343466;
* È stato risolto il seguente problema relativo alla segmentazione: AN-342313
* È stato risolto il seguente problema relativo a Data Warehouse: AN-344292
* Sono stati risolti i seguenti problemi relativi ai feed di dati: AN-339545; AN-340092; AN-342124; AN-342862; AN-343737; AN-344035; AN-344329; AN-344703; AN-344721; AN-344940; AN-345180; AN-345196; AN-345225; AN-345236; AN-345326; AN-345631; AN-345659
* Sono stati risolti i seguenti problemi relativi alle origini dati: AN-343541
* Sono stati risolti i seguenti problemi relativi ad Analysis Workspace: AN-336303; AN-336472; AN-338422; AN-338556; AN-339718; AN-340147; AN-340301; AN-340421; AN-340951; AN-341172; AN-342905; AN-342909; AN-343448; AN-343570; AN-344050; AN-344182; AN-344763; AN-344768;
* Sono stati risolti i seguenti problemi relativi all’amministrazione di Analytics: AN-342519; AN-342523; AN-343623; AN-343882; AN-344237; AN-344829; AN-345235;
* Sono stati risolti i seguenti problemi relativi a A4T: AN-341619; AN-344402
* È stato risolto il seguente problema relativo all’app per dispositivo mobile: AN-342010

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
