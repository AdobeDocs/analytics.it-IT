---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 49e7e64254a6466af852ee6dd48c7b37a15c744c
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 79%

---

# Note sulla versione corrente di Adobe Analytics (maggio 2024)

**Ultimo aggiornamento**: giovedì 22 maggio 2024

Queste note sulla versione coprono il periodo di rilascio dal 15 maggio 2024 fino a tutto giugno. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nuova documentazione per l’aggiornamento da Adobe Analytics a Customer Journey Analytics** | Per le organizzazioni che eseguono l’aggiornamento da Adobe Analytics a Customer Journey Analytics, esistono diverse opzioni e molte considerazioni da tenere a mente, a seconda dell’implementazione Adobe Analytics corrente e degli obiettivi a lungo termine dell’organizzazione. Sono ora disponibili nuove risorse di documentazione per aiutarti a comprendere meglio:<ul><li>I vari percorsi di aggiornamento esistenti</li><li>Quali percorsi di aggiornamento sono disponibili in base all’implementazione Adobe Analytics corrente dell’organizzazione</li><li>Vantaggi e svantaggi di ciascun percorso di aggiornamento</li><li>Linee guida dettagliate per ogni percorso di aggiornamento</li><li>Considerazioni per la gestione dei dati storici</li></ul>[Introduzione alla migrazione a Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Disponibile ora |
| **Impostare i campi `contextData` tramite XDM** | I clienti che inviano dati ad Adobe Analytics tramite la rete Experience Edge possono [impostare i valori dei dati contestuali](https://experienceleague.adobe.com/it/docs/analytics/implementation/vars/page-vars/contextdata) direttamente in XDM o nelle parti “dati” del payload. |  | Disponibile ora |
| **API di Reporting in tempo reale 2.0 di Analytics** | La nuova API di Reporting in tempo reale 2.0 di Adobe Analytics migliora l’integrazione dei clienti e fornisce risultati di reporting rapidi. Questi risultati possono essere utilizzati a livello di programmazione per lavorare con rapporti di base, con tendenze e con raggruppamenti. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/real-time/) | | 30 maggio 2024 |
| **Dati multimediali in streaming: invia dati web alla rete Edge di Adobe Experience Platform con Web SDK** | Ora puoi utilizzare Adobe Experience Platform Web SDK per inviare dati multimediali in streaming alla rete Edge di Adobe Experience Platform. Questo miglioramento consente di creare campagne più personalizzate e fornire contenuti più personalizzati, con conseguente aumento dei dati di tracciamento da includere nei rapporti.<p>Questa modifica fornisce un metodo di raccolta unificato per le implementazioni web in tutte le soluzioni Platform, come Customer Journey Analytics, Adobe Real-time CDP, Adobe Journey Optimizer e inoltro eventi. In precedenza, l’unico modo per inviare i dati web di Streaming Media ad Edge Network era utilizzare l’API Media Edge. <p>(Il link alla documentazione è stato aggiornato)</p> | | 31 maggio 2024 |
| **Aumento delle soglie predefinite per traffico ridotto** | Verso la **metà di aprile 2024**, Adobe inizierà ad aumentare le soglie di traffico ridotto della suite di rapporti predefinita come segue: ![soglie di traffico ridotto](assets/thresholds.png). Questo influisce solo sulle variabili attualmente impostate al di sotto delle nuove soglie. Queste modifiche saranno apportate in modo incrementale ed è previsto che il lavoro sia completato entro la **fine del mese di maggio**. Con l’introduzione di questi aumenti, potresti notare modifiche per le variabili ad alta cardinalità:<ul><li>Per il reporting possono essere disponibili più valori di dimensione.</li><li>Segmenti e metriche calcolate possono includere più dati.</li><li>Le suite di rapporti virtuali basate sui segmenti possono includere più dati.</li><li>Le esportazioni delle classificazioni possono includere più dati.</li></ul> | Metà aprile 2024 | 31 maggio 2024 |
| **Impostazioni dell&#39;amministratore per controllare gli account e le posizioni utilizzati per l&#39;esportazione e l&#39;importazione** | Una nuova scheda &quot;Impostazioni amministratore&quot; in Gestione posizioni consente agli amministratori di controllare se gli utenti possono creare e modificare account e posizioni. Queste impostazioni si applicano quando gli utenti configurano account di importazione ed esportazione cloud e percorsi di importazione ed esportazione cloud. <p>Gli amministratori possono anche limitare i tipi di account (Google Cloud Platform, Azure RBAC, Amazon S3 e così via) che gli utenti possono creare e utilizzare.</p><p>In precedenza, qualsiasi utente poteva creare, modificare e utilizzare account e posizioni per qualsiasi tipo di account.</p><p>(Il link alla documentazione è stato aggiornato)</p> | Giugno 2024 | Giugno 2024 |
| **Condividere account e percorsi utilizzati per l&#39;esportazione e l&#39;importazione** | Gli utenti possono ora rendere disponibili a tutti gli utenti della propria organizzazione gli account e le posizioni creati. Solo i proprietari degli account e delle posizioni e gli amministratori di sistema possono modificare ed eliminare gli account e le posizioni.<p>In precedenza, gli account e le posizioni potevano essere utilizzati solo dall’utente che li aveva creati.</p><p>Queste impostazioni sono disponibili quando gli utenti configurano account di importazione ed esportazione cloud e percorsi di importazione ed esportazione cloud. </p> <p>(Il link alla documentazione è stato aggiornato)</p> | Giugno 2024 | Giugno 2024 |
| **Fare in modo che Activity Map utilizzi un numero inferiore di chiamate server per Web SDK** | Attualmente, gli eventi di collegamento Activity Map vengono conteggiati come propri eventi e comportano costi aggiuntivi. Questo miglioramento raccoglie alcuni eventi di collegamento e li inserisce nell’hit successivo, in modo simile a come gli eventi vengono gestiti da AppMeasurement. <p>(Il link alla documentazione è stato aggiornato)</p> | La versione beta inizia il 31 maggio 2024 | Da definire |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* Sono stati risolti i seguenti problemi di classificazione: AN-343186; AN-344711; AN-344856; AN-345094; AN-345179; AN-346265; AN-345288; AN-346339; AN-346560; AN-347572; AN-347681; AN-347768; AN-348024
* Sono stati risolti i seguenti problemi di data warehouse: AN-346789; AN-347031; AN-347568;
* Sono stati risolti i seguenti problemi relativi ai feed di dati: AN-343616; AN-345831; AN-345988; AN-346124; AN-346232; AN-346972; AN-347680; AN-347755; AN-347954
* Sono stati risolti i seguenti problemi relativi alle origini dati: AN-347890;
* Sono stati risolti i seguenti problemi di Analysis Workspace: AN-321503; AN-343103; AN-343471; AN-345171; AN-345223; AN-345912; AN-346026; AN-346330; AN-346839; AN-347679
* È stato risolto il seguente problema relativo a A4T: AN-345118;

### Altre correzioni apportate ad Analytics

AN-327749; AN-332949; AN-342881; AN-343171; AN-343708; AN-344034; AN-345559; AN-346023; AN-346230; AN-346330; AN-346469; AN-346606; AN-346750; AN-346973; AN-347026; AN-347110; AN-347439;

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza di 13 mesi di`cust_visids`** salvati | giovedì 22 maggio 2024 | Una prossima versione del motore di elaborazione degli hit di Analytics, **previsto per luglio 2024**, inizierà ad applicare una scadenza di 13 mesi di `cust_visids`. Se nella suite di rapporti è abilitato “Abilita unione visitatori”, questa impostazione viene utilizzata per trovare `cust_visid` per un `visid_high/visid_low value` senza `cust_visid` sull’hit. Attualmente, non vi è alcuna scadenza della mappatura di un `cust_visid` per un `visid_high/visid_low`. Con questa versione, se sono trascorsi 13 mesi o più da quando `visid_high/visid_low` ha avuto un `cust_visid` su un hit, la mappatura scadrà. |
| **Aggiornamenti per area geografica ISO** | 10 maggio 2024 | Il 7 giugno 2024 Adobe eseguirà gli aggiornamenti per l’area geografica ISO 2024. Con questa versione, sono previsti aggiornamenti minori relativi alle aree geografiche. |

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
