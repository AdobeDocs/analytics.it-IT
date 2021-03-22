---
title: Terminazione dell'elaborazione completa delle origini dati
description: Motivi della fine del ciclo di vita e confronti tra API di inserimento dati in blocco e Origini dati di elaborazione completa.
translation-type: tm+mt
source-git-commit: 97e60e4c3a593405f92f47e5aa79ece70e0b3d60
workflow-type: tm+mt
source-wordcount: '1221'
ht-degree: 27%

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

| Variabile BDIA | Variabile colonna Elaborazione completa | Descrizione |
| --- | --- | --- |
| aamlh | Non supportati | Suggerimento sulla posizione di Adobe Audience Manager. |
| browserHeight | browserHeight | Altezza browser in pixel (ad esempio, 768) |
| browserWidth | browserWidth | Larghezza browser in pixel (ad esempio, 1024) |
| campagna | campagna | Codice di tracciamento campagna di conversione |
| channel | canale | Stringa canale (ad esempio, sezione Sport) |
| colorDepth | colorDepth | Profondità colore monitor in bit (ad esempio, 24) |
| connectionType | connectionType | Tipo di connessione del visitatore (LAN o modem) |
| contextData.key | Non supportati | Le coppie chiave-valori sono specificate in denominando l’intestazione &quot;contextData.product&quot; o &quot;contextData.color&quot; |
| cookiesEnabled | cookiesEnabled | `Y` o  `N` se il visitatore supporta i cookie di sessione di prima parte |
| currencyCode | currencyCode | Codice valuta ricavi (ad esempio, `USD`) |
| customerID.[customerIDType].authState | Non supportati | Lo stato autenticato del visitatore. I valori supportati sono: 0, 1, 2, SCONOSCIUTO, AUTENTICATO, LOGGED_OUT o &#39;&#39; (senza distinzione tra maiuscole e minuscole). Due virgolette singole consecutive (&#39;&#39;) fanno sì che il valore venga omesso dalla stringa di query, che si traduce in 0 quando viene effettuato l&#39;hit. I valori numerici authState supportati indicano quanto segue: 0 = SCONOSCIUTO, 1 = AUTENTICATO, 2 = LOGGED_OUT. Il customerIDType può essere una qualsiasi stringa alfanumerica, ma deve essere considerato sensibile a maiuscole e minuscole. |
| customerID.[customerIDType].id | Non supportati | ID cliente da utilizzare. Il customerIDType può essere una qualsiasi stringa alfanumerica, ma deve essere considerato sensibile a maiuscole e minuscole. |
| customerID.[customerIDType].isMCSeed | Non supportati | Indica se si tratta o meno del valore di seed per l’ID visitatore Marketing Cloud. I valori supportati sono: 0, 1, TRUE, FALSE, &#39;&#39; (senza distinzione tra maiuscole e minuscole). Se si utilizzano 0, FALSE o due virgolette singole consecutive (&#39;), il valore viene omesso dalla stringa di query. Il customerIDType può essere una qualsiasi stringa alfanumerica, ma deve essere considerato sensibile a maiuscole e minuscole. |
| eVarN | eVarN, cioè `<eVar2>`..`<eVar>` | Nome eVar conversione. Puoi avere fino a 75 eVar ( eVar1 - eVar75 ) Puoi specificare il nome dell’eVar (eVar12) o un nome descrittivo (Ad Campaign 3). |
| events | events | [Stringa](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars) Eventi, formattata utilizzando la stessa sintassi della variabile s.events . Ad esempio: scAdd,event1,event7 |
| hierN | hierN, cioè `<hier2>`..`</hier2>` | Nome gerarchia. Puoi avere fino a 5 gerarchie ( hier1 - hier5 ). È possibile specificare il nome predefinito della gerarchia `hier2` o un nome descrittivo (Yankees). |
| homePage | homePage | S o N se la pagina corrente è la pagina iniziale del visitatore. |
| indirizzo IP | Non supportati | L’indirizzo IP del visitatore. |
| javaEnabled | javaEnabled | S o N se il visitatore ha abilitato Java. |
| javaScriptVersion | javaScriptVersion | Versione JavaScript (ad esempio, 1.3). |
| lingua | Non supportati | Lingua supportata dal browser. Ad esempio, `en-us`. |
| linkName | linkName | Nome del collegamento. |
| linkType | linkType | Tipo di collegamento. I valori supportati includono: `d: Download link`, `e: Exit link`, `o: Custom link`. |
| linkURL | linkURL | HREF del collegamento. |
| Ad esempio, list2. | Non supportati | Un elenco delimitato di valori che vengono passati in una variabile e quindi segnalati come voci di riga individuali ai fini del reporting. |
| marketingCloudVisitorID | Non supportati | Marketing Cloud ID. Consulta [Identificazione visitatore](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api) e il servizio ID visitatore del Marketing Cloud. |
| Non supportati | charSet | Il set di caratteri supportato per il sito Web. Ad esempio, UTF-8, ISO-8859-1 e così via. |
| Non supportati | clickAction | Identificatore oggetto per mappa clic visitatore (oid). |
| Non supportati | clickActionType | Identificatore oggetto per mappa clic visitatore (oidt). |
| Non supportati | clickContext | Identificatore pagina per mappa clic visitatore (pid). |
| Non supportati | clickContextType | Identificatore pagina per mappa clic visitatore (pidt). |
| Non supportati | clickSourceID | Indice origine per mappa clic visitatore (oi). |
| Non supportati | clickTag | Nome tag oggetto per mappa clic visitatore (ot). |
| Non supportati | scXmlVer | Numero versione richiesta XML rapporti di marketing (ad esempio 1.0). |
| Non supportati | timezone | Offset fuso orario del visitatore da GMT in ore (ad esempio, -8). |
| pageName | pageName | Nome della pagina. |
| pageType | pageType | Tipo di pagina (ad esempio, &quot;Pagina di errore&quot;). |
| pageURL | pageURL | URL della pagina (ad esempio, https://www.example.com/index.html). |
| plugins | plugins | Elenco separato da punto e virgola dei nomi dei plug-in del browser. |
| products | products | Elenco di tutti i prodotti nella pagina. Separa i prodotti con una virgola. Ad esempio: Sport;Palla;1;5.95,Giocattoli; Top;1:1.99. |
| prop1 - prop75 | propN, cioè `<prop2>`..`</prop2>` | Stringa Property# (ad esempio, sezione Sport). |
| propN | propN | Valori proprietà per le proprietà. |
| purchaseID | purchaseID | Numero ID acquisto. |
| referrer | referrer | URL per referente pagina. |
| reportSuiteID | s_account | Specifica le suite di rapporti in cui si desidera inviare i dati. Separa più ID suite di rapporti con una virgola. |
| resolution | resolution | Risoluzione del monitor (ad esempio, 1024x768). |
| server | server | Stringa Server. |
| stato | stato | Stringa Stato di conversione. |
| timestamp | data | Utilizzare il formato di data ISO 8601 di AAAA-MM-DDThh:mm:ss±UTC_offset (ad esempio, 2021-09-01T12:00:00-07:00 ) o Unix Time Format (il numero di secondi trascorsi dal 1° gennaio 1970). |
| trackingServer | Non supportati | Può essere fornito solo tramite intestazione di colonna. |
| transactionID | Non supportati | Valore comune utilizzato per collegare le attività utente multicanale insieme a scopo di reporting. Per ulteriori informazioni, consulta la [Guida utente di Origini dati](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources). |
| userAgent | Non supportati | Stringa agente utente |
| visitorID | visitorID | ID Analytics del visitatore. Consulta [Identificazione visitatore](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| zip | zip | Codice zip di conversione. |
