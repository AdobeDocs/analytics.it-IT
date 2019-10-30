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
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono catturati ed elaborati nel reporting. Le variabili di configurazione più comuni, solitamente impostate nel JavaScript AppMeasurement.js globale principale. Queste variabili possono essere impostate all’interno del codice a livello di pagina di Analytics e, se appropriato, dei collegamenti.

Per impostazione predefinita, non tutte queste variabili vengono visualizzate nel codice quando si genera codice tramite **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Alcune di queste variabili di configurazione potrebbero non essere applicabili alle esigenze di implementazione del sito.

Alcuni degli obiettivi di utilizzo di queste variabili di configurazione sono:

* Consente di tenere traccia di più siti/domini.
* Utilizzate qualsiasi valuta sugli acquisti.
* Acquisire dati in lingue diverse.
* Tracciamento dei collegamenti (numero di file scaricati, collegamenti a siti esterni).
* Tieni traccia dei collegamenti personalizzati per scopi unici.

> [!NOTE] [!DNL AppMeasurement] richiede che tutte le variabili di configurazione siano impostate prima della chiamata iniziale alla funzione track, `t()`. Se le variabili di configurazione sono impostate dopo la chiamata a `t()`, potrebbero verificarsi risultati imprevisti. Per garantire la corretta raccolta dei dati, tutte le variabili di configurazione devono essere al di sopra della `doPlugins` funzione.

Per informazioni su variabili di configurazione specifiche, fate clic su uno dei seguenti collegamenti:

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specifica la suite di rapporti in cui i dati vengono memorizzati e segnalati.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html): Selezionate dinamicamente la suite di rapporti in base all'URL di ogni pagina.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html): Specifica le regole utilizzate per determinare la suite di rapporti di destinazione.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html): Utilizzare l'oggetto DOM per recuperare la sezione dell'URL a cui vengono applicate tutte le regole.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html): Implementare il contrassegno per le variabili popolate in modo dinamico.

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html): Converti i dati in ingresso in UTF-8 per l'archiviazione e la creazione di report in Analytics.

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html): Determinare il tasso di conversione da applicare alle entrate.

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html): Stabilisce quale dominio sono impostati i `s_cc` cookie e `s_sq` i cookie.

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html): Determinare il dominio per `s_cc` e `s_sq` i cookie specificando il numero di punti nel dominio dell’URL della pagina.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html): Specificate i cookie impostati da JavaScript (`s_sq`, `s_cc`, plug-in) che sono intrinsecamente cookie di prime parti, anche con domini `2o7.net` `omtrdc.net` o terze parti.

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html): Determinare la durata di vita di un cookie come elaborato sia dai server JavaScript che dai server di raccolta dei dati.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html): Fare riferimento alla funzione e consentire la chiamata nella posizione appropriata all'interno del file JavaScript.

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Funzione che consente di utilizzare come parametri sia il callback (una funzione) che i parametri per la funzione.

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Funzione che consente di utilizzare come parametri sia il callback (una funzione) che i parametri per la funzione.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html): Consente di tenere traccia dei collegamenti ai file scaricabili sul sito.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html): Consente di determinare se un collegamento selezionato è un collegamento di uscita.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html): Determinare se i dati ClickMap sono raccolti.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html): Includete un elenco separato da virgole di estensioni di file.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkintfilters.html): Include un elenco di filtri separati da virgole che rappresentano i collegamenti che fanno parte del sito.

* [s.linkLeftQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html): Stabilire se la stringa di query deve essere inclusa o meno nei rapporti Exit Links e File Download.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html): Includete un elenco separato da virgole di variabili inviate con collegamenti personalizzati, di uscita e di download.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html): Utilizzare per creare rapporti su un sottoinsieme specifico di collegamenti di uscita.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html): Chiama la `s_doPlugins` funzione prima di ogni richiesta di immagine.

