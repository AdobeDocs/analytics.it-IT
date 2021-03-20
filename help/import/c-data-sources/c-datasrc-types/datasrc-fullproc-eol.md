---
title: Terminazione dell'elaborazione completa delle origini dati
description: Motivi della fine del ciclo di vita e confronti tra API di inserimento dati in blocco e Origini dati di elaborazione completa.
translation-type: tm+mt
source-git-commit: 2e077db74b7719f49aec513fc99dad33a4d5b831
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 11%

---


# Terminazione dell&#39;elaborazione completa delle origini dati

Per diversi anni, Origini dati a elaborazione completa ti ha consentito di inviare dati a livello di hit ad Adobe Analytics. Questi dati sono stati elaborati allo stesso modo dei dati raccolti tramite le nostre librerie JavaScript e l’SDK per app mobili. Nel 2020, Adobe ha rilasciato l’ [API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), che esegue le stesse funzioni di Origini dati a elaborazione completa, ma con funzioni aggiuntive. Questo argomento fornisce dettagli sulle funzionalità aggiuntive fornite dall’API di inserimento dati in blocco e illustra le differenze nei formati di file.

A partire dal 25 marzo 2021, Adobe impedirà la creazione di nuove connessioni Origini dati Elaborazione completa . Le connessioni esistenti continueranno a essere supportate fino a quando il servizio non sarà completamente obsoleto. La deprecazione avrà luogo nel 2021, anche se non è ancora stata determinata una data specifica.

## Perché terminiamo questa funzione?

L’API di inserimento dati in blocco (BDIA) fornisce funzionalità aggiuntive e copre tutti i casi d’uso supportati dalla funzione Elaborazione completa. Crediamo che sarà meglio utilizzare l’API di inserimento dati in blocco.

## Differenze chiave tra l’elaborazione completa delle origini dati e l’API di inserimento dati in blocco

* L’inserimento di dati in blocco consente l’invio di più file che possono essere elaborati in parallelo. Puoi utilizzare i gruppi di visitatori per garantire la continuità del visitatore e l’attribuzione eVar.
* L’inserimento di dati in blocco dispone di funzionalità di convalida dei dati e di gestione degli errori, rimuovendo così parte del lavoro amministrativo di invio dei dati degli hit.
* L’inserimento dati in blocco supporta diverse opzioni per gli ID visitatore. Puoi inviare sia l’ID di Analytics che l’ID di Marketing Cloud (per ulteriori informazioni, consulta [Servizio identità](https://experienceleague.adobe.com/docs/id-service/using/home.html) ). Inoltre, puoi utilizzare il tuo ID come [seed per generare un ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* L’inserimento di dati in blocco supporta le variabili di dati di elenco e di contesto.
* L’inserimento dati in blocco non supporta i dati di Activity Map.

## Differenze chiave in formato file e contenuto

* L’inserimento dati in blocco contiene alcuni campi obbligatori aggiuntivi. Per ulteriori informazioni, consulta la [documentazione](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) .
* Per garantire la continuità e l’attribuzione dei visitatori, l’inserimento di dati in blocco richiede che le righe all’interno dei file siano ordinate in ordine cronologico. Per informazioni sull&#39;ordine dell&#39;attività del visitatore tra file, consulta [Gruppi di visitatori](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) .
* L’inserimento dati in blocco richiede che i file siano compressi in formato .csv in formato .gzip.
* BDIA utilizza &quot;timestamp&quot; invece di &quot;date&quot;.

Per ulteriori dettagli, vedere il seguente confronto dei valori dei campi disponibili in BDIA (Bulk Data Insertion) e FPDS (Full Processing Data Sources).

## Confronto dei valori dei campi disponibili in BDIA e FPDS

| BDIA, FPDS, Entrambi | Variabile BDIA | Variabile colonna Elaborazione completa | Descrizione |
| --- | --- | --- | --- |
| BDIA | aamlh | Non supportati | Suggerimento sulla posizione di Adobe Audience Manager. Vedi i valori ID validi nella tabella di elenco dell&#39;area AAM seguente. |
| Entrambi | browserHeight | browserHeight | Altezza browser in pixel (ad esempio, 768) |
| Entrambi | browserWidth | browserWidth | Larghezza browser in pixel (ad esempio, 1024) |
| Entrambi | campagna | campagna | Codice di tracciamento campagna di conversione |
| Entrambi | channel | canale | Stringa canale (ad esempio, sezione Sport) |
| Entrambi | colorDepth | colorDepth | Profondità colore monitor in bit (ad esempio, 24) |
| Entrambi | connectionType | connectionType | Tipo di connessione del visitatore (LAN o modem) |
| BDIA | contextData.key | Non supportati | Le coppie chiave-valori sono specificate in denominando l’intestazione &quot;contextData.product&quot; o &quot;contextData.color&quot; |
| Entrambi | cookiesEnabled | cookiesEnabled | `Y` o  `N` se il visitatore supporta i cookie di sessione di prima parte |
| Entrambi | currencyCode | currencyCode | Codice valuta ricavi (ad esempio, `USD`) |
| BDIA | customerID.[customerIDType].authState | Non supportati | Lo stato autenticato del visitatore. I valori supportati sono: 0, 1, 2, SCONOSCIUTO, AUTENTICATO, LOGGED_OUT o &#39;&#39; (senza distinzione tra maiuscole e minuscole). Due virgolette singole consecutive (&#39;&#39;) fanno sì che il valore venga omesso dalla stringa di query, che si traduce in 0 quando viene effettuato l&#39;hit. I valori numerici authState supportati indicano quanto segue: 0 = SCONOSCIUTO, 1 = AUTENTICATO, 2 = LOGGED_OUT. Il customerIDType può essere una qualsiasi stringa alfanumerica, ma deve essere considerato sensibile a maiuscole e minuscole. |
| BDIA | customerID.[customerIDType].id | Non supportati | ID cliente da utilizzare. Il customerIDType può essere una qualsiasi stringa alfanumerica, ma deve essere considerato sensibile a maiuscole e minuscole. |
| BDIA | customerID.[customerIDType].isMCSeed | Non supportati | Indica se si tratta o meno del valore di seed per l’ID visitatore Marketing Cloud. I valori supportati sono: 0, 1, TRUE, FALSE, &#39;&#39; (senza distinzione tra maiuscole e minuscole). Se si utilizzano 0, FALSE o due virgolette singole consecutive (&#39;), il valore viene omesso dalla stringa di query. Il customerIDType può essere una qualsiasi stringa alfanumerica, ma deve essere considerato sensibile a maiuscole e minuscole. |
