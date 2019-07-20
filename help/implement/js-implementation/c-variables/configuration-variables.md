---
description: Variabili di configurazione impostate in appmeasurement. js.
keywords: Implementazione di Analytics
seo-description: Variabili di configurazione impostate in appmeasurement. js per Adobe Analytics
seo-title: Variabili di configurazione
solution: Analytics
subtopic: Variabili
title: Variabili di configurazione
topic: Sviluppatore e implementazione
uuid: a 19484 b 6-e 350-4 c 12-b 4 d 6-a 31 c 79 a 42 db 0
translation-type: tm+mt
source-git-commit: 696e7ed6dc6648cf523bc81e6cd40c7a06115484

---


# Variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono acquisiti ed elaborati nei report. Le variabili di configurazione più comuni impostate in genere nel javascript appmeasurement. js principale. Queste variabili possono essere impostate nel codice a livello di pagina di Analytics e nei collegamenti quando appropriato.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Alcune di queste variabili di configurazione potrebbero non essere applicabili alle esigenze di implementazione del sito.

Alcuni degli obiettivi di queste variabili di configurazione sono:

* Tenere traccia di più siti/domini.
* Utilizzate qualsiasi valuta per gli acquisti.
* Acquisire dati indifferenti.
* Tracciamento dei collegamenti (numero di file scaricati, collegamenti a siti esterni).
* Tieni traccia dei collegamenti personalizzati a scopi univoci.

>[!NOTE]
>
>[!DNL AppMeasurement] richiede che tutte le variabili di configurazione siano impostate prima della chiamata iniziale alla funzione di tracciamento. `t()` If configuration variables are set after the call to `t()`, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

## s.account {#concept_685A5C832A6C40619ACB5920925785DC}

<!--
s_account.xml
-->

La variabile determina la suite di rapporti in cui i dati vengono memorizzati e segnalati.

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. L'ID suite di rapporti è determinato da Adobe.

**Parametri**

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| 40 Byte | Nel percorso URL | N/D | N/D |

Each report suite ID must match the value created in the [!DNL Admin Console]. Ogni ID suite di rapporti deve essere di almeno 40 byte, ma l'aggregazione di tutte le suite di rapporti (l'elenco separato da virgole) non ha alcun limite.

La suite di rapporti è il livello fondamentale di segmentazione nei report. Puoi impostare tutte le suite di rapporti come il tuo contratto. Ogni suite di rapporti fa riferimento a un set dedicato di tabelle popolate nei server di raccolta di Adobe. A report suite is identified by the `s_account` variable in your JavaScript code.

Within [!DNL Analytics], the site drop-down box in the upper left of the reports displays the current report suite. Ogni suite di rapporti ha un identificatore univoco denominato ID suite di rapporti. The `s_account` variable contains one or more report suite IDs to which data is sent. The report suite ID value, which is invisible to [!DNL Analytics] users, must be provided or approved by Adobe before you use it. Every report suite ID has an associated "friendly name" that can be changed in the report suites section of the [!DNL Admin Console].

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). You can declare the `s_account` variable on the HTML page, which is a common practice when the value of `s_account` may change from page to page. Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of `s_account` also appears in the domain, before 112.2o7.net. Il valore nel percorso è l'unico valore che determina la suite di rapporti di destinazione. Il testo grassetto di seguito mostra le suite di rapporti a cui vengono inviati i dati, così come appaiono nel debugger. See [DigitalPulse Debugger](../../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

