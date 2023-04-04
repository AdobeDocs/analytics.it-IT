---
title: Fine del ciclo di vita per l’elaborazione completa delle origini dati
description: Ulteriori informazioni sull'annuncio della fine del ciclo di vita per le origini dati a elaborazione completa.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 7%

---

# Fine del ciclo di vita per l’elaborazione completa delle origini dati

Le origini dati a elaborazione completa hanno sempre consentito alle organizzazioni di inviare dati a livello di hit in Adobe Analytics. Questi dati sono stati elaborati allo stesso modo dei dati raccolti tramite metodi tradizionali di raccolta dati, come AppMeasurement. Nel 2020, Adobe ha rilasciato il [API di inserimento dati in blocco](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), che esegue le stesse funzioni delle origini dati a elaborazione completa, ma con funzioni aggiuntive. Questa pagina fornisce dettagli sulle funzionalità aggiuntive fornite dall’API di inserimento dati in blocco e illustra le differenze nei formati di file.

Il 25 marzo 2021, Adobe ha impedito la creazione di nuove connessioni di origini dati a elaborazione completa. Il 31 gennaio 2022 sono stati disattivati tutti i servizi di trattamento completo dei dati.

## Differenze chiave tra le origini dati a elaborazione completa e l’API di inserimento dati in blocco

* L’inserimento di dati in blocco consente di inviare più file per l’elaborazione parallela. I gruppi di visitatori garantiscono la continuità del visitatore e l’attribuzione eVar.
* L’inserimento di dati in blocco dispone di funzionalità di convalida dei dati e gestione degli errori, rimuovendo parte del lavoro amministrativo di invio dei dati degli hit.
* L&#39;inserimento di dati in blocco supporta più metodi di identificazione degli ID visitatore.
* L’inserimento di dati in blocco contiene alcuni campi obbligatori aggiuntivi: Una colonna di identificazione del visitatore, una `pageName` (o equivalente collegamento), `reportSuiteID`, `timestamp`e `userAgent`.
* Per garantire la continuità e l’attribuzione dei visitatori, l’inserimento di dati in blocco richiede che le righe all’interno dei file siano ordinate in ordine cronologico. Vedi [Gruppi di visitatori](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) per informazioni sull’ordinamento dell’attività del visitatore tra file.
* L’inserimento di dati in blocco richiede che i file siano compressi con estensione .csv in formato .gzip.
* Utilizzo BDIA `timestamp` anziché `date`.

## Confronto tra variabili BDIA e fonti di dati a elaborazione completa

Le seguenti variabili sono state introdotte nell’inserimento di dati in blocco, precedentemente non disponibili nelle origini dati a elaborazione completa:

* **`aamlh`**: Suggerimento sulla posizione di Adobe Audience Manager.
* **`contextData.key`**: [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**: Experience Cloud di variabili del servizio ID. Include `id`, `authState` e `isMCSeed`.
* **`hints`**: [Suggerimento client](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html) variabili. Include `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion`e `wow64`.
* **`ipaddress`**: L’indirizzo IP del visitatore.
* **`language`**: La [Lingua](/help/components/dimensions/language.md) dimensione.
* **`list1`** - **`list3`**: [Variabili elenco](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**: L’Experience Cloud ID del visitatore.
* **`tnta`**: Payload di dati di Target utilizzato in [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=it) integrazioni.
* **`trackingServer`**: La [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) variabile.
* **`transactionID`**: La [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variabile.
* **`userAgent`**: Stringa dell&#39;agente utente del dispositivo.

Le seguenti variabili non sono supportate tramite l’inserimento di dati in blocco:

* **`charSet`**: La [`charSet`](/help/implement/vars/config-vars/charset.md) variabile. L&#39;inserimento di dati in blocco supporta solo UTF-8.
* **`timezone`**: L’offset del fuso orario del visitatore da GMT in ore.
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**: Variabili utilizzate nella raccolta dati di Activity Map.
