---
title: Fine del ciclo di vita delle origini dati a elaborazione completa
description: Ulteriori informazioni sull’annuncio della fine del ciclo di vita per le origini dati a elaborazione completa.
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
role: Admin
TQID: 'https://experienceleague.adobe.com/3NSbjRWl0GsomjsEXo8XczQ1RWOPGpqW4OM2YeUo3Wk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f46a60da-b0b2-4ca3-bd91-271173f4123d
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 414
ht-degree: 5%

---

# Fine del ciclo di vita delle origini dati a elaborazione completa

Le origini dati a elaborazione completa hanno sempre consentito alle organizzazioni di inviare dati a livello di hit ad Adobe Analytics. Questi dati sono stati elaborati con le stesse modalità dei dati raccolti attraverso i metodi tradizionali di raccolta dei dati, come AppMeasurement. Nel 2020, Adobe ha rilasciato l&#39;API di inserimento dati in blocco [Bulk](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), che esegue le stesse funzioni delle origini dati a elaborazione completa, ma con funzionalità aggiuntive. Questa pagina fornisce dettagli sulle funzionalità aggiuntive fornite dall’API di inserimento dati in blocco e illustra le differenze nei formati di file.

Il 25 marzo 2021 Adobe ha impedito la creazione di nuove connessioni di origini dati a elaborazione completa. Il 31 gennaio 2022 sono stati disattivati tutti i servizi di elaborazione dati completa.

## Differenze chiave tra le origini dati a elaborazione completa e l’API di inserimento dati in blocco

* L’inserimento di dati in blocco consente di inviare più file per l’elaborazione parallela. I gruppi di visitatori garantiscono la continuità dei visitatori e l’attribuzione eVar.
* L’inserimento di dati in blocco dispone di funzionalità di convalida dei dati e gestione degli errori, che consentono di rimuovere parte del lavoro amministrativo necessario per l’invio dei dati hit.
* L’inserimento di dati in blocco supporta più metodi di identificazione degli ID visitatore.
* L&#39;inserimento di dati in blocco include alcuni campi obbligatori aggiuntivi: una colonna di identificazione del visitatore, un `pageName` (o equivalente al collegamento), `reportSuiteID`, `timestamp` e `userAgent`.
* Per garantire la continuità e l’attribuzione del visitatore, l’inserimento di dati in blocco richiede che le righe all’interno dei file siano ordinate in ordine cronologico. Consulta [Gruppi di visitatori](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) per informazioni sull&#39;ordinamento dell&#39;attività dei visitatori in più file.
* L&#39;inserimento di dati in blocco richiede che i file siano compressi con estensione csv in formato .gzip.
* BDIA utilizza `timestamp` invece di `date`.

## Confronto delle variabili tra BDIA e origini dati a elaborazione completa

Le seguenti variabili sono state introdotte nell’inserimento di dati in blocco, in precedenza non disponibili nelle origini dati a elaborazione completa:

* **`aamlh`**: hint di posizione Adobe Audience Manager.
* **`contextData.key`**: [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**: variabili del servizio ID visitatore. Include `id`, `authState` e `isMCSeed`.
* **`hints`**: [Client hint](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html) variabili. Include `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion` e `wow64`.
* **`ipaddress`**: dimensione [Indirizzo IP](/help/components/dimensions/ip-address.md).
* **`language`**: dimensione [Lingua](/help/components/dimensions/language.md).
* **`list1`** - **`list3`**: [Variabili elenco](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**: ID Experience Cloud del visitatore.
* **`tnta`**: payload di dati di destinazione utilizzato nelle integrazioni [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=it).
* **`trackingServer`**: la variabile [`trackingServer`](/help/implement/vars/config-vars/configuration-variables.md).
* **`transactionID`**: la variabile [`transactionID`](/help/implement/vars/page-vars/transactionid.md).
* **`userAgent`**: stringa agente utente del dispositivo.

Le seguenti variabili non sono supportate tramite l’inserimento di dati in blocco:

* **`charSet`**: la variabile [`charSet`](/help/implement/vars/config-vars/charset.md). L&#39;inserimento di dati in blocco supporta solo UTF-8.
* **`timezone`**: scostamento del fuso orario del visitatore da GMT in ore.
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**: variabili utilizzate nella raccolta dati di Activity Map.