**Sintassi e valori possibili**{#section_3BE913DF26D848AEB4CB5B0A6CE7F0CA}

L'ID suite di rapporti è una stringa alfanumerica di caratteri ASCII, con lunghezza non superiore a 40 byte. L'unico carattere non alfanumerico consentito è il trattino. Spazi, punti, virgole e altri punteggiatura non sono consentiti. The `s_account` variable may contain multiple report suites, all of which receive data from that page.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

All values of `s_account` must be provided or approved by Adobe.

**Esempi** {#section_16580A9101B64560A58C7745397FB42F}

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

**Configurazione della variabile in Analytics**{#section_7DFB2CCF02F045AFB1AD4F376638393B}

The friendly name associated with each report suite ID can be changed by Adobe [!DNL Customer Care]. The friendly name can be seen in [!DNL Analytics] in the site drop-down box in the top, left section of the screen.

**Insidie, domande e suggerimenti**{#section_BFFDA5C0AF31442494B0E02F0925CF93}

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. Use the [!DNL DigitalPulse Debugger] to determine the destination report suite(s).

* In some cases, [!DNL VISTA] can be used to alter the destination report suite. Using [!DNL VISTA] to re-route or copy the data to another report suite is recommended when using first-party cookies, or if your site has more than 20 active report suites.

* Always declare `s_account` inside the JS file or just before it is included.

## s.dynamicAccountSelection {#concept_FAD499DB357148DB8BD74F08093D3E35}

La variabile consente di selezionare in modo dinamico la suite di rapporti in base all'URL di ciascuna pagina.

>[!NOTE]
>
>`dynamicAccountSelection` non funziona con il tracciamento personalizzato dei collegamenti.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | False |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

**Sintassi e valori possibili**{#section_36E5D0E2170345F5A652B44CE85DFED1}

```js
s.dynamicAccountSelection=[true|false]
```

Only 'true' and 'false' are allowed as values of *`dynamicAccountSelection`*.

**Esempi** {#section_E8CE8BA62C7545889531495E2521663D}

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

**Impostazioni di configurazione**{#section_F052FA38144B4F84B015A263A8E711CF}

Nessuno

**Insidie, domande e suggerimenti**{#section_62F0B0895BC84A05840AEEED0643DE60}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Always use the [!DNL DigitalPulse Debugger] to determine which report suite is receiving data from each page.

## s.dynamicAccountList {#concept_19715BA0AD4D41748E0C4A4A6B71AB51}

<!-- 
dynamicAccountList.xml
-->

[!DNL AppMeasurement] per javascript è possibile selezionare in modo dinamico una suite di rapporti in cui invia dati. La variabile contiene le regole utilizzate per determinare la suite di rapporti di destinazione.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | "" |

This variable is used in conjunction with the *`dynamicAccountSelection`* and *`dynamicAccountMatch`* variables. The rules in *`dynamicAccountList`* are applied if *`dynamicAccountSelection`* is set to 'true,' and they apply to the section of the URL specified in *`dynamicAccountMatch`*.

If none of the rules in *`dynamicAccountList`* matches the URL of the page, the report suite identified in `s_account` is used. Le regole elencate in questa variabile vengono applicate in ordine da sinistra a destra. Se l'URL della pagina corrisponde più di una regola, per determinare la suite di rapporti viene utilizzata la regola più a sinistra. Di conseguenza, le regole più generiche devono essere spostate a destra dell'elenco.

In the following examples, the page URL is `www.mycompany.com/path1/?prod_id=12345` and `dynamicAccountSelection` is set to *true* and `s_account` is set to `mysuitecom.`

| Dynamicaccountlist Value | Dynamicaccountmatch Value | Suite di rapporti per ricevere dati |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window. location. host | mysuite1 |
| " mysuite 1 = path 4, path 1; mysuite 2 = path 2 " | window. location. pathname | mysuite 1, mysuite 2 |
| " mysuite 1 = path 5 " | window. location. pathname | mysuitecom, mysuite 1 |
| " myprodsuite = prod_ id " | window. location. search? window. location. search: "? ") | myprodsuite |

**Sintassi e valori possibili**{#section_7360E4354ED345E8BAAE210DBD58A7EC}

The `dynamicAccountList` variable is a semicolon-separated list of name=value pairs (rules). Ogni parte dell'elenco deve contenere i seguenti elementi:

* uno o più ID suite di rapporti (separati da virgole)
* un segno uguale a
* uno o più filtri URL (separati da virgole)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

Nella stringa (nessuna spaziatura) devono essere utilizzati solo caratteri ASCII standard.

**Esempi** {#section_49936D14EF6D45859B666C9E7A4CBA9E}

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

**Impostazioni di configurazione**{#section_9F99CD741BC7449B8CCC108094B2EB85}

Nessuno

**Insidie, domande e suggerimenti**{#section_3E10534FCC05457AB67147BB480C8BB3}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Se l'URL della pagina corrisponde a più regole, viene utilizzata la regola più vuota a sinistra.
* Se nessuna regola corrisponde, viene utilizzata la suite di rapporti predefinita.
* Se la pagina viene salvata sul disco rigido di un utente o viene convertita tramite un motore di traduzione basato sul Web (come le pagine tradotte di Google), la selezione dell'account dinamico potrebbe non funzionare. For more precise tracking, populate the `s_account` variable server-side.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* When using dynamic account selection, be sure to update *`dynamicAccountList`* every time you obtain a new domain.
* Use the [!DNL DigitalPulse Debugger] when trying to identify the destination report suite. `dynamicAccountSelection` La variabile sostituisce sempre il valore di `s_account`.

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

<!-- 
dynamicAccountMatch.xml
-->

La variabile utilizza l'oggetto DOM per recuperare la sezione dell'URL a cui tutte le regole sono applicate.

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Since the default value is [!DNL window.location.host], this variable is not required for [!UICONTROL Dynamic Account Selection] to work. For additional information, see [dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51).

The rules found in `dynamicAccountList` are applied to the value of `dynamicAccountMatch`. If `dynamicAccountMatch` only contains [!DNL window.location.host] (default), the rules in `dynamicAccountList` apply only to the domain of the page.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | window. location. host |

**Sintassi e valori possibili**{#section_95CD81972C22419B80A921CA137D3841}

The `dynamicAccountMatch` variable is usually populated by the Adobe consultant who provides the AppMeasurement for JavaScript file. Tuttavia, i valori elencati di seguito possono essere applicati in qualsiasi momento.

```js
s.dynamicAccountMatch=[DOM object]
```

| Descrizione | Valore |
|---|---|
| Domain (predefinito) | window. location. host |
| Percorso | window. location. pathname |
| Stringa di query | (window. location. search? window. location. search: "? ") |
| Dominio e percorso | window. location. host + window. location. pathname |
| Percorso e stringa query | window. location. pathname + (window. location. search? window. location. search: "? ") |
| URL completo | window. location. href |

**Esempi** {#section_924687CCE255421AA2223A3D4B8B6A30}

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

**Impostazioni di configurazione**{#**section_43BCE13B1ADD4D418DF7CBB9DD7A6472}

Nessuno

**Insidie, domande e suggerimenti**{#section_EF9B2977BC21497D8C5EEB9BAD731E17}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* When pages are saved to a hard drive, [!DNL window.location.host] is empty, causing those page views to be sent to the default report suite (in `s_account`).

* When a page is translated via a web-based translation engine, such as Google, the [!UICONTROL Dynamic Account Selection] does not work as designed. For more precise tracking, populate the [!UICONTROL s_account]variable server-side.

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

<!-- 
dynamicVariablePrefix.xml
-->

La variabile consente la distribuzione delle variabili, che devono essere popolate in modo dinamico.

I cookie, le intestazioni della richiesta e i parametri delle stringhe di query immagine sono disponibili per essere inseriti in modo dinamico.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | D= | Any | D= |

**Sintassi e valori possibili**{#section_D0669899567F46B6A081C7661362BA81}

```js
s.prop1="D=User-Agent”
```

OPPURE USA FLAG PERSONALIZZATO PER VARIABILI DINAMICHE

```js
s.dynamicVariablePrefix=".."
```

**Esempi** {#section_DD148560F9E8416EBCF159194FA427AC}

```js
s.prop1="D=User-Agent”
```

OPPURE USA FLAG PERSONALIZZATO PER VARIABILI DINAMICHE

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

**Insidie, domande e suggerimenti**{#section_6889908FBD78488D955F67DDB17617B1}

* Le variabili dinamiche possono essere utilizzate per ridurre notevolmente la lunghezza totale dell'URL copiando i valori in altre variabili.
* Le variabili dinamiche possono essere utilizzate per raccogliere dati da intestazioni e cookie non disponibili in caso contrario per la raccolta dati.

## s.charSet {#concept_E65B9A8F75C3482C87D0D455805F89BD}

<!-- 
charset.xml
-->

La proprietà charset, normalmente impostata nel file javascript, viene utilizzata da Analytics per convertire i dati in entrata in UTF -8 per l'archiviazione e la creazione di rapporti da parte di Analytics.

>[!Note:] La proprietà charset è necessaria per inviare dati a una suite di rapporti multibyte e non deve mai essere utilizzata con una suite di rapporti standard. L'impostazione della proprietà charset con una suite di rapporti ISO standard può causare un troncamento variabile o una conversione imprevista dei caratteri.

Il valore della proprietà charset deve corrispondere alla codifica della pagina Web nell'intestazione tag META o http, anche se la sintassi può essere leggermente diversa. Anche se il tag META può utilizzare un alias per la codifica, il valore di charset deve utilizzare il nome preferito (o ufficiale) della codifica.

Alcune delle codifiche più comuni con nome e alias preferiti sono elencate nella tabella seguente.

| Nome preferito | Alias |
|--- |--- |
| ISO -8859-1 | ISO_ 8859-1, CP 819, latin 1 |
| ISO -8859-2 | ISO_ 8859-2, latin 2 |
| ISO -8859-5 | ISO_ 8859-5, cyrillic |
| Big5 | Big -5 |
| Shift_ JIS | SJIS |

Dato che esistono numerose codifiche e alias, contatta il tuo consulente di implementazione o l'Assistenza clienti Adobe per confermare il valore corretto per charset, se non viene visualizzato nella tabella sopra.

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

Qualsiasi valore non-blank del parametro charset causa la conversione dei dati in UTF -8 per l'archiviazione. Tutti i caratteri nell'intervallo 128-255 verranno convertiti nella sequenza a due byte UTF -8 corretta e memorizzati. Questi caratteri non verranno visualizzati correttamente in una suite di rapporti standard. Pertanto, la proprietà charset non deve mai essere utilizzata con una suite di rapporti standard.

Analogamente, un valore vuoto del parametro charset non riuscirà a superare il processo di conversione dei dati, e tutti i caratteri nell'intervallo 128-255 verranno memorizzati come un singolo byte. Questi caratteri non verranno visualizzati correttamente in una suite di rapporti multibyte, poiché i codici a byte singolo per questi caratteri non sono UTF -8 validi. Pertanto, il parametro charset deve essere sempre usato con una suite di rapporti multibyte. Inoltre, è necessario utilizzare il valore appropriato per la codifica della pagina Web.

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the *`charSet`* variable must be populated.

**Parametri**

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | CE | N/D | "" |

**Sintassi e valori possibili**{#section_EBC2176067A04D9E814CF78A86DC80FA}

```js
s.charSet="character_set"
```

**Esempi** {#section_406DE0A2B58441DB8512F5B3BE5D9CB5}

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```

## s.currencyCode {#concept_CE216F1610E2499D8178DB9A8EB97C63}

<!-- 
currencycode.xml
-->

La variabile determina il tasso di conversione da applicare alle entrate.

Tutti gli importi monetari sono archiviati in una valuta di vostra scelta. If that currency is the same as that specified in *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | cc | Conversione &gt; Acquisti &gt; Ricavi da tutti i rapporti conversione che mostrano entrate o valori monetari | " USD " |

If your site allows visitors to purchase in multiple currencies, you should use the *`currencyCode`* variable to make sure revenue is stored in the appropriate currency. For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. Non appena la raccolta dati riceve i dati, utilizza il tasso di conversione corrente per convertire il 40 Euro nel suo equivalente USD.

Populating the *`currencyCode`* variable on the HTML page instead of in the JavaScript file is recommend if you sell in multiple currencies. If you want to use your own conversion rates rather than the conversion rates used by Adobe, set the *`currencyCode`* to equal the base currency of your report suite. You then convert all revenue before sending it into [!DNL Analytics].

La conversione valuta si applica sia alle entrate che agli eventi di valuta. Si tratta di eventi utilizzati per sommare valori simili alle entrate, come tasse e spedizione. I ricavi e gli eventi di valuta sono specificati nella stringa dei prodotti. For more information on products, see [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). For more details on how currencies are managed, see [Multi-Currency Support](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/)..

**Sintassi e valori possibili**{#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

Only the currency codes listed in [Multi-Currency Support](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/) are allowed.

**Esempi** {#section_D55ED45369544C8AAA02B3193752636C}

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

**Impostazioni di configurazione**{#section_D05E29F545A04958B1C0A82248BCA1B0}

Adobe [!DNL Customer Care] can change the default currency setting for your report suite. Quando cambi la valuta di base per una suite di rapporti, le entrate esistenti nel sistema non sono convertite. Tutti i nuovi valori delle entrate saranno convertiti di conseguenza.

**Insidie, domande e suggerimenti**{#section_08A80A87B54A4861905953A6FA61FF8F}

* If you notice surprisingly large amounts of revenue in reports, ensure that the *`currencyCode`* variable and base currency of the report suite are set correctly.
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics.
* Gli eventi di valuta non devono essere utilizzati per scopi non valutari. If you need to count arbitrary or dynamic values that are not currency, use the [!UICONTROL numeric] event type.
* When the *`currencyCode`* variable is empty, no conversion is applied.

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

<!-- 
cookiedomain.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. Ad esempio, è possibile impostare i cookie con il nome completo della pagina utilizzando:

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

<!-- 
cookiedomainperiods.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Questa variabile viene utilizzata anche da alcuni plug-in per determinare il dominio corretto per impostare il cookie del plug-in.

The default value for *`cookieDomainPeriods`* is "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain `www.mysite.com`, *`cookieDomainPeriods`* should be "2". For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting *`cookieDomainPeriods`* to "2" on the domain `www.mysite.co.jp`, the `s_cc` and `s_sq` cookies are created on the domain `co.jp`. Because `co.jp` is an invalid domain, almost all browsers reject these cookies. As a consequence, visitor click map data is lost, and the [!UICONTROL Visitor Profile] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] report indicates that almost 100% of visitors reject cookies.

If *`cookieDomainPeriods`* is set to "3" but the domain contains only two periods, the JavaScript file sets the cookies on the subdomain of the site. For example, if setting *`cookieDomainPeriods`* to "3" on the domain `www2.mysite.com`, the `s_cc` and `s_sq` cookies are created on the domain `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example, `store.toys.mysite.com` would still have *`cookieDomainPeriods`* set to "2". This variable definition correctly sets the cookies on the root domain, [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

See also [s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274).

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | CDP | Agisce su più rapporti in quanto controlla la modalità di memorizzazione e gestione dell'ID visitatore. | "2" |

>[!NOTE]
>
>Alcuni servizi di calcolo cloud sono considerati domini di livello principale, che non consentono la scrittura di cookie. (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) Se implementi su tali servizi, potresti essere potenzialmente interessato dall'impostazione della privacy di Analytics, che rimuove gli utenti che hanno bloccato tutti i cookie se non hai configurato il tuo dominio (ad esempio, se stai sottoponendo a test la tua implementazione). In questo caso, ogni hit in cui il sistema ha determinato che i cookie sono disabilitati, non funzionali o inaccessibili viene rifiutato e quindi escluso dai report.

**Esempi** {#section_4218BE29FA5E49F58975A2094329B268}

Impostazione manuale della variabile:

```js
s.cookieDomainPeriods = "3";
```

Diversi esempi per impostare in modo dinamico la variabile se il file javascript di base è entrambi tipi:

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

**Insidie, domande e suggerimenti**{#section_F3BE3F039E5C4359B694DBB61369822C}

* If you notice that visitor click map data is absent, or that the [!UICONTROL Traffic] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] report shows a large percentage of visitors who reject cookies, check that the value of *`cookieDomainPeriods`* is correct.

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. Ciò può causare la perdita di dati quando i visitatori passano da un dominio all'altro.
* The *`cookieDomainPeriods`* variable was used in deprecated implementations prior to *`trackingServer`* to set the visitor ID cookie. Though only present in outdated code, failure to correctly define *`cookieDomainPeriods`* in this circumstance puts your implementation at risk of data loss.

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

<!-- 
fpCookieDomainPeriods.xml
-->

La variabile è destinata ai cookie impostati da javascript (s_ sq, s_ cc, plug-in) che sono cookie di prime parti ereditati anche se l'implementazione utilizza i domini di terze parti 2 o 7. net o omtrdc. net.

The *`fpCookieDomainPeriods`* variable should never be dynamically set . If you use *`cookieDomainPeriods`*, it is good practice to specify a value for *`fpCookieDomainPeriods`* as well. *`fpCookieDomainPeriods`* eredita il *`cookieDomainPeriods`* valore. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " *`fpCookieDomainPeriods`*" refers to the number of periods (".") nel dominio quando il dominio inizia con «www». For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

The [!DNL AppMeasurement] for JavaScript file uses the *`fpCookieDomainPeriods`* variable to determine the domain with which to set first-party cookies other than the [!UICONTROL visitor ID] (s_vi) cookie. Questa variabile presenta almeno due cookie, inclusi s_ sq e s_ cc (utilizzati rispettivamente per il controllo dei cookie e il controllo dei cookie). Cookies used by plug-ins such as [!UICONTROL getValOnce] are also affected.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | Cookiedomainperiod |

**Codice di esempio per l'impostazione delle variabili di dominio cookie**{#section_5200A92D40384C82998606E800B69E13}

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

**Sintassi e valori possibili**{#section_87923F4C12E74AF99CC9AFC0FFD77D49}

The *`cookieDomainPeriods`* variable is expected to be a string, as shown below.

```js
s.fpCookieDomainPeriods="3"
```

**Esempi** {#section_EF7355718AD849BF963EE9F6F9F79891}

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

**Impostazioni di configurazione**{#section_DB65D9BC4F3048C8AD08F9A7CD8FCFC0}

Nessuno

## s.cookieLifetime {#concept_8347C6648B0E4D4996E2F223C34B9A3D}

<!-- 
cookielifetime.xml
-->

La variabile viene utilizzata sia dai server javascript che dai server di raccolta dati per determinare la durata di un cookie.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | cl | Traffico &gt; Tecnologia &gt; Cookie tutti i rapporti sui visitatori | "" |

If *`cookieLifetime`* is set, it overrides any other cookie expirations for both JavaScript and data collection servers, with one exception, described below. The *`cookieLifetime`* variable can have one of three values:

* [!DNL Analytics] Cookie
* Cookie
* Impostazioni e plug-in javascript

**Sintassi e valori possibili**{#section_09D4D122451B45FAB2C9398600EC66F1}

```js
s.cookieLifetime="value"
```

I valori possibili sono elencati di seguito:

* ""
* " NONE "
* " SESSION "
* Un numero intero che rappresenta il numero di secondi alla scadenza

**Esempi** {#section_91499F70C8B14D3292FCF1B60F04E30A}

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

**Impostazioni di configurazione**{#section_7BDAD4CFE8414C9BA5717A8C8B1BDD34}

Nessuno

**Insidie, domande e suggerimenti**{#section_23E24877F6554E0D9F8C8B7A9C2994B2}

*`cookieLifetime`* influisce [!DNL Analytics] sul tracciamento. If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Use caution when setting *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

<!-- 
doPlugins.xml
-->

La variabile è un riferimento alla funzione e consente la chiamata della funzione nella posizione appropriata all'interno del file javascript.

The *`s_doPlugins`* function is called each time any of the following occurs:

* *`t()`* La funzione è denominata
* *`tl()`* La funzione è denominata
* Clic su un collegamento di uscita o di scaricamento
* Clic su qualsiasi elemento pagina tracciato da mappa clic visitatore

The *`doPlugins`* function is used to run customized routines to gather or alter data. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the *`s_doPlugins`* function should be called s_mc_doPlugins.

**Sintassi e valori possibili**{#section_5CFB94598521455E80947964A306EA89}

The *`s_doPlugins`* function should not be in quotes, and *`doPlugins`* should always be assigned to the exact name of the *`s_doPlugins`* function (if that function is renamed).

```js
s.doPlugins=s_doPlugins;
```

**Esempi** {#section_A5CF0054C56745268A1313CCC7730022}

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

**Impostazioni di configurazione**{#section_641F0EC55E3349E5A3F8671446797074}

Nessuno

**Insidie, domande e suggerimenti**{#section_0C7FB61CF0C946EF8A7D1B686D36E6ED}

* L'unico motivo per cambiare il nome dell'oggetto (ad esempio, da s a s_ mc) è quello di condividere contenuto con o di estrarre contenuto da altri clienti. Renaming the *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* If you unexpectedly start pulling in content from another Adobe customer, and your *`s_doPlugins`* function is being overwritten, it is possible to simply rename the *`s_doPlugins`* function without changing the object name. Mentre la soluzione migliore consiste nell'utilizzare un nome oggetto diverso da quello di altri file javascript sulla stessa pagina, non è necessario farlo.

## s. registerpretrackcallback e s. registerposttrackcallback

Queste funzioni sono utilizzate come parametri: callback (una funzione) e i parametri a tale funzione. Ad esempio:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

The callback is invoked with the `requestUrl` and any parameters passed in when the callback is registered. Ciò si verifica prima o dopo la chiamata di tracciamento, a seconda del metodo utilizzato per registrare il callback.

L'ordine in cui tali callback vengono invocati non è garantito. I callback registrati nella funzione pranziana vengono invocati dopo la creazione dell'URL di tracciamento finale. I callback post vengono chiamati a seguito di una chiamata di tracciamento completata (se la chiamata di tracciamento non riesce, queste funzioni non vengono chiamate). Any callback registered with `registerPreTrackCallback` do not affect the tracking call. Inoltre, la chiamata di qualsiasi metodo di tracciamento in qualsiasi callback registrato non è consigliata e potrebbe provocare un ciclo infinito.

## s.trackDownLoadLinks {#concept_0A7AEAB3172A4BEA8B2E8B1A3A8F596C}

<!-- 
trackDownloadLinks.xml
-->

Impostate su true se desiderate tenere traccia dei collegamenti ai file scaricabili sul sito.

If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* is used to determine which links are downloadable files.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | True |

The *`trackDownloadLinks`* variable should only be set to 'false' if there are no links to downloadable files on your site, or you don't care to track the number of clicks on downloadable files. If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. I dati inviati con un collegamento di download includono l'URL del download dei collegamenti e i dati relativi al clic sul visitatore per tale collegamento. If *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

**Sintassi e valori possibili**{#section_828492CC2A144BC68D18C30CF397EEFC}

The *`trackDownloadLinks`* variable is expected to be either 'true' or 'false.'

**Esempi** {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```js
s.trackDownloadLinks=true 
```

```js
s.trackDownloadLinks=false
```

**Impostazioni di configurazione**{#section_9A5F69966BAF433A8DA2BCF655A652D1}

Nessuno

**Insidie, domande e suggerimenti**{#section_B3764520D81143968F96CB69AADD457F}

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.
* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

<!-- 
trackExternalLinks.xml
-->

Se è "true", e viene utilizzato per determinare se un collegamento a cui è stato fatto clic è un collegamento di uscita.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | True |

The *`trackExternalLinks`* variable should only be set to 'false' if there are no exit links on your site, or if you don't care to track the number of clicks on those exit links. Un collegamento di uscita è un collegamento che porta un visitatore all'esterno del sito. If *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. I dati inviati con un collegamento di uscita includono l'URL del collegamento, il nome del collegamento e i dati della mappa clic per quel collegamento. If *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

**Sintassi e valori possibili**{#section_267748949A7544658E1D838AAEF964B2}

The *`trackExternalLinks`* variable is expected to be either 'true' or 'false.'

```js
s.trackExternalLinks=true|false
```

**Esempi** {#section_EF18DB05884240F5B5062631E68E10A7}

```js
s.trackExternalLinks=true 
```

```js
s.trackExternalLinks=false
```

**Impostazioni di configurazione**{#section_C8748CFE36324FAFB14C23E3E1FB5082}

Nessuno

**Insidie, domande e suggerimenti**{#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

<!-- 
trackInlineStats.xml
-->

La variabile determina se i dati clickmap vengono raccolti.

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | ClickMap | False |

**Sintassi e valori possibili**{#section_46B2C1DD0D104A01A9C239929420CD90}

```js
s.trackInlineStats=true|false
```

The *`trackInlineStats`* variable is expected to be either 'true' or 'false.'

**Esempi** {#section_F146770917A3493AB8007626913CD6AB}

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

**Impostazioni di configurazione**{#section_FB2CDB07CDCE454786D96A66E4D8EDCD}

Nessuno

## s.linkDownloadFileTypes {#concept_06CC14C69DFD4887A5E6967A157A9E05}

<!-- 
linkDownloadFileTypes.xml
-->

La variabile è un elenco separato da virgole di estensioni di file.

If your site contains links to files with any of these extensions, the URLs of these links will appear in the [!UICONTROL File Downloads] report.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | N/D | Traffico &gt; Traffico sito &gt; Download file | " exe, zip, wav, mp 3, mov, mpg, avi, wmv, doc, pdf, xls " |

The *`linkDownloadFileTypes`* variable is only relevant when *`trackDownloadLinks`* is set to 'True.'

Only left-mouse-clicks on a link are counted in the [!UICONTROL File Downloads] report. All file downloads that start automatically when a page loads, or that are only downloaded after a redirect, are not counted in the [!UICONTROL File Downloads] report. When you right-click a file and select the "Save Target As..." option, it is not counted in the [!UICONTROL File Downloads] report.

The *`linkDownloadFileTypes`* variable may be used to track clicks to RSS feeds. If you have links to RSS feeds with a .xml or other extension, appending ",xml" to the *`linkDownloadFileTypes`* list allows you to see how often each RSS link is clicked.

**Sintassi e valori possibili**{#section_E0B3F3817BBF4B11AFAABEF8BB951E5A}

Includere solo le estensioni di file (senza spazi).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Qualsiasi estensione file può essere inclusa nell'elenco. Be careful not to include a common file extension, such as htm or aspx, in *`linkDownloadFileTypes`*. In tal modo viene inviata una richiesta di immagine aggiuntiva per ogni clic, che verrà addebitata come chiamata server principale.

**Esempi** {#section_C53F1AF768434CEBA65F3D255BC470AD}

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

**Impostazioni di configurazione**{#section_CE24D5852E4D441A958A4EDDB82382A7}

Nessuno

**Insidie, domande e suggerimenti**{#section_786CF22D5553429EB6524B13774793BC}

* Only left-clicks on download files cause the URL to appear in the [!UICONTROL File Downloads] report.
* Including a common file extension in *`linkDownloadFileTypes`* may significantly increase the total server calls sent to Adobe's servers.
* Links to server-side redirects or HTML pages that automatically begin downloading a file are not counted unless the file extension is in *`linkDownloadFileTypes`*.
* Collegamenti che utilizzano javascript (ad esempio javascript: Openlink () non viene conteggiato nei download dei file.

## s.linkInternalFilters {#concept_D53C1186762E4AAE82451712B0801CAD}

<!-- 
linkInternalFilters.xml
-->

La variabile viene utilizzata per determinare quali collegamenti sul sito sono chiusi.

È un elenco di filtri separati da virgole che rappresentano i collegamenti che fanno parte del sito.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Paths (Percorsi) &gt; Entries &amp; Exits (Uscita) &gt; Exit Links (Esci da collegamenti) |  |

>[!NOTE]
>
>In precedenza era consigliato impostare linkinternalfilters su javascript:. In questo modo, tutti i domini venivano considerati esterni, incluso il dominio corrente in cui si trova il tag. Se vuoi che diversi domini siano considerati interni, puoi aggiungerli, come mostrato negli esempi seguenti.

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. La finestra Destinazione di un collegamento di uscita è a comparsa o la finestra esistente non influisce sulla visualizzazione del collegamento nel rapporto sui collegamenti di uscita. Exit links are only tracked if *`trackExternalLinks`* is set to `"true"`. (See [Link Tracking](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) in the Dynamic Tag management documentation for information about how DTM handles exit links.) The filters in *`linkInternalFilters`* are not case-sensitive.

The list of filters in *`linkInternalFilters`* applies to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). I filtri vengono sempre applicati al percorso assoluto dell'URL, anche se viene utilizzato un percorso relativo.

Be careful that all the domains of your site (and any partners who are using your JavaScript file) are included in *`linkInternalFilters`*. Se non hai tutti i domini inclusi nell'elenco, tutti i collegamenti on e a tali domini vengono considerati collegamenti di uscita, aumentando le chiamate al server inviate. If you would like multiple domains or companies to use a single [!DNL AppMeasurement] for JavaScript file, you may consider populating *`linkInternalFilters`* on the page, overriding the value specified in the JavaScript file. Se hai domini personalizzati che eseguono immediatamente il reindirizzamento al dominio principale, questi domini personalizzati non devono essere inclusi nell'elenco.

L'esempio seguente illustra come viene utilizzata questa variabile. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

**Sintassi e valori possibili**{#section_810966F09912415B96EA9C2EDAE0CEA0}

The *`linkInternalFilters`* variable is a comma-separated list of ASCII characters. Non sono consentiti spazi.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

**Esempi** {#section_491F48556DC247889D54C66FC431B4EC}

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

**Impostazioni di configurazione**{#section_546AC1FACB664ABFBCF312990097C987}

Nessuno

**Insidie, domande e suggerimenti**{#section_E83A6F8B6EE44D51A2800D83F8BB264F}

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* Periodically check the [!UICONTROL Paths] &gt; [!UICONTROL Entries & Exits] &gt; [!UICONTROL Exit] Links report to make sure that none of the entries in that report are incorrect.

* Controlla periodicamente i contratti partner per determinare se contengono restrizioni per il tracciamento dei collegamenti. Ad esempio, potrebbe essere vietato tenere traccia dei collegamenti visualizzati nei annunci visualizzati partner. Filter partner links by adding their domain to *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

## s.linkLeaveQueryString {#concept_118C280E29394DB5A16DBBF41EB4D742}

<!-- 
linkLeaveQueryString.xml
-->

Per impostazione predefinita, le stringhe di query sono escluse da tutti i rapporti.

Per alcuni collegamenti di uscita e collegamenti di download, la parte importante dell'URL può essere nella stringa query, come mostrato nell'URL di esempio seguente.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

The download file name can be defined in the query string and, consequently, the query string is necessary to make the [!UICONTROL File Downloads] report more accurate.

The *`linkLeaveQueryString`* variable determines whether or not the query string should be included in the [!UICONTROL Exit Links] and [!UICONTROL File Download] reports.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | N/D | Uscita dai download dei file dei collegamenti | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

**Sintassi** {#section_C40CF036B71A496D92574C6E46DE8302}

```js
s.linkLeaveQueryString=[false/true]
```

**Esempi** {#section_E42CEC8DDE624A4B979F4F6C8094A7F9}

```js
s.linkLeaveQueryString=false
```

**Valori possibili**{#section_E13211451B664B909B1BFDD050472F18}

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

**Impostazioni di configurazione**{#section_835FD74D3CA9425A9D091CACF88A6F1F}

Non è necessaria alcuna configurazione per questa variabile.

**Insidie, domande e suggerimenti**{#section_085E79D1A7F74F5D95F82D34FB82AEC4}

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.

## s.linkTrackVars {#concept_A6B117826C15402EBD0781A94C8065B9}

<!-- 
linkTrackVars.xml
-->

La variabile è un elenco separato da virgole di variabili che vengono inviate con collegamenti personalizzati, exit e download.

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

All variables that should be sent with link data (custom, exit, and download links) should be listed in *`linkTrackVars`*. If *`linkTrackEvents`* is used, *`linkTrackVars`* should contain "events."

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Any | "Nessuno" |

When populating *`linkTrackVars`*, do not use the 's.' prefix for variables. For example, instead of populating *`linkTrackVars`* with "s.prop1," you should populate it with "prop1." The following example illustrates how *`linkTrackVars`* should be used.

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

Poiché il collegamento a google.com è un collegamento di uscita (a meno che tu non sia Google), l'evento 1 e evar 1 vengono inviati con i dati del collegamento exit, aumentando le istanze associate a evar 1 e il numero di volte in cui l'evento 1 viene attivato. In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

**Sintassi e valori possibili**{#section_DCC239F5CFE74959856764DAB1862BA7}

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. Utilizzate'evar 1 'anziché's. evar 1.'

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

The *`linkTrackVars`* variable may contain only variables that are sent to [!DNL Analytics], namely: *`events`*, *`campaign`*, *`purchaseID`*, *`products`*, [!UICONTROL eVar1-75], [!UICONTROL prop1-75], [!UICONTROL hier1-5], *`channel`*, *`server`*, *`state`*, *`zip`*, and *`pageType`*.

**Esempi** {#section_546BAAC7373A41BF8583B280EAAB607C}

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

**Impostazioni di configurazione**{#section_E387604B8A434A7F89A82A886649A89D}

Nessuno

**Insidie, domande e suggerimenti**{#section_99E0783A608C4462945F35D21AB4AC2B}

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* If *`linkTrackEvents`* is used, *`linkTrackVars`* must contain "events."

* Non utilizzate "s." o "s_ objectname." per le variabili.

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

<!-- 
linkTrackEvents.xml
-->

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

In the first link to [!DNL help.php], notice that the events variable retains the value that was set before the link was clicked,. Questo consente l'invio dell'evento 1 con il collegamento personalizzato. In the second example, the link to [!DNL test.php], event2 is not recorded because it is not listed in *`linkTrackEvents`*.

To avoid confusion and potential problems, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. This variable is only considered if *`linkTrackVars`* contains "events."

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Conversione   | "Nessuno" |

**Sintassi e valori possibili**{#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

The *`linkTrackEvents`* variable is a comma-separated list of events (no spaces).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Only event names are allowed in *`linkTrackEvents`*. These events are listed in [Events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). Se viene visualizzato uno spazio prima o dopo il nome dell'evento, l'evento non può essere inviato con richieste di immagini collegate al collegamento.

**Esempi** {#section_AB7F952E522A4DCC92944EBF74C26BDD}

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

**Impostazioni di configurazione**{#section_D938A47346D94A0C9E98FB327F2EF349}

Nessuno

**Insidie, domande e suggerimenti**{#section_DBB68BECC9D44380816113DB2566C38C}

* The JavaScript file only uses *`linkTrackEvents`* if *`linkTrackVars`* contains the "events" variable. "events" should be included in *`linkTrackVars`* only when *`linkTrackEvents`* is defined.

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

<!-- 
linkExternalFilters.xml
-->

Se il sito contiene molti collegamenti a siti esterni e non desiderate tenere traccia di tutti i collegamenti uscita, utilizzate per generare rapporti su un sottoinsieme specifico di collegamenti di uscita.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Paths (Percorsi) &gt; Entries &amp; Exits (Uscita) &gt; Exit Links (Esci da collegamenti) | "" |

The *`linkExternalFilters`* variable is an optional variable used in conjunction with *`linkInternalFilters`* to determine whether a link is an exit link. Un collegamento di uscita è definito come qualsiasi collegamento che allontana il visitatore dal sito. La finestra Destinazione di un collegamento di uscita è una finestra a comparsa o la finestra esistente, non influisce sulla visualizzazione del collegamento nel rapporto sui collegamenti di uscita. Exit links are tracked only if *`trackExternalLinks`* is set to 'true.' The filters in *`linkExternalFilters`* and *`linkInternalFilters`* are case insensitive.

>[!NOTE]
>
>If you don't want to use *`linkExternalFilters`*, delete it or set it to "".

The filters list in *`linkExternalFilters`* and *`linkInternalFilters`* apply to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to 'true,' the filters apply to the entire URL (domain, path, and query string). Questi filtri vengono sempre applicati al percorso assoluto dell'URL, anche se viene utilizzato un percorso relativo.

Most companies find that *`linkInternalFilters`* gives them enough control over exit links that they don't need *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

L'esempio seguente illustra come viene utilizzata questa variabile. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

**Sintassi e valori possibili**{#section_E35DAAAE8BDE44CEB8F6763EF1344693}

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. Non sono consentiti spazi.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Any portion of a URL might be included in *`linkExternalFilters`*, separated by commas.

**Esempi** {#section_1D2F13EEC28942868C2F4207ADF2DDE0}

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

**Impostazioni di configurazione**{#section_2D0CA911855B4B3698145FC18D5021C3}

Nessuno

**Insidie, domande e suggerimenti**{#section_8B40E6F539E3473B934A8DB7C5086D73}

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. Do not use this variable in place of *`linkInternalFilters`* to force internal links to become exit links.

* If *`linkExternalFilters`* should be applied to the query string of a link, make sure *`linkLeaveQueryString`* is set to 'true.' See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

<!-- 
s_usePlugins.xml
-->

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | True |

**Sintassi e valori possibili**{#section_BAD0F150047A4B7FB1214491B939A1FC}

```js
s.usePlugins=true|false
```

The [!UICONTROL usePlugins] variable is expected to be either 'true' or 'false.'

**Esempi** {#section_1423CC3026384B1A9F78B272166B1DF5}

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

The [!UICONTROL usePlugins] variable should only be false (or not declared) if the *`s_doPlugins`* function is not declared in your JavaScript file.

**Impostazioni di configurazione**{#section_DFD41717134147E988B6AFC7DE5BB9E3}

Nessuno