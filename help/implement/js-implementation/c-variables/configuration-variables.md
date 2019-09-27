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
source-git-commit: a340bb50ec437db64dafaddc0b20aec740aee299

---


# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono catturati ed elaborati nel reporting. The most-common configuration variables that are typically set in the main global JavaScript AppMeasurement.js). Queste variabili possono essere impostate all’interno del codice a livello di pagina di Analytics e, se appropriato, dei collegamenti.

Per impostazione predefinita, non tutte queste variabili vengono visualizzate nel codice quando si genera codice tramite **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Some of these configuration variables may not be applicable to your site's implementation needs.

Alcuni degli obiettivi di utilizzo di queste variabili di configurazione sono:

* Track multiple sites/domains.
* Use any currency on purchases.
* Capture data indifferent languages.
* Tracciamento dei collegamenti (numero di file scaricati, collegamenti a siti esterni).
* Tieni traccia dei collegamenti personalizzati per scopi unici.

>[!NOTE]
>
>[!DNL AppMeasurement] richiede che tutte le variabili di configurazione siano impostate prima della chiamata iniziale alla funzione track, `t()`. Se le variabili di configurazione sono impostate dopo la chiamata a `t()`, potrebbero verificarsi risultati imprevisti. Per garantire la corretta raccolta dei dati, tutte le variabili di configurazione devono essere al di sopra della `doPlugins` funzione.

Per informazioni su variabili di configurazione specifiche, fate clic su uno dei seguenti collegamenti:

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specifica la suite di rapporti in cui i dati vengono memorizzati e segnalati.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html): Selezionate dinamicamente la suite di rapporti in base all'URL di ogni pagina.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html): Specifica le regole utilizzate per determinare la suite di rapporti di destinazione.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html): Utilizzare l'oggetto DOM per recuperare la sezione dell'URL a cui vengono applicate tutte le regole.

* [s.dynamicVariablePrefix: Deploy flagging for dynamically-populated variables.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html)

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html): Converti i dati in ingresso in UTF-8 per l'archiviazione e la creazione di report in Analytics.

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html): Determinare il tasso di conversione da applicare alle entrate.

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html): Stabilisce quale dominio sono impostati i `s_cc` cookie e `s_sq` i cookie.

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html): Determinare il dominio per `s_cc` e `s_sq` i cookie specificando il numero di punti nel dominio dell’URL della pagina.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html): Specificate i cookie impostati da JavaScript (`s_sq`, `s_cc`, plug-in) che sono intrinsecamente cookie di prime parti, anche con domini `2o7.net` `omtrdc.net` o terze parti.

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html): Determinare la durata di vita di un cookie come elaborato sia dai server JavaScript che dai server di raccolta dei dati.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html): Refer and allow the function to be called at the appropriate location within the JavaScript file.

* [s.registerPreTrackCallback: Function for taking as parameters both the callback (a function), and the parameters to that function.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html)

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Function for taking as parameters both the callback (a function), and the parameters to that function.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html): Consente di tenere traccia dei collegamenti ai file scaricabili sul sito.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html): Consente di determinare se un collegamento selezionato è un collegamento di uscita.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html): Determinare se i dati ClickMap sono raccolti.

* [s.linkDownloadFileTypes: Include a comma-separated list of file extensions.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html)

* [s.linkInternalFilters: Includes a comma-separated list of filters that represent the links that are part of the site.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkintfilters.html)

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html): Determine whether or not the query string should be included in the Exit Links and File Download reports.

* [s.linkTrackVars: Include a comma-separated list of variables that are sent with custom, exit, and download links.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)

* [s.linkExternalFilters: Use to report on a specific subset of exit links.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html)

* [s.usePlugins: Call the  function prior to each image request.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html)`s_doPlugins`

