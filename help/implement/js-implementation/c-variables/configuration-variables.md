---
description: Variabili di configurazione impostate in AppMeasurement.js.
keywords: Implementazione di Analytics
seo-description: Variabili di configurazione impostate in AppMeasurement.js per Adobe Analytics
seo-title: Variabili di configurazione
solution: Analytics
subtopic: Variabili
title: Variabili di configurazione
topic: Sviluppatore e implementazione
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 9212d70ab8fd7bc0ccfb7e781a92b1731f0a40bd

---


# Configuration variables overview

Configuration variables control the way data is captured and processed in reporting. Le variabili di configurazione più comuni, solitamente impostate nel JavaScript AppMeasurement.js globale principale. These variables can be set within the Analytics page-level code and links when appropriate.

Not all of these variables appear in the code by default when you generate code through the  &gt; . **[!UICONTROL Admin Tool]****[!UICONTROL Code Manager]** Some of these configuration variables may not be applicable to your site's implementation needs.

Some of the goals of using these configuration variables are:

* Consente di tenere traccia di più siti/domini.
* Use any currency on purchases.
* Capture data indifferent languages.
* Tracciamento dei collegamenti (numero di file scaricati, collegamenti a siti esterni).
* Tieni traccia dei collegamenti personalizzati per scopi unici.

>[!NOTE]
>
>[!DNL AppMeasurement] richiede che tutte le variabili di configurazione siano impostate prima della chiamata iniziale alla funzione track, `t()`. Se le variabili di configurazione sono impostate dopo la chiamata a `t()`, potrebbero verificarsi risultati imprevisti. Per garantire la corretta raccolta dei dati, tutte le variabili di configurazione devono essere al di sopra della `doPlugins` funzione.

Per informazioni su variabili di configurazione specifiche, fate clic su uno dei seguenti collegamenti:

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specifica la suite di rapporti in cui i dati vengono memorizzati e segnalati.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Selezionate dinamicamente la suite di rapporti in base all'URL di ogni pagina.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specifica le regole utilizzate per determinare la suite di rapporti di destinazione.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Utilizzare l'oggetto DOM per recuperare la sezione dell'URL a cui vengono applicate tutte le regole.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Implementare il contrassegno per le variabili popolate in modo dinamico.

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Converti i dati in ingresso in UTF-8 per l'archiviazione e la creazione di report in Analytics.

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determinare il tasso di conversione da applicare alle entrate.

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Stabilisce quale dominio sono impostati i `s_cc` cookie e `s_sq` i cookie.

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determinare il dominio per `s_cc` e `s_sq` i cookie specificando il numero di punti nel dominio dell’URL della pagina.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specificate i cookie impostati da JavaScript (`s_sq`, `s_cc`, plug-in) che sono intrinsecamente cookie di prime parti, anche con domini `2o7.net` `omtrdc.net` o terze parti.

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determinare la durata di vita di un cookie come elaborato sia dai server JavaScript che dai server di raccolta dei dati.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Fare riferimento alla funzione e consentire la chiamata nella posizione appropriata all'interno del file JavaScript.

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Funzione che consente di utilizzare come parametri sia il callback (una funzione) che i parametri per la funzione.

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Funzione che consente di utilizzare come parametri sia il callback (una funzione) che i parametri per la funzione.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Track links to downloadable files on your site.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Consente di determinare se un collegamento selezionato è un collegamento di uscita.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determinare se i dati ClickMap sono raccolti.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Includete un elenco separato da virgole di estensioni di file.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Include un elenco di filtri separati da virgole che rappresentano i collegamenti che fanno parte del sito.

* [s.linkLeftQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Stabilire se la stringa di query deve essere inclusa o meno nei rapporti Exit Links e File Download.

* [s.linkTrackVars: Include a comma-separated list of variables that are sent with custom, exit, and download links.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.linkExternalFilters: Use to report on a specific subset of exit links.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.usePlugins: Call the  function prior to each image request.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)`s_doPlugins`

