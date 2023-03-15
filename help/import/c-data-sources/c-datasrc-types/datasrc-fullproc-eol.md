---
title: Fine del ciclo di vita per le origini dati a elaborazione completa
description: Motivi della fine del ciclo di vita e confronti tra API di inserimento dati in blocco e origini dati a elaborazione completa.
feature: Data Sources
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 28%

---

# Fine del ciclo di vita per le origini dati a elaborazione completa

Per diversi anni, Origini dati a elaborazione completa ti ha consentito di inviare dati a livello di hit ad Adobe Analytics. Questi dati sono stati elaborati con le stesse modalità dei dati raccolti tramite le nostre librerie JavaScript e l’SDK per app mobile. Nel 2020, Adobe ha rilasciato il [API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), che esegue le stesse funzioni di Origini dati a elaborazione completa, ma con funzioni aggiuntive. Questo argomento fornisce dettagli sulle funzionalità aggiuntive fornite dall’API di inserimento dati in blocco e illustra le differenze nei formati di file.

A partire dal 25 marzo 2021, Adobe ha impedito la creazione di nuove connessioni Origini dati a elaborazione completa. Le connessioni esistenti sono state supportate fino a quando il servizio non è stato completamente dichiarato obsoleto il 31 gennaio 2022. Oltre alla documentazione standard, forniamo una descrizione dettagliata del [passaggi necessari per inviare dati tramite API di inserimento dati in blocco](https://adobe.ly/aabdia).

## Perché abbiamo terminato questa funzione?

L’API di inserimento dati in blocco (BDIA) fornisce funzionalità aggiuntive, coprendo allo stesso tempo tutti i casi d’uso supportati dall’Elaborazione completa. Puoi sfruttare al meglio l’API di inserimento dati in blocco.

## Differenze chiave tra origini dati a elaborazione completa e API di inserimento dati in blocco

* L’inserimento di dati in blocco consente l’invio di più file che possono essere elaborati in parallelo. Puoi utilizzare i gruppi di visitatori per garantire la continuità dei visitatori e l’attribuzione eVar.
* L’inserimento di dati in blocco dispone di funzionalità di convalida dei dati e di gestione degli errori, in modo da rimuovere parte del lavoro amministrativo necessario per l’invio dei dati hit.
* L’inserimento di dati in blocco supporta diverse opzioni per gli ID visitatore. Puoi inviare sia l’ID Analytics che l’ID Marketing Cloud (consulta [Servizio identità](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) per ulteriori informazioni). Inoltre, puoi utilizzare un tuo ID come [seed per la generazione di un ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* L’inserimento di dati in blocco supporta le variabili di dati di elenco e contestuali.
* L’inserimento di dati in blocco non supporta i dati Activity Map.

## Differenze chiave nel formato dei file e nel contenuto

* Nell’inserimento di dati in blocco sono presenti alcuni campi obbligatori aggiuntivi. Consulta la [documentazione](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) per i dettagli.
* Per garantire la continuità e l’attribuzione del visitatore, l’inserimento di dati in blocco richiede che le righe all’interno dei file siano ordinate in ordine cronologico. Consulta [Gruppi di visitatori](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) per informazioni sull’ordine in cui l’attività Visitatore viene ordinata tra i file.
* L’inserimento di dati in blocco richiede che i file siano compressi con estensione csv in formato .gzip.
* BDIA utilizza &quot;timestamp&quot; invece di &quot;date&quot;.

Per ulteriori dettagli, consulta il seguente confronto dei valori dei campi disponibili in Bulk Data Insertion (BDIA) e Full Processing Data Sources (FPDS).

## Confronto dei valori di campo disponibili in BDIA e FPDS

| Variabile BDIA | Variabile colonna Elaborazione completa | Descrizione |
| --- | --- | --- |
| aamlh | Non supportati | hint di posizione Adobe Audience Manager. |
| browserHeight | browserHeight | Altezza browser in pixel (ad esempio, 768) |
| browserWidth | browserWidth | Larghezza browser in pixel (ad esempio, 1024) |
| campaign | campaign | Codice di tracciamento della campagna di conversione |
| channel | channel | Stringa canale (ad esempio, sezione Sport) |
| colorDepth | colorDepth | Profondità colore monitor in bit (ad esempio, 24) |
| connectionType | connectionType | Tipo di connessione del visitatore (LAN o modem) |
| contextData.key | Non supportati | Le coppie chiave-valori vengono specificate in denominando l’intestazione &quot;contextData.product&quot; o &quot;contextData.color&quot; |
| cookiesEnabled | cookiesEnabled | `Y` o `N` per se il visitatore supporta i cookie di sessione di prime parti |
| currencyCode | currencyCode | Codice valuta ricavi (ad esempio, `USD`) |
| customerID.[customerIDType].authState | Non supportati | Stato di autenticazione del visitatore. I valori supportati sono: 0, 1, 2, UNKNOWN, AUTHENTICATED, LOGGED_OUT o &quot;&quot; (senza distinzione maiuscole/minuscole). Due virgolette singole consecutive (&#39;&#39;) causano l’omissione del valore dalla stringa di query, che si traduce in 0 quando viene eseguito l’hit. I valori numerici authState supportati indicano quanto segue: 0 = SCONOSCIUTO, 1 = AUTENTICATO, 2 = LOGGED_OUT. Il tipo customerIDT può essere qualsiasi stringa alfanumerica, ma deve essere considerato sensibile a maiuscole e minuscole. |
| customerID.[customerIDType].id | Non supportati | ID cliente da utilizzare. Il tipo customerIDT può essere qualsiasi stringa alfanumerica, ma deve essere considerato sensibile a maiuscole e minuscole. |
| customerID.[customerIDType].isMCSeed | Non supportati | Se si tratta o meno del valore di partenza per l’ID visitatore del Marketing Cloud. I valori supportati sono: 0, 1, TRUE, FALSE, &#39;&#39; (senza distinzione maiuscole/minuscole). Se si utilizza 0, FALSE o due virgolette singole consecutive (&#39;&#39;), il valore viene omesso dalla stringa di query. Il tipo customerIDT può essere qualsiasi stringa alfanumerica, ma deve essere considerato sensibile a maiuscole e minuscole. |
| eVarN | eVarN, ovvero `<eVar2>`...`<eVar>` | Nome eVar conversione. Puoi avere fino a 75 eVar ( eVar 1 - eVar 75 ) Puoi specificare il nome dell’eVar (eVar 12) o un nome descrittivo (Ad Campaign 3). |
| events | events | [Stringa eventi](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html#vars), formattato con la stessa sintassi della variabile s.events. Ad esempio: scAdd,event1,event7 |
| hierN | hierN, ovvero `<hier2>`...`</hier2>` | Nome gerarchia. Puoi avere fino a 5 gerarchie ( hier1 - hier5 ). È possibile specificare il nome della gerarchia predefinita `hier2` o un nome descrittivo (Yankees). |
| homePage | homePage | S o N se la pagina corrente è la pagina iniziale del visitatore. |
| indirizzo IP | Non supportati | Indirizzo IP del visitatore. |
| javaEnabled | javaEnabled | S o N se il visitatore ha abilitato Java. |
| javaScriptVersion | javaScriptVersion | Versione JavaScript (ad esempio, 1.3). |
| lingua | Non supportati | Lingua supportata del browser. Esempio: `en-us`. |
| linkName | linkName | Nome del collegamento. |
| linkType | linkType | Tipo di collegamento. I valori supportati includono: `d: Download link`, `e: Exit link`, `o: Custom link`. |
| linkURL | linkURL | HREF del collegamento. |
| list Ad esempio, list2. | Non supportati | Un elenco delimitato di valori che vengono passati in una variabile e quindi segnalati come singole voci di riga per il reporting |
| marketingCloudVisitorID | Non supportati | Marketing Cloud ID. Consulta [Identificazione visitatore](https://experienceleague.adobe.com/docs/id-service/using/home.html#id-service-api) e il servizio ID visitatore del Marketing Cloud |
| Non supportati | charSet | Il set di caratteri supportato per il sito Web. Ad esempio, UTF-8, ISO-8859-1 e così via. |
| Non supportati | clickAction | Identificatore oggetto per mappa clic visitatore (oid). |
| Non supportati | clickActionType | Identificatore oggetto per mappa clic visitatore (oidt). |
| Non supportati | clickContext | Identificatore pagina per mappa clic visitatore (pid). |
| Non supportati | clickContextType | Identificatore pagina per mappa clic visitatore (pidt). |
| Non supportati | clickSourceID | Indice origine per mappa clic visitatore (oi). |
| Non supportati | clickTag | Nome tag oggetto per mappa clic visitatore (ot). |
| Non supportati | scXmlVer | Numero versione richiesta XML rapporti di marketing (ad esempio 1.0). |
| Non supportati | timezone | Offset fuso orario del visitatore da GMT in ore (ad esempio, -8). |
| pageName | pageName | Nome della pagina |
| pageType | pageType | Tipo di pagina (ad esempio, &quot;Pagina di errore&quot;). |
| pageURL | pageURL | URL della pagina (ad esempio, https://www.example.com/index.html). |
| plugins | plugins | Elenco separato da punto e virgola dei nomi dei plug-in del browser. |
| products | products | Elenco di tutti i prodotti sulla pagina. Separa i prodotti con una virgola. Ad esempio: Sport;Ball;1;5.95,Giocattoli; Top;1:1.99. |
| prop1 - prop75 | propN, ovvero `<prop2>`...`</prop2>` | Stringa Property# (ad esempio, Sports Section). |
| propN | propN | Valori proprietà per le proprietà. |
| purchaseID | purchaseID | Numero ID acquisto. |
| referrer | referrer | URL per referente pagina. |
| reportSuiteID | s_account | Specifica le suite di rapporti in cui desideri inviare i dati. Devi separare più ID suite di rapporti con una virgola. |
| resolution | resolution | Risoluzione del monitor (ad esempio, 1024x768). |
| server | server | Stringa Server. |
| state | state | Stringa Stato di conversione. |
| timestamp | data | Utilizza il formato data ISO 8601 AAAA-MM-DDThh:mm:ss±UTC_offset (ad esempio, 2021-09-01T12:00:00-07:00 ), o Unix Time Format (il numero di secondi trascorsi dal 1 gennaio 1970). |
| trackingServer | Non supportati | Può essere fornito solo tramite intestazione di colonna. |
| transactionID | Non supportati | Valore comune utilizzato per collegare tra loro le attività utente multicanale a scopo di reporting. Per ulteriori informazioni, vedere [Guida utente di Origini dati](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html#data-sources). |
| userAgent | Non supportati | Stringa agente utente |
| visitorID | visitorID | ID Analytics del visitatore. Consulta [Identificazione visitatore](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). |
| zip | zip | Codice zip di conversione. |
