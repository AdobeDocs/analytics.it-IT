---
description: Le variabili di pagina comporteranno direttamente un rapporto, come pagename, List Prop, List Variables e così via.
keywords: Implementazione di Analytics
seo-description: Le variabili di pagina comporteranno direttamente un rapporto, come pagename, List Prop, List Variables e così via.
seo-title: Variabili di pagina
solution: Analytics
subtopic: Variabili
title: Variabili di pagina
topic: Sviluppatore e implementazione
uuid: 2578 eddd -74 db -4 a 8 a -96 f 2-d 0289 ec 1826 b
translation-type: tm+mt
source-git-commit: af2c0dd5269fe54dec949d4bd98bb09f22c9bfa2

---


# Variabili di pagina

Le variabili di pagina comporteranno direttamente un rapporto, come pagename, List Prop, List Variables e così via.

## browserHeight {#concept_DB87062001824369A56AA1E7969EC02A}

La variabile visualizza l'altezza della finestra del browser.

<!-- 
browserheight.xml
-->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Questa variabile deve essere letta solo e non deve mai essere impostata.

Puoi leggere questi valori e copiarli in prop/evar, ma non modificarli mai. Questa variabile viene introdotta con la versione H .11 del file javascript.

**Parametri**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Query Param </th> 
   <th class="entry"> Valore </th> 
   <th class="entry"> Esempio  </th> 
   <th class="entry"> Report interessati </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>Un numero intero positivo </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Traffico &gt; Tecnologia &gt; Altezza browser </p> </td> 
  </tr> 
 </tbody> 
</table>

## browserWidth {#concept_BA0C4C2D655D41A4AEF059E21E4A55A2}

La variabile visualizza la larghezza della finestra del browser.

<!-- 

browserwidth.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Questa variabile deve essere letta solo e non deve mai essere impostata.

Puoi leggere questi valori e copiarli in prop/evar, ma non modificarli mai. Questa variabile viene introdotta con la versione H .11 del file javascript.

**Parametri**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Query Param</b> </p> </td> 
   <td> <p> <b>Valore</b> </p> </td> 
   <td> <p> <b>Esempio</b> </p> </td> 
   <td> <p> <b>Report interessati</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>Un numero intero positivo </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Traffico &gt; Tecnologia &gt; Larghezza browser </p> </td> 
  </tr> 
 </tbody> 
</table>

## campaign {#concept_C7BF7B8A69D048A6AB482052A98A91F8}

La variabile identifica le campagne di marketing utilizzate per portare visitatori sul sito. Il valore di in genere viene prelevato da un parametro di stringa query.

<!-- 

campaign.xml

 -->

**Parametri**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro Debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 Byte </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>Conversione &gt; Campagne &gt; Codice di tracciamento </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

Ogni elemento di una campagna di marketing deve avere un codice di tracciamento univoco associato. Ad esempio, una parola chiave del motore di ricerca a pagamento potrebbe avere un codice di tracciamento pari a 112233. When someone clicks the keyword with the 112233 tracking code and is routed to the corresponding website, the *`campaign`* variable records the tracking code.

There are two main ways to populate the *`campaign`* variable:

* The [!UICONTROL getQueryParam] plug-in, used in the JavaScript file, retrieves a query string parameter from the URL. For more information on the [!UICONTROL getQueryParam] plugin, see [Implementation Plug-ins](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* Assign a value to the *`campaign`* variable in the HTML on the Web page.

With either method of populating the *`campaign`* variable, the Back button traffic may inflate the actual number of click-throughs from a campaign element.

Ad esempio, un visitatore accede al sito facendo clic su una parola chiave di ricerca a pagamento. Quando il visitatore arriva sulla pagina di destinazione, l'URL contiene un parametro stringa query che identifica il codice di tracciamento della parola chiave. Il visitatore quindi fa clic su un collegamento a un'altra pagina, quindi fa clic sul pulsante Indietro per tornare alla pagina di destinazione. Quando il visitatore arriva una seconda volta sulla pagina di destinazione, l'URL con il parametro della stringa query identifica nuovamente il codice di tracciamento. E un secondo click-through viene registrato, gonfiando erroneamente il numero di click-through.

To avoid this inflation of click-throughs, Adobe recommends using the [!UICONTROL getValOnce] plugin to force each campaign click-through to be counted only once per session. For more information on the [!UICONTROL getValOnce] plugin, see [Implementation Plug-ins](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**Sintassi e valori possibili**{#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

The *`campaign`* variable has the same limitations as all other variables. Adobe consiglia di limitare il valore ai caratteri ASCII standard.

**Distinzione tra maiuscole e minuscole**{#section_112A9A0F886148B6BEF9A7C94BE0A36F}

Le evar non fanno distinzione tra maiuscole e minuscole, ma vengono visualizzate nelle maiuscole della prima occorrenza. Ad esempio, se la prima istanza di evar 1 è impostata su «Registrato», ma tutte le istanze successive vengono trasmesse come «accesso», i rapporti mostrano sempre «Accesso» come valore della evar.

**Esempi** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**Impostazioni di configurazione**{#section_4083F281968443169EAF8C0E8529D7BC}

Ogni valore della campagna rimane attivo per un utente e riceve credito per le attività e gli eventi di successo dell'utente fino alla scadenza. Puoi modificare la scadenza della variabile della campagna in Admin Console.

**Insidie, domande e suggerimenti**{#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* To keep click-throughs from being inflated, use the [!UICONTROL getValOnce] plugin to let the click-through for a campaign be counted only once per session. For more information on the [!UICONTROL getValOnce] plug-in, see [Implementation Plug-ins](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* For more information on tracking marketing campaigns and keyword buys, see [Campaigns](https://marketing.adobe.com/resources/help/en_US/reference/?f=campaign).
* Use the [!DNL DigitalPulse Debugger] to see the actual value of campaigns (v0 in the debugger). Se la release v 0 non viene visualizzata nel debugger, per quella pagina non vengono registrati dati della campagna.

## channel {#concept_C7770B8C15724A99B10F8F468AF82D0D}

La variabile viene utilizzata più spesso per identificare una sezione del sito.

<!-- 

channel.xml

 -->

Ad esempio, un esercente potrebbe avere sezioni come Electronics, Toys o Apparel. Un sito multimediale può avere sezioni come News, Sport o Business.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 Byte | CH | Contenuto del sito &gt; Sezioni del sito | "" |

Adobe consiglia di compilare la variabile canale su ogni pagina. You can also turn on a correlation between the *`channel`* and [!UICONTROL page name] variables.

When sections have one or more levels of subsections, you can show those sections in the *`channel`* variable or use separate variables to identify levels.

**Sintassi e valori possibili**{#section_ED90592730B64242A737F4090F1DCEE4}

```js
s.channel="value"
```

The *`channel`* variable has no extra limitations on its values.

**Esempi** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Insidie, domande e suggerimenti**{#section_61941D5E4E644B59A267A4F44FD5DE8C}

If your site contains multiple levels, you can use the *`hierarchy`* or another variable to designate those levels. *`channel`* Il valore non persiste, ma gli eventi di successo generati sulla stessa pagina vengono attribuiti al *`channel`* valore.

## colorDepth {#concept_756516E181F449B996DA9CC5A53FFA3D}

La variabile viene utilizzata per mostrare il numero di bit utilizzati per visualizzare il colore su ciascun pixel della schermata.

<!-- 

colordepth.xml

 -->

Ad esempio, 32 rappresenta 32 bit di colore sullo schermo. This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Questa variabile deve essere letta solo e non deve mai essere impostata.

You may read these values and copy them into `props/eVars`, but you should never alter them. Questa variabile viene introdotta con la versione H .11 del file javascript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| c | 8,16 e 32 | 32 | Traffico &gt; Tecnologia &gt; Monitor Profondità colore |

## connectionType {#concept_2F98ECB8BB3D490F834F274EFF02860E}

La variabile, in Internet Explorer, indica se il browser è configurato su una connessione LAN o modem.

<!-- 

conntype.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Questa variabile deve essere letta solo e non deve mai essere impostata.

You may read these values and copy them into `props/eVars`, but you should never alter them. Questa variabile viene introdotta con la versione H .11 del file javascript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| ct | lan o modem | lan | Traffico &gt; Tecnologia &gt; Tipo di connessione |

## cookiesEnabled {#concept_DF5B37E38D0D4F6DB910F419F92467ED}

La variabile indica se un cookie di sessione first-party può essere impostato da javascript.

<!-- 

cookiesenabled.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Questa variabile deve essere letta solo e non deve mai essere impostata.

You may read these values and copy them into `props/eVars`, but you should never alter them. Questa variabile viene introdotta con la versione H .11 del file javascript.

| Query Param | Valore | Esempio  |
|---|---|---|
| k | Y o N | Y |

## dc {#concept_ECE6C83376704B3C84A920EFDD338A31}

(Obsoleto) La variabile consente di selezionare il centro dati al quale i dati vengono inviati.

<!-- 

dc.xml

 -->

>[!NOTE]
>
>La variabile dc è stata rimossa. You should set *`trackingServer`* for all implementations to the value that is generated by [!UICONTROL Code Manager] in s_code.js.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | 112 |

The data center is identified in the *`dc`* variable in order to match [!UICONTROL ActionSource].

## eVarN {#concept_74FFDDB44B5344E18ABC6F2F99DF4649}

The [!UICONTROL eVar] variables are used for building custom reports.

<!-- 

eVarN.xml

 -->

Quando una evar è impostata su un valore per un visitatore, il valore viene ricordato finché non scade. Tutti gli eventi di successo rilevati da un visitatore mentre il valore evar è attivo vengono conteggiati verso il valore evar.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 255 Byte | V1-v75 ( [or v100 or v250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) | Conversione personalizzata | "" |

**Scadenza**{#section_6DB5882B960D4660AE248B91B76883C4}

[!UICONTROL eVars] scade dopo un periodo di tempo specificato. Dopo la scadenza dell'evar, non riceve più credito per gli eventi di successo. Le evar possono anche essere configurate per scadere su eventi di successo. Ad esempio, se si dispone di una promozione interna scaduta alla fine di una visita, la promozione interna riceve credito solo per acquisti o registrazioni che si verificano durante la visita in cui sono stati attivati.

Esistono due modi per scadere una evar:

* Puoi impostare l'evar in scadenza dopo un determinato periodo di tempo o un evento.
* Puoi utilizzare forza la scadenza di una evar, utile quando si rimuove una variabile.

Se a maggio viene utilizzata una evar per riflettere promozioni interne e scade dopo 21 giorni e a giugno viene utilizzato per acquisire le parole chiave di ricerca interna, il 1 giugno dovrebbe forzare la scadenza o reimpostazione della variabile. In tal modo sarà possibile mantenere i valori di promozione interni dai report di giugno.

**Distinzione tra maiuscole e minuscole**{#section_6E9145B7FCC2438E95BB35AAE3857412}

Le evar non fanno distinzione tra maiuscole e minuscole, ma vengono visualizzate nelle maiuscole della prima occorrenza. Ad esempio, se la prima istanza di evar 1 è impostata su «Registrato», ma tutte le istanze successive vengono trasmesse come «accesso», i rapporti mostrano sempre «Accesso» come valore della evar.

**Contatori**{#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

Anche se le evar vengono utilizzate più spesso per contenere valori stringa, possono essere configurate anche come contatori. Le evar sono utili come contatori quando si cerca di calcolare il numero di azioni intraprese da un utente prima di un evento. Ad esempio, puoi utilizzare un evar per acquisire il numero di ricerche interne prima dell'acquisto. Ogni volta che un visitatore cerca, la evar deve contenere il valore «+1». Se un visitatore cerca quattro volte prima di un acquisto, viene visualizzata un'istanza per ogni totale: 1.00, 2.00, 3.00 e 4.00. Tuttavia, solo il 4.00 riceve credito per l'evento di acquisto (Ordini e metriche Entrate). Solo i numeri positivi sono consentiti come valori di un contatore evar.

**Sottorelazioni**{#section_2BEABBBC735241F4BA42E74D19B5AEE0}

A common requirement for a [!UICONTROL Custom eVar] report is the ability to break down one [!UICONTROL Custom eVar] report by another. Ad esempio, se una evar contiene genere e un altro contiene stipendi, potresti fare una domanda: dei visitatori di sesso femminile al sito, il numero di ricavi generati dalle donne che hanno effettuato oltre $ 50,000 all'anno. Qualsiasi evar completamente correlato consente questo tipo di interruzione nei rapporti. Ad esempio, se l'evar di genere dispone di sottorelazioni complete abilitate, tutti gli altri report evar personalizzati possono essere suddivisi per genere e il genere può essere suddiviso da tutti gli altri. Per visualizzare la relazione tra due rapporti, solo una di esse necessita di tutte le sottorelazioni complete abilitate. By default, [!UICONTROL Campaigns], [!UICONTROL Products], and [!UICONTROL Category] reports are fully sub-related (any eVar can be broken down by campaign or products).

**Sintassi e valori possibili**{#section_BD46438B14F3488FB9AC42994C317B06}

While eVars may be renamed, they should always be referred to in the JavaScript file by eVarX, where X is a number between 1 and 75 ( [or 100, or 250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)).

```js
s.eVarX="value"
```

Quando non viene utilizzato come contatore, le evar hanno le stesse limitazioni di tutte le altre variabili. Se la evar è un "contatore", deve ricevere valori numerici come "1" o "2.5". Se vengono forniti più di due posizioni decimali, il contatore evar viene arrotondato a due posizioni decimali. Un contatore evar potrebbe non contenere numeri negativi.

**Esempi** {#section_B37F4B0D56734DA3AB02BB218825BA4E}

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**Impostazioni di configurazione**{#section_BD1FE63001C84D3DB69F3DEE243960B6}

eVars can be configured in [!UICONTROL Analytics > Admin > Report Suites > Edit Settings > Conversion > Conversion Variables]. All eVars can be configured with a [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Allocation], [!UICONTROL Expire After Setting], or [!UICONTROL Reset]. Ogni impostazione di configurazione viene indirizzata separatamente.

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Impostazione </th> 
   <th class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nome </td> 
   <td> Allows you to change the name of the eVar report within <span class="keyword"> Analytics </span>. <p>The eVar should still be referenced as s.eVarX in the JavaScript code, no matter what name is given to the report in <span class="keyword"> Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> Type (Tipo) </td> 
   <td> Consente di mostrare se evar è una stringa di testo o un contatore. </td> 
  </tr> 
  <tr> 
   <td> Allocazione </td> 
   <td> Utilizzato per configurare il valore dell'evar ricevuto credito per gli eventi di successo. <p>Se Allocazione è impostata su "Più recente (ultimo)", B riceve credito. </p> <p>Se Allocazione è impostata su «Valore originale (prima)», A riceve il credito. </p> <p>Se Allocazione è impostata su "Linear", sia A e B ricevono credito per metà del valore di acquisto. </p> </td> 
  </tr> 
  <tr> 
   <td> Scade dopo </td> 
   <td> Consente di determinare se una evar scade su un evento specifico, come l'acquisto, o dopo un periodo di tempo personalizzato o predefinito. </td> 
  </tr> 
  <tr> 
   <td> Reset </td> 
   <td> By selecting the <span class="wintitle"> Reset </span> check box for an eVar, and clicking <span class="wintitle"> Save </span> at the bottom of the page, all values of that eVar are immediately expired. In tal caso, solo i nuovi valori dell'evar ricevono credito per gli eventi di successo. </td> 
  </tr> 
 </tbody> 
</table>

**Insidie, domande e suggerimenti**{#section_DA6912C802E445F986C6DE4234C6C737}

* Unlike [!UICONTROL prop] variables, eVar variables are not allowed to be lists of delimited values. Se hai compilato un evar con un elenco di valori, ad esempio "uno, due, tre", tale stringa esatta viene visualizzata nei rapporti.
* I contatori evar non possono contenere numeri negativi.

## Eventi {#concept_FFD115543D54401B98FE683BD7D5B3FE}

La variabile viene utilizzata per registrare eventi di successo comuni sul carrello e eventi di successo personalizzati.

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro Debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nessun limite </td> 
   <td> events </td> 
   <td> <p>Eventi carrello acquisti </p> <p>Eventi personalizzati </p> </td> 
   <td> N/D </td> 
  </tr> 
 </tbody> 
</table>

An [!UICONTROL event] should be considered a milestone within a site. Gli eventi di successo sono più comunemente popolati nella pagina di conferma finale di un processo, ad esempio un processo di registrazione o una registrazione a newsletter. Gli eventi personalizzati sono definiti compilando la variabile degli eventi con i valori letterali definiti nella sezione Valori possibili di seguito.

By default, success events are configured as *counter* events. Gli eventi contatore contano il numero di volte in cui è impostato un evento di successo (x +1). Events can also be configured as *numeric* events. Gli eventi numerici consentono di specificare il numero da incrementare (come potrebbe essere necessario quando si conteggia valori dinamici o arbitrari, ad esempio il numero di risultati restituiti da una ricerca interna).

A final event type, *currency*, allows you to define the amount to be added (similar to numeric events), but displays as currency in reports, and is subject to currency conversions based on the s. *`currencyCode`* value and the default currency setting for your report suite. For additional information on using numeric and currency events, see [Products](../../../implement/js-implementation/c-variables/page-variables.md#concept_A4007F6307E4419DAA65E1668A8FEBA2).

**Configurazione della variabile**{#section_9195286C34C54B02B2598E2B856492C3}

The [!UICONTROL s.events] variable is enabled by default for all implementations. I sette eventi di conversione preconfigurati vengono automaticamente abilitati per tutte le nuove suite di rapporti. New custom events (event1- [event100 or event1000](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) can be enabled by any admin-level user using the Admin Console.

**Valori possibili**{#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

Di seguito è riportato un elenco di possibili valori per la variabile degli eventi:

| Evento | Descrizione | Rapporti Popolata |
|---|---|---|
| all'evento | Visualizzazioni prodotto | Variabile   |
| Scoen | Apri/inizializza un nuovo carrello | Carrelli |
| Cetd | Aggiungere elementi al carrello acquisti | Aggiunte carrello |
| Scremove | Rimuovere elementi dal carrello acquisti | Rimozioni carrello |
| Scview | Visualizzare il carrello della spesa | Visualizzazioni carrello |
| Sccheckout | Inizio del processo di pagamento | Pagamenti |
| purchase | Completamento di un acquisto (ordine) | Ordini |
| event 1 - event 1000 (event 100 per il prodotto point) | Eventi personalizzati | Eventi personalizzati |

**Sintassi ed esempi**{#section_45A159DF00114066B8551DDEB15E084C}

Counter events are set by placing the desired events in the [!UICONTROL s.events] variable, in a comma-separated list (if multiple events are to be passed).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

Se si utilizza un codice H 23 o versione successiva, gli eventi del contatore possono avere numeri interi superiori a uno assegnato.

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

L'implementazione di eventi contatore con valori interi assegnati tratterà l'evento come se venisse attivato più volte nella richiesta di immagine. Gli eventi contatore non consentono i decimali. Se questa funzione è richiesta, si consiglia di utilizzare eventi numerici.
Numeric and currency events must be included in the [!UICONTROL s.events] variable, though they typically receive their numerical value (e.g., 24.99) in the [!UICONTROL s.products] variable. Questo consente di collegare valori numerici e valutari specifici a singoli prodotti.

**Serializzazione degli eventi** {#section_A89488EF4471405AAFC4D6DD05E77621}

Per impostazione predefinita, un evento viene conteggiato ogni volta che l'evento viene impostato sul sito.

See [Event Serialization](../../../implement/js-implementation/event-serialization.md#concept_092B638D7FEE423D91F8A57EA8E09705) for more information.

**Sintassi** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**Esempi** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```

## hierN {#concept_C4475D1584D544ACB4C0A573EB60FA08}

The [!UICONTROL hierarchy] variable determines the location of a page in your site's hierarchy.

<!-- 

hierN.xml

 -->

Questa variabile è particolarmente utile per i siti con più di tre livelli nella struttura del sito. Ad esempio, un sito multimediale potrebbe avere 4 livelli alla sezione Sport: Sport, Sport locali, Baseball e Red Sox. Se qualcuno visita la pagina Baseball, Sport, Local Sports e Baseball, tutti i livelli riflettono tale visita.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 255 Byte | H 1-H 5 | Gerarchia | "" |

There are five [!UICONTROL hierarchy] variables available, which must be enabled by Adobe Customer Care. Al momento dell'abilitazione della gerarchia, è necessario definire un delimitatore per la variabile e il numero massimo di livelli per la gerarchia. Ad esempio, se il carattere di delimitazione è una virgola, la gerarchia sportiva potrebbe essere visualizzata come segue.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Accertarsi che nessuno dei nomi delle sezioni contenga il carattere di delimitazione. Ad esempio, se una delle sezioni è denominata "Coach Griffin, Jim", è necessario scegliere un delimitatore diverso da virgola. Ogni sezione gerarchica è limitata a 255 byte, mentre il limite variabile totale è di 255 byte. Dopo aver scelto un delimitatore (al momento della creazione della gerarchia), esso non viene facilmente modificato.

Contattare l'Assistenza clienti di Adobe per modificare il delimitatore di una gerarchia esistente. I delimitatori possono essere composti anche da più caratteri, ad esempio || o/|\, che sono meno propensi all'apparizione in una sezione gerarchica.

**Sintassi e valori possibili**{#section_0739948A68A2420DAB1CBEA3115A5A66}

Non inserire uno spazio tra ciascun carattere di delimitazione. Nell'esempio seguente, N è un numero compreso tra uno e cinque.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

Non utilizzare il carattere di delimitazione, tranne per delimitare i livelli della gerarchia. Il carattere di delimitazione può essere costituito da qualsiasi carattere o carattere desiderato.

**Esempi** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**Impostazioni di configurazione**{#section_E823FB3CAD744D2480EBCE2DF9B134CC}

Nessuno

**Insidie, domande e suggerimenti**{#section_104E5BD320764BDEA5FA8D13A70C78E3}

* Il delimitatore non può essere modificato dopo la configurazione della gerarchia. Se il delimitatore della gerarchia deve essere modificato, contattare l'Assistenza clienti Adobe.
* Il numero di livelli non può essere modificato dopo la configurazione della gerarchia.

>[!NOTE]
>
>Le modifiche alle gerarchie possono comportare un costo di servizio.

## homepage {#concept_0A3E416F1A064BA396B5FCEABFB7B0B4}

In Internet Explorer, la variabile indica se la pagina corrente è impostata come home page dell'utente.

<!-- 

homepage.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Questa variabile deve essere letta solo e non deve mai essere impostata.

Puoi leggere questi valori e copiarli in prop/evar, ma non modificarli mai. Questa variabile viene introdotta con la versione H .11 del file javascript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| hp | Y o N | Y | Traffico &gt; Tecnologia &gt; Home page |

## javaEnabled {#concept_F24A3536F1F0453DA214B16BAA5A6F67}

La variabile indica se Java è abilitato nel browser.

<!-- 

javaEnabled.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell'esecuzione di doplugins.

>[!NOTE]
>
>Questa variabile deve essere letta solo e non deve mai essere impostata.

Puoi leggere questi valori e copiarli in prop/evar, ma non modificarli mai. Questa variabile viene introdotta con la versione H .11 del file javascript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| v | Y o N | Y | Traffico &gt; Tecnologia &gt; Java |

## javascriptVersion {#concept_19E2C9F87BB24E69B911C0F5873CAA90}

La variabile indica la versione di javascript supportata dal browser.

<!-- 

javascriptVersion.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Questa variabile deve essere letta solo e non deve mai essere impostata.

Puoi leggere questi valori e copiarli in prop/evar, ma non modificarli mai. Questa variabile viene introdotta con la versione H .11 del file javascript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | Traffico &gt; Tecnologia &gt; Versione javascript |

La versione H .10 e versioni successive del file javascript rileva con precisione fino alla versione 1.7 (la versione più elevata al momento del rilascio H .10). Versioni precedenti del file javascript sono state rilevate solo alla versione 1.3

## linkName {#concept_1B2A3F56C9AD4C23A8A4331730EC2B8F}

The  variable is an optional variable used in [!UICONTROL Link Tracking] that determines the name of a custom, download, or exit link.

<!-- 

linkName.xml

 -->

The *`linkName`* variable is not normally needed because the third parameter in the *`tl()`* function replaces it.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro Debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 byte </td> 
   <td> pev2 </td> 
   <td> <p>Download dei file </p> <p>Collegamenti personalizzati </p> <p>Uscita dai collegamenti </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL Custom Links] fare riferimento a collegamenti che inviano dati di tracciamento. The *`linkName`* variable (or the third parameter in the *`tl()`* function) is used to identify the value that appears in the [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report. If *`linkName`* is not populated, the URL of the link appears in the report.

**Sintassi e valori possibili**{#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

There are no limitations on *`linkName`* outside of the standard variable limitations.

**Esempi** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**Impostazioni di configurazione**{#section_F15FF429FC274F708D50DF79D4668EA3}

Nessuno

**Insidie, domande e suggerimenti**{#section_170A78452A7340B5B229713AC1FB71FA}

* The *`linkName`* variable is replaced by the third parameter in the *`tl()`* function.

* If the *`linkName`* variable and the third parameter in the *`tl()`* function are blank, the full URL of the link (with the exception of the query string) appears in the report (even if the link is relative).

## linkType {#concept_7695692AF5D843E3B370F6D345E32964}

La variabile è una variabile opzionale utilizzata nel tracciamento dei collegamenti che determina quale rapporto viene visualizzato un nome o un URL di collegamento (collegamento personalizzato, scaricamento o uscita).

<!-- 

linkType.xml

 -->

The *`linkType`* variable is not normally needed because the second parameter in the *`tl()`* function replaces it.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro Debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Un carattere </td> 
   <td> pe = [lnk_ o | lnk_ d | lnk_ e] </td> 
   <td> <p>Download dei file </p> <p>Collegamenti personalizzati </p> <p>Uscita dai collegamenti </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

I collegamenti personalizzati inviano dati ad Analytics. The *`linkType`* variable (or the second parameter in the *`tl()`* function) is used to identify the report in which the link name or URL appears ( [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report).

For exit and download Links, the *`linkType`* variable is automatically populated depending on whether the link clicked is an exit or download link. A custom link may be configured to send data to any of the three reports with this variable or with the second parameter in the *`tl()`* function. By setting *`linkType`* to 'o,' 'e,' or 'd,' the *`linkName`* or link URL is sent to the [!UICONTROL Custom Links], [!UICONTROL Exit Links], or [!UICONTROL File Downloads] report respectively.

**Sintassi e valori possibili**{#section_18DB3A8083FB4F75B970055ED336DA4E}

The *`linkType`* variable syntax depends on whether you use XML or a query string.

Se si utilizza XML, la variabile può contenere solo un carattere singolo, ovverò o,''e,'o'd.'

```js
s.tl(this,’o’,’Link Name’);
```

If you are using the query-string `pe`, you need to use `lnk_d`, `lnk_e`, or `lnk_o`.

**Esempi** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**Impostazioni di configurazione**{#section_59738AD1B5E94294B8D36F4E772DEDB3}

Nessuno

**Insidie, domande e suggerimenti**{#section_F0D01DDE3FDA486C987162DA50A79C45}

* If *`linkType`* is not specified, custom links ('o') is assumed.

## List Props {#concept_83ED74232225431F83A796E22FFC75B4}

Le proprietà elenco sono un elenco delimitato di valori passati in una variabile, quindi segnalati come elementi di singole righe. Le proprietà elenco sono più comunemente implementate in pagine contenenti valori selezionabili dall'utente, ad esempio elementi elencati con caselle di controllo o pulsanti di scelta. Sono utili in qualsiasi circostanza in cui desiderate definire più valori in una variabile senza inviare più richieste di immagini.

<!-- 

list_props.xml

 -->

**Considerazioni**

* List props are enabled only on traffic variables ( [props](../../../implement/js-implementation/c-variables/page-variables.md#concept_0F10FA2DE69B4029A31EA5E9313AA254)).
* I percorsi e le correlazioni non possono essere abilitati per proprietà elenco.
* Analytics fornisce visite e visitatori univoci a quasi tutti i report, inclusi tutti i report prop dell'elenco.
* Le classificazioni sono supportate per le proprietà dell'elenco.
* Qualsiasi variabile di traffico personalizzata può diventare un prop dell'elenco. (Exceptions: [pageName](../../../implement/js-implementation/c-variables/page-variables.md#concept_5827B499DAC34B5D8445F9D9140CC328), [channel](../../../implement/js-implementation/c-variables/page-variables.md#concept_C7770B8C15724A99B10F8F468AF82D0D), and [server](../../../implement/js-implementation/c-variables/page-variables.md#concept_BF77952603BA454BAFC9A0A81D06A7D2).)

* Durante la definizione di valori duplicati nella stessa richiesta di immagine, le istanze non vengono deduplicate.

È possibile modificare un prop in un prop di amministrazione nella pagina Strumenti di amministrazione &gt; Suite di rapporti &gt; Variabili traffico abilitando Supporto elenco e quindi selezionando un delimitatore. I delimitatori più usati sono due punti, due punti, virgole o tubi. Il carattere di delimitazione può essere tecnicamente uno qualsiasi dei primi caratteri ASCII 127.

**Esempi di implementazione**{#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

Quando richiedete l'attivazione di proprietà elenco, indicate il carattere di delimitazione da utilizzare. After the *`s.prop`* of your choice is enabled, multiple values can be set in the variable as shown in the following examples:

Un prop dell'elenco delimitato da una barra, passando due valori:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

Un prop dell'elenco delimitato da una virgola che passa più valori:

```js
s.prop2="cerulean,vermilion,saffron"
```

È inoltre possibile inviare proprietà elenco con un singolo valore:

```js
s.prop3="Single value"
```

Il delimitatore può essere modificato in qualsiasi momento. Tuttavia, l'implementazione deve corrispondere al nuovo carattere di delimitazione. Se non si utilizza il delimitatore corretto, il valore del prop dell'elenco viene trattato come un singolo elemento di riga concatenata nei report.

Poiché una proprietà dell'elenco è ancora una variabile traffico, è soggetta a limitazioni di variabile traffico. Le proprietà elenco sono limitate a 100 byte di dati e sono influenzate dalle impostazioni di sensibilità alle maiuscole/minuscole.

## List Variable {#concept_AC42F2D69B674C02A484137CE5B4E687}

Noto anche come Var elenco. Analogamente alla funzione Elenco proprietà, le variabili elenco consentono più valori all'interno della stessa richiesta di immagine. Inoltre, agiscono in modo simile alle evar, che rimangono oltre la richiesta dell'immagine su cui sono stati definiti. Potete utilizzare queste variabili per vedere la causa ed effetto tra più elementi su una singola pagina, come elenchi di prodotti, elenchi di desideri, elenchi di miglioramenti alla ricerca o elenchi di annunci visualizzati.

<!-- 

listN.xml

 -->

**Considerazioni**

* Le variabili elenco memorizzano i valori specifici facendo riferimento al cookie visitorid nel browser del visitatore.
* Un limite di 250 valori massimi viene archiviato contemporaneamente per visitatore. Se vengono superati i 250 valori per visitatore, vengono usati gli ultimi 250 valori. La scadenza di tali valori si basa sulla scadenza configurata per la variabile.
* Ogni valore delimitato può contenere un massimo di 255 caratteri (o meno se utilizzano caratteri multibyte). Si tratta della lunghezza massima di ogni elemento.
* Non esiste alcun limite al numero di caratteri all'interno di questa variabile. L'unica eccezione a questa limitazione è rappresentata dai browser Internet Explorer precedenti, che impongono una limitazione di 2083 caratteri per tutte le richieste URL.
* Sono disponibili tre variabili elenco per suite di rapporti.
* L'utilizzo di Variabili elenco richiede il codice H 23 o superiore.
* Le variabili elenco possono essere classificate.
* Se i valori duplicati sono definiti nella stessa richiesta di immagine, le variabili dell'elenco deduplicano tutte le istanze di tali valori.
* Le variabili elenco più granulari possono essere segmentate a livello di hit (o visualizzazione pagina). Se hai un var di elenco con tre valori nella stessa richiesta di immagine, tutte le regole di segmento che corrispondono a un valore verranno estratte in reporting. Viceversa, se viene definita una regola esclusiva che corrisponde a un singolo valore, tutti e tre i valori sono esclusi.

**Configurazione** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

Puoi accedere alla configurazione in Admin Console e aggiornarla senza che Adobe Client Care debba essere coinvolto:

1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**
1. Seleziona la suite di rapporti.
1. Click  **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

* **Nome**: Ogni valore delimitato può contenere un massimo di 255 caratteri (o meno se utilizzano caratteri multibyte). Si tratta della lunghezza massima di ogni elemento.
* **Delimitatore valore**: Il carattere utilizzato per separare i valori nell'elenco Var. Generalmente si tratta di caratteri quali virgole, due punti, tubi o qualcosa di simile.

   >[!NOTE]
   >
   >I caratteri multibyte non sono supportati come delimitatori nelle variabili elenco. Il delimitatore deve essere un singolo byte.

* **Scadenza**: Simile alla scadenza evar, questo determina il tempo che può verificarsi tra l'elenco dell'elenco e l'evento di conversione affinché sia correlato.

   * **A una visualizzazione pagina o a un livello di visita**: Gli eventi di successo oltre la visualizzazione della pagina o la visita non rimanderanno ad alcun valore all'interno dell'elenco Var.
   * **In base a un periodo di tempo, ad esempio giorno, settimana, mese, ecc. Gli eventi di successo oltre il periodo di tempo specificato non rimanderanno ad alcun valore all'interno dell'elenco Var.** È possibile definire anche un numero personalizzato di giorni.
   * **Eventi di conversione specifici**: Qualsiasi altro evento di successo che viene attivato dopo l'evento specifico designato non rimanda ad alcun valore all'interno dell'elenco Var.
   * **Mai**: Qualsiasi quantità di tempo può passare tra l'evento Elenco e l'evento success.

* **Allocazione**: Questa impostazione determina il modo in cui gli eventi di successo dividono il credito tra valori:

   * **Completo**: Tutti i valori delle variabili definiti prima della scadenza della variabile ottengono un credito completo per gli eventi di successo.
   * **Lineare**: Tutti i valori delle variabili definiti prima della scadenza della variabile ottengono credito diviso per gli eventi di conversione.
   * I valori delle variabili non vengono mai sovrascritti, ma aggiunti ai valori che ottengono credito per gli eventi di successo.

* **Valori massimi**: Indica il numero di valori attivi consentiti per la variabile dell'elenco. Ad esempio, se è impostato su 3, vengono salvati solo gli ultimi 3 valori acquisiti e tutti i valori precedenti acquisiti. Tenere presente che se più valori per la stessa var dell'elenco vengono inviati sullo stesso hit e hai limitato con valori massimi, ogni valore avrà la stessa marca temporale e non viene garantito il valore salvato.

   Un limite di 250 valori massimi viene archiviato contemporaneamente per visitatore. Se vengono superati i 250 valori per visitatore, vengono usati gli ultimi 250 valori. La scadenza di tali valori si basa sulla scadenza configurata per la variabile.

   L'impostazione Valori massimi è utile per limitare l'attribuzione a un numero specifico di valori. Ad esempio, se un elenco var è impostato su «A, B, C» nella prima pagina di una visita, e quindi su «X, Y, Z» nella pagina successiva, l'attribuzione viene distribuita a questi sei valori in base all'allocazione. Se desiderate limitare l'attribuzione solo a "X, Y, Z", potete impostare i valori massimo su tre.

To set up or edit List Vars, go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

**Esempi di implementazione**{#section_564AFE6A2F524BFEB372EC0F7FEBA656}

Ciascuno degli esempi seguenti utilizza una virgola per il delimitatore del valore.

**Definizione di un singolo valore all'interno di un elenco di variabili:**

```js
s.list1="Cat";
```

**Superamento di più valori:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Attribuzione delle entrate a un elenco di variabili:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

Questo risultato mostrerebbe tre elementi con $ 50 ciascuna delle entrate. (Annuncio banner principale; Barra laterale laterale; e Campaign Campaign 1.) Tenete presente che il totale di questo rapporto deduplica i ricavi, quindi il totale riflette anche $ 50.

**Entrate collegate a una var elenco impostata più volte durante una visita:**

**Allocazione**: Completo

**Scadenza**: Visita

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s. events/s. products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Pagina 1 </td> 
   <td colname="col2"> <code> s. list 1 =» value 1, value 2, value 3»; </code> </td> 
   <td colname="col3"> (non impostato) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pagina 2 </td> 
   <td colname="col2"> <code> s. list 1 =» value 4, value 5, value 6»; </code> </td> 
   <td colname="col3"> <p> <code> s. events =» purchase»; </code> </p> <p> <code> s. products =»; product; 1; 200» </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Risultato**: Tutti i valori impostati nell'elenco var 1 in qualsiasi momento durante la visita (valore 1, valore 2, valore 3, valore 4, valore 5, valore 6) ottieni il credito completo per l'acquisto.

## maxDelay {#concept_B355038C3B094BB68C0DC6C80F9FE5B0}

La variabile s. maxdelay viene utilizzata principalmente nelle integrazioni Genesis DFA per determinare il periodo di timeout nel contatto dell'host DFA. Se Adobe non riceve una risposta dai server DFA entro il periodo specificato impostato nella variabile, la connessione viene interrotta e i dati vengono elaborati normalmente. Implementa questa variabile se ti interessa il tempo di risposta di DFA su ciascuna pagina. Si consiglia di sperimentare con questo valore per determinare il periodo di timeout ottimale.

<!-- 

maxDelay.xml

 -->

**Esempio di implementazione**

```
s.maxDelay="750";
```

**Proprietà**

* Questa variabile è una metrica evento opzionale compilata tramite javascript implementata sul sito.
* Se l'host DFA non risponde entro il periodo di tempo specificato, l'evento designato alle esecuzioni Timeout (assegnato tramite la procedura guidata di integrazione Genesis).
* Questa variabile può contenere solo un valore numerico.
* Il tempo specificato è espresso in millisecondi.
* L'aumento del tempo di attesa raccoglie più dati DFA, ma aumenta anche il rischio di perdere dati hit Analytics.

   Losing Analytics hit data would occur when the user navigates away from the page during the *`s.maxDelay`* period.

* Diminuendo il tempo di attesa ridurrete il rischio di perdere i dati hit di Analytics, ma è possibile ridurre la quantità di dati DFA inviati con i dati di hit.

   Losing DFA integration data would occur when the *`s.maxDelay`* period does not accommodate enough time for the DFA host to respond.

>[!NOTE]
>
>Adobe non ha il controllo sul tempo di risposta di DFA. Se riscontri problemi coerenti anche dopo aver aumentato il periodo di ritardo massimo a un periodo di tempo ragionevole, consulta l'amministratore dell'account DFA della tua organizzazione.

## mediaLength {#concept_F52B1670122C4461824223E525307060}

La variabile specifica la lunghezza totale del supporto in corso di riproduzione.

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro Debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nessuna dimensione massima per l'intera richiesta pev 3: le dimensioni sono limitate al limite di lunghezza URL del browser. </td> 
   <td> pev3 </td> 
   <td> Tempo trascorso sul video; <p>Segmenti video visualizzati </p> </td> 
   <td> Nessuno </td> 
  </tr> 
 </tbody> 
</table>

**Sintassi e valori possibili**{#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

** Metodo di tracciamento automatico: **

If using [!UICONTROL s.Media.autoTrack], the [!UICONTROL mediaLength] variable does not need to be implemented explicitly. Viene determinato automaticamente da appmeasurement per il codice javascript.

**Metodo di tracciamento manuale:**

Sintassi:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Esempi** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Insidie, domande e suggerimenti**{#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* You must call the media tracking methods only if the player cannot be tracked using [!UICONTROL s.Media.autoTrack] = true.
* If not tracking using [!UICONTROL autoTrack], be sure to set the length in seconds.

## mediaName {#concept_A4CB1782DE244C23BA6CBB5E806DDE6A}

Questa variabile specifica il nome dell'elemento video o multimediale.

<!-- 

mediaName.xml

 -->

It is only available via the [!UICONTROL Data Insertion API] and [!UICONTROL Full Processing Data Source].

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 64 KB | pev3 | Video; Next Video Flow; Flusso video precedente; Segmenti video visualizzati; Tempo trascorso sul video | Nessuno |

**Sintassi e valori possibili**{#section_F97A2253BBD24FEBBC225F233A319F5D}

**Metodo di tracciamento automatico:**

If using [!UICONTROL s.Media.autoTrack], the *`mediaName`* variable does not need to be implemented explicitly. Viene determinato automaticamente da appmeasurement per il codice javascript.

**Metodo di tracciamento manuale:**

Sintassi:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Esempi** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Insidie, domande e suggerimenti**{#section_941A445BB52E4063B0F6920E61BB90DE}

* You must call the media tracking methods only if player cannot be tracked using [!UICONTROL s.Media.autoTrack] = true.
* Questa variabile viene memorizzata come variabile di testo mysql, opposta a VARCHAR (100).

## mediaPlayer {#concept_1932756C093B4B2FBA0484E5A58EF927}

Questa variabile specifica il lettore utilizzato per utilizzare un elemento video o un elemento multimediale.

<!-- 

mediaPlayer.xml

 -->

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 Byte | pev3 | Lettori video | Nessuno |

**Sintassi e valori possibili**{#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**Metodo di tracciamento automatico:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Metodo di tracciamento manuale:**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Esempi** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Insidie, domande e suggerimenti**{#section_0020E031338F4A4880B9AC5B9A85BEF5}

È necessario chiamare i metodi di tracciamento multimediali solo se il lettore non può essere tracciato utilizzando s. Media. autotrack = true.

## mediaSession {#concept_19E6C850C3244CB6973140709BDCB0B9}

Questa variabile specifica i segmenti di una risorsa video o multimediale consumata.

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro Debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 Byte </td> 
   <td> pev3 </td> 
   <td> Tempo trascorso sul video <p>Segmenti video visualizzati </p> </td> 
   <td> Nessuno </td> 
  </tr> 
 </tbody> 
</table>

**Sintassi e valori possibili**{#section_9A63266633C4427CB4A6549E4D887B85}

**Metodo di tracciamento automatico:**

If using [!UICONTROL s.Media.autoTrack], the *`mediaName`* does not need to be implemented explicitly. Verrà determinato automaticamente da appmeasurement per il codice javascript.

**Metodo di tracciamento manuale:**

Sintassi:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**Esempi** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Insidie, domande e suggerimenti**{#section_1BCEB037AB724B6EBE87420BD3604B88}

You must call the media tracking methods only if player cannot be tracked using [!UICONTROL s.Media.autoTrack] = true.

## Media.trackEvents {#concept_B1C5FF6C437949EBA5D52040AC6BB6D9}

La variabile identifica gli eventi da inviare con un hit di supporto.

<!-- 

media_trackEvents.xml

 -->

It is only applicable with JavaScript and [!UICONTROL ActionSource].

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | s. Media. trackevents = "None" |

**Sintassi e valori possibili**{#section_66A978EF56914BEAAE73359A268A1B4A}

Nomi evento, ad esempio event 1 o purchase.

**Esempi** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents=”event1,purchase”
```

**Insidie, domande e suggerimenti**{#section_030B11C64EE84D46A85CA550DB732D28}

Make sure to populate [!UICONTROL trackVars] with "events" whenever this variable is populated.

## Media.trackVars {#concept_4350CA9A892148AE93C8133AB3B4BEA4}

La variabile identifica le variabili da inviare con un hit di supporto.

<!-- 

media_trackVars.xml

 -->

It is only applicable with JavaScript and [!UICONTROL ActionSource].

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | s. Media. trackvars = "None" |

**Sintassi e valori possibili**{#section_7374684A7EB34AE685E8C40A66CFD289}

Variable names such as [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`*, and so forth.

**Esempi** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars=”prop2,events,eVar3”
```

**Insidie, domande e suggerimenti**{#section_615AE1B696124B00B78F651B03813EAB}

* Even if eVar3 is specified in [!UICONTROL trackVars], it is sent with the media hit.

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

La variabile controlla l'ordine in cui i cookie e gli ID utente iscritto vengono utilizzati per identificare i visitatori.

<!-- 

mobile.xml

 -->

See [Mobile network protocols](../../../implement/js-implementation/c-additional-libraries/network-protocols.md#concept_2425537FC9CB45DD868B5FA2298B6CAC).

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | /5/ o /1/ nel percorso dell'URL dell'immagine | N/D | Nessuno |

**Sintassi e valori possibili**{#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**Insidie, domande e suggerimenti**{#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Use cross-visitor identification to mitigate possible spikes in visitor traffic when using the *`s.mobile`* variable with the JavaScript cookie implementation.

## pageName {#concept_5827B499DAC34B5D8445F9D9140CC328}

La variabile contiene il nome di ogni pagina sul sito.

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro Debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 byte </td> 
   <td> pageName </td> 
   <td> <p>Pagine </p> <p>Paths (Percorsi) </p> </td> 
   <td> URL pagina </td> 
  </tr> 
 </tbody> 
</table>

The *`pageName`* variable should be populated with a value that business users recognize. In most cases the *`pageName`* value is not the URL or the path to the file. Common *`pageName`* values include names such as "Home Page," "Checkout," "Purchase Thank you," or "Registration."

Attenzione a non consentire l'apparizione di trattini nuova riga, -em o -en, o di qualsiasi carattere HTML nel nome della pagina e in altre variabili. Alcuni browser inviano nuovi caratteri, mentre altri no, per cui i dati in Analytics possono essere suddivisi tra due nomi di pagina apparentemente identici. Molti elaboratori di testi e client e-mail convertono automaticamente il trattino in un trattino -en o -em durante la digitazione. Poiché i trattini -en e -em sono caratteri non validi nelle variabili di Analytics (caratteri ASCII con codici superiori a 127), Analytics non registra il nome della pagina contenente il carattere non valido e mostra l'URL.

If *`pageName`* is left blank, the URL is used to represent the page name. Leaving *`pageName`* blank is often problematic because the URL may not always be the same for a page `www.mysite.com` and `mysite.com` are the same page with different URLs).

**Sintassi e valori possibili**{#section_7A61EE70F1A84D26B414404998C84BA8}

The *`pageName`* variable should contain a useful identifier for business users of Analytics.

```js
s.pageName="page_name"
```

There are no limitations on *`pageName`* outside of the standard variable limitations.

**Esempi** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**Impostazioni di configurazione**{#section_58CBC68C805344A999EB47455FEBA8D5}

Administrators have the ability to change the visible page name in Analytics with the [!UICONTROL Name Pages] tool, which is potentially dangerous and may negatively affect your reports. Please contact Adobe Customer Care before using the [!UICONTROL Name Pages] tool.

**Insidie, domande e suggerimenti**{#section_BB41DC9682C34385B9CAA80D5257C113}

Make sure the *`pageName`* doesn't contain illegal characters.

## pageType {#concept_F67870238EF74491B5D3909A33CDB985}

La variabile viene utilizzata solo per designare una pagina Errore 404 pagina non trovato.

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro Debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 20 byte </td> 
   <td> pageType </td> 
   <td> Paths &gt; Pages &gt; Pages <p>Non trovato </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. Set up the *`pageType`* variable on the error page exactly as shown below.

Non utilizzate la variabile nome pagina in 404 pagine di errore. The *`pageType`* variable is only used for the 404 Error page.

Nella maggior parte dei casi, la pagina Errore 404 è una pagina statica codificata come hardcoded. In questi casi, è importante che il riferimento al file. JS sia impostato su un percorso/percorso appropriato o relativo.

**Sintassi e valori possibili**{#section_C1C59968226446559B05F6EE7374D525}

The only allowable value of *`pageType`* is "errorPage" as shown below.

```js
s.pageType="errorPage"
```

**Esempi** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Impostazioni di configurazione**{#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

Nessuno

**Insidie, domande e suggerimenti**{#section_943681AB01FE47BEAC72E93CB60C53C8}

To capture other server-side errors (such as 500 errors), use a prop to capture the error message and put "`500 Error: <URL>`" where `<URL>` is the URL requested, in the *`pageName`* variable. By following this course of action, you can use [!UICONTROL Pathing] reports to see which paths caused users to generate 500 errors. Il prop spiega quale messaggio di errore viene fornito dal server.

## pageURL {#concept_A15F710CD0174297A2286BF3E7452113}

La variabile sostituisce l'URL effettivo della pagina.

<!-- 

pageURL.xml

 -->

In alcuni rari casi, l'URL della pagina non è l'URL che si desidera riportare in Analytics.

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro Debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nessun limite * </td> 
   <td> <p>G </p> </td> 
   <td> Traffico &gt; Segmentazione &gt; Percorsi pagine più popolari </td> 
   <td> URL della pagina </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Although Adobe allows *`pageURL`* values up to 64k, some browsers impose a size limit on the URL of image requests. To prevent truncation of other data, page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter.

**Sintassi e valori possibili**{#section_22AF3BF7C2F743549967B0C760A095C0}

The *`pageURL`* variable must be a valid URL, with a valid protocol. Il dominio deve essere visualizzato in minuscolo prima di essere compilato nei rapporti e la stringa di query può essere eliminata, a seconda delle impostazioni di Analytics.

```js
s.pageURL="proto://domain/path?query_string"
```

Come URL della pagina sono consentiti solo caratteri compatibili con l'URL.

>[!NOTE]
>
>It is strongly advised that you contact your Adobe consultant or Customer Care before using the *`pageURL`* variable for custom purposes.

**Esempi** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**Impostazioni di configurazione**{#section_A8F77DAD88164528ACC5C16C066B47DF}

Nessuno

## plugins {#concept_B570F04FEDA34EB7A9826687FE633953}

La variabile, in browser Netscape e Mozilla, elenca i plug-in installati nel browser.

<!-- 

plugins.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Questa variabile deve essere letta solo e non deve mai essere impostata.

Puoi leggere questi valori e copiarli in prop/evar, ma non modificarli mai. Questa variabile viene introdotta con la versione H .11 del file javascript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| p | Plug-in riconosciuti | Plug-in Scheda IE; Quicktime Plug-in 7.1.6; Plug-in predefinito Mozilla; Rilevatore applicazione itunes; Adobe Acrobat; Contenitore plug-in generale activetouch; Shockwave Flash; Microsoft Office 2003; Java (TM) Platform SE 6 U 1; Libreria Dynamic Link di Windows Media Player; Microsoft® DRM; | Traffico &gt; Tecnologia &gt; Plugin |

## products {#concept_A4007F6307E4419DAA65E1668A8FEBA2}

La variabile viene utilizzata per tenere traccia dei prodotti e delle categorie di prodotti, nonché per quantità di acquisto e prezzo di acquisto. I prodotti vengono generalmente impostati insieme a un evento carrello o a un evento.

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>In January of 2016, we updated the logic that sets the *`prodView`* event automatically, which happens when there is a *`product`* but no *`event`*. This update may cause an increase in *`prodView`* events. *`prodViews`* aumenteranno solo nei casi in cui:
>
>1. The events variable contains nothing but an unrecognized event, such as *`shoppingCart`* or *`cart`*, which are not valid events.
   >
   >
1. *`products`* La variabile non è vuota.
>
>
A possible side effect is that merchandising eVars triggered by *`prodView`* events could be associated with an empty *`product`*, but only if the *`product list`* contains only an invalid product (such as a semicolon with no product listed).

The *`products`* variable tracks how users interact with products on your site. Ad esempio, la variabile "products" può tenere traccia del numero di volte che un prodotto viene visualizzato, aggiunto al carrello, estratto e acquistato. Può inoltre tenere traccia dell'efficacia relativa delle categorie di merchandising sul sito. Gli scenari di seguito sono comuni per l'utilizzo della variabile products.

The *`products`* variable should always be set in conjunction with a success event.

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro Debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>The " <span class="wintitle"> products </span>" string has a maximum size of 64k. </p> </td> 
   <td> products </td> 
   <td> Variabile   <p>Categorie (facoltativo) </p> <p>Revenue (facoltativo) </p> <p>Unità (facoltativo) </p> <p>Eventi personalizzati (facoltativo) </p> <p>Evar (facoltativo) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Sintassi** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| Campo | Definizione |
|---|---|
| Categoria | Contiene la categoria di prodotto associata. Nella versione 15, i prodotti possono essere associati a più categorie che correggono un limite presente nella versione 14. Se in precedenza non si registra una categoria di prodotto, si consiglia di iniziare a compilare questo campo per le suite di rapporti che si trovano nella versione 15. |
| Prodotto | (Obbligatorio) L'identificatore utilizzato per tenere traccia di un prodotto. This identifier is used to populate the [!UICONTROL Products] report. Assicuratevi di usare lo stesso identificatore nel processo di checkout. |
| Quantità | Numero di unità acquistate. This field must be set with a [!UICONTROL purchase] event to be recorded. |
| Prezzo | Si riferisce al costo combinato della quantità totale acquistata (unità x singoli unità di prezzo), non al singolo prezzo. This field must be set with a [!UICONTROL purchase] event to be recorded. |
| Eventi | Eventi di valuta associati al prodotto specificato. See [Product-Specific Currency Events](../../../implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C) and [Order-Wide Currency Events](../../../implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0). |
| Evar | Valori evar per merchandising associati a un prodotto specifico. See [Merchandising Variables](/help/components/c-variables/c-merch-variables/var-merchandising.md). |

The values included in the *`products`* variable are based on the type of event you are recording. Il delimitatore categoria/prodotto (;) è richiesto come segnaposto quando si omette Categoria. Altri delimitatori sono richiesti solo se sono necessari per distinguere il parametro incluso, come mostrato negli esempi di questa pagina.

**Impostazione di prodotti con eventi non di acquisto**{#section_D5E689D4AAE941EC851CA9B98328A4DE}

The *`products`* variable must be set in conjunction with a success event.

**Impostazione dei prodotti con un evento di acquisto**{#section_618AAC96E7B541A7AABAA028E5F4E5C3}

*`purchase`* The event should be set on the final confirm ("Thank You! ") del processo dell'ordine. The product name, category, quantity, and price are all captured in the *`products`* variable. Although the *`purchaseID`* variable is not required, it is strongly recommended in order to prevent duplicate orders.

**Eventi valuta specifici per il prodotto**{#section_F814DF053C0D463A97DA039E6323720C}

If a currency event receives a value in the *`products`* variable instead of the events variable, it applies only to that value. Questa funzione è utile per tenere traccia degli sconti specifici per i prodotti, per la spedizione dei prodotti e per valori simili. Ad esempio, se avete configurato l'evento 1 per tenere traccia della spedizione del prodotto, un prodotto con una spesa di spedizione "4.50" potrebbe essere simile a quanto segue:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

In questo esempio, il valore di 4.50 è associato direttamente al prodotto «Running Shoes». Se aggiungete l'evento 1 al rapporto prodotti, vedrete «4.50» elencato per l'elemento «Running Shoes». Simile a Prezzo, questo valore deve riflettere il totale della quantità indicata. Se avete 2 elementi con una spesa di spedizione pari a 4.50 ciascuna, l'evento 1 deve essere "9.00".

**Eventi di valuta a livello di singolo ordine**{#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

If a currency event receives a value in the events list instead of the *`products`* variable, it applies to all products in the *`products`* variable. Questo è utile per monitorare sconti a livello di ordine, spedizione e valori simili, senza modificare il prezzo del prodotto o tracciarlo separatamente nell'elenco dei prodotti.

Ad esempio, se avete configurato l'evento 10 per contenere gli sconti a livello di ordine, un acquisto con uno sconto del 10% potrebbe essere simile a quanto segue:

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

Nei rapporti sull'evento valuta, il totale del report rappresenta il totale dell'evento deduplicato (in questo esempio, la quantità totale di sconti durante il periodo di reporting), non la somma dei valori dell'evento per ogni prodotto. Ad esempio, visualizzerete «9.95» elencato per «Running Shoes» (Scarpe esecuzione) e «Running Calks» (Esegui calze), e il totale sarà anche «9.95».

>[!NOTE]
>
>if a value for the same Numeric/Currency Event is specified in the *`products`* variable and in the *`events`* variable, the value from the *`events`* is used.

**Insidie, domande e suggerimenti**{#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* The *`products`* variable should always be set in conjunction with a [!UICONTROL success] event (events). If no [!UICONTROL success] event is specified, the default event is [!UICONTROL prodView].

* Elimina tutte le virgole e i punto e virgola dai nomi di prodotto e categoria prima della compilazione dei prodotti.
* Rimuovete tutti i caratteri HTML (simboli registrati, marchi registrati e così via).
* Rimuovi i simboli di valuta ($) dal prezzo.

**Esempi** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s. products =» Category; ABC 123» </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. products =» Category 2; ABC 123; ABC 456» </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. products =» Category 3; ABC 123; 1; 10» </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. products =» Category; ABC 123; 1; 10; ABC 456; 2; 19.98» </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. events =» event 1» </code> <p> <code> s. products = "Category; ABC 123; ; ; event 1 = 1.99 " </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. events =» event 1» </code> <p> <code> s. products = "Category; ABC 123; 1; 10; event 1 = 1.99 " </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. events =» event 1» </code> <p> <code> s. products = "Category; ABC 123; 1; 10; event 1 = 1.99; ABC 123; 2; 19.98; event 1 = 1.99 " </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. events =» event 1, event 2» </code> <p> <code> s. products = "Category; ABC 123; 1; 10; event 1 = 1.99 | event 2 = 25 " </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. events =» event 1, event 2» </code> <p> <code> s. products = "Category; ABC 123; 1; 10; event 1 = 1.99 | event 2 = 25; evar 1 = 2 Day Shipping " </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. events =» event 1, event 2» </code> <p> <code> s. products = "Category; ABC 123; 1; 10; event 1 = 1.99 | event 2 = 25; evar 1 = 2 Day Shipping | evar 2 = 3 Stars " </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. events =» event 1, event 2» </code> <p> <code> s. products = "Category; ABC 123; 1; 10; event 1 = 1.99 | event 2 = 25; evar 1 = 2 Day Shipping; ABC 456; 2; 19.98; event 1 = 1.99 | event 2 = 100; evar 1 = Shipping Shipping " </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. events =» event 1, event 2, event 3» </code> <p> <code> s. products = "Category; ABC 123; 1; 10; event 1 = 1.99 | event 2 = 25; evar 1 = 2 Day Shipping; ABC 456; 2; 19.98; event 1 = 1.99 | event 2 = 100; evar 1 = Ground Shipping; ; ; ; event 3 = 2.9; evar 3 = 20% off " </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s. events =» event 1, event 2, event 3 = 9.95» </code> <p> <code> s. products = "Category; ABC 123; ; ABC 456; 2; 19.98; event 1 = 1.99 | event 2 = 100; evar 1 = Ground Shipping; ; ; ; event 3 = 2.9; evar 3 = 20% off " </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## propN {#concept_0F10FA2DE69B4029A31EA5E9313AA254}

Property ( [!UICONTROL prop]) variables are used for building custom reports within the [!UICONTROL Traffic Module].

<!-- 

propN.xml

 -->

La variabile prop può essere utilizzata come contatore (per calcolare il numero di volte in cui viene inviata una visualizzazione di pagina), per i rapporti percorsi o nei rapporti di correlazione.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | c 1-c 75 | Traffico personalizzato | "" |

**Sintassi e valori possibili**{#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

There are no limitations on [!UICONTROL property] variables outside of the standard variable limitations.

**Esempi** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Impostazioni di configurazione**{#section_25FDEB6ECA8242A2A44EE540C083078A}

Contact Adobe Customer Care about showing [!UICONTROL Visit], [!UICONTROL Visitor], and [!UICONTROL Path] metrics for [!UICONTROL prop] variables.

## purchaseID {#concept_21937434E63F413CB469007623B933AE}

Viene utilizzato per tenere un ordine di conteggio più volte nel reporting.

<!-- 

purchaseID.xml

 -->

Whenever the [!UICONTROL purchase] event is used on your site, you should use the *`purchaseID`* variable.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 20 byte | purchaseID | Conversione &gt; Acquisti &gt; Conversione ricavi | "" |

When a visitor purchases an item from your site, *`purchaseID`* is populated on the "Thank You" page at the same place the [!UICONTROL purchase] event is fired. If the *`purchaseID`* is populated, the products on the "Thank You" page are counted only once per *`purchaseID`*. Questo è importante perché molti visitatori del sito salveranno i "Ringraziamenti" o "Pagina di conferma" per i propri scopi. The *`purchaseID`* keeps purchases from being counted each time the page is viewed.

In addition to keeping the purchase data from being counted twice, the *`purchaseID`*, when used, keeps all conversion data from being double counted in reports.

**Sintassi e valori possibili**{#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

The *`purchaseID`* must be 20 characters or fewer, and be standard ASCII.

**Esempi** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Impostazioni di configurazione**{#section_1808631C96674380BF9C4A6D9A2C568E}

Nessuno

**Insidie, domande e suggerimenti**{#section_F5D010F234ED43F19AD1FCD2CD64E060}

The *`purchaseID`* variable allows all conversion variables on the page to be counted only once in reports.

## referrer {#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B}

La variabile può essere utilizzata per ripristinare le informazioni di riferimento perdute.

<!-- 

referrer.xml

 -->

I reindirizzamenti lato server e javascript vengono spesso utilizzati per indirizzare i visitatori verso posizioni corrette. Tuttavia, quando un browser viene reindirizzato, l'URL di provenienza originale viene perso.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 255 byte | R | Traffic &gt; Finding Methods Conversion &gt; Finding Methods | document. referrer |

Molte aziende utilizzano reindirizzamenti in molti luoghi nei propri siti Web. Ad esempio, un visitatore può essere inviato tramite un reindirizzamento da un risultato di ricerca a pagamento del motore di ricerca. Quando un browser viene reindirizzato, il referente viene spesso perso. The *`referrer`* variable may be used to restore the original *`referrer`* value on the first page after a redirect. The *`referrer`* may be populated server-side, or via JavaScript from the query string.

Affinché Analytics possa registrare un referente, deve essere "ben formata", ovvero deve seguire il formato URL standard, con un protocollo e la posizione appropriata.

**Sintassi e valori possibili**{#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

Only URL-compatible values should be in the *`referrer`*. Verificate che la stringa sia codificata URL (senza spazi).

**Esempi** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**Impostazioni di configurazione**{#section_7AAEF28A7CBC446984F32C0659EFBF8D}

Nessuno

**Insidie, domande e suggerimenti**{#section_B42BF7FBA1094FF9805707FEA810CFE1}

The *`referrer`* must look like a standard URL and include a protocol.

## resolution {#concept_8CBDDBE710744A3AA09E6B1E1519BF30}

La variabile indica la risoluzione monitor del visitatore che visualizza la pagina Web.

<!-- 

resolution.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Questa variabile deve essere letta solo e non deve mai essere impostata.

Puoi leggere questi valori e copiarli in prop/evar, ma non modificarli mai. Questa variabile viene introdotta con la versione H .11 del file javascript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| s | Wxh | 1680x1050 | Traffico &gt; Tecnologia &gt; Risoluzione monitor |

## s_objectID {#concept_48B50DE6B7E546EBB4D187033F1CAF2B}

The  variable is a global variable that should be set in the [!UICONTROL onClick] event of a link.

<!-- 

s_objectID.xml

 -->

By creating a unique object ID for a link or link location on a page, you can either improve visitor activity tracking or use [!UICONTROL Activity Map] to report on a link type or location, rather than the link URL.

>[!NOTE]
>
>A trailing semicolon (;) is required when using s_objectID with [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 Byte | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | L'URL assoluto di un collegamento selezionato |

There are three common reasons to use *`s_objectID`*:

* Per aggregare l'attività dei visitatori che si modifica spesso durante un giorno.
* To separate link activity that [!UICONTROL Activity Map] combines.
* To improve the accuracy of [!UICONTROL Activity Map] data reporting.

**Aggregazione di clic su collegamenti altamente dinamici**{#section_BA730A0393B149DDBCAA272C3C23A1C5}

If your site is highly dynamic, and links on some pages change throughout the day, *`s_objectID`* may used to identify the location of a link on the page. If *`s_objectID`* is set to "top left 1" or "top left 2," which represents the first link in the top left of the page for example, then all links that appear in that location (or that have *`s_objectID`* set to the same value) are reported together with visitor click map. If you don't use *`s_objectID`*, you see the number of times that a specific link was clicked, but you lose insight into how all the other links in that location were used by visitors to your site.

**Clic diversi clic**{#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

If the *`pageName`* variable on your site is used to show the section or template a visitor is viewing, rather than the specific page the visitor is viewing, you may want to use *`s_objectID`* to separate links that appear on multiple versions of that page template. Ad esempio, se disponete di una pagina modello per tutti i prodotti sul sito, è probabile che vi sia un collegamento alla pagina principale e a una casella di ricerca da tale modello su tutte le pagine. If you want to see how those links are used on an individual product basis (rather than a template basis), you can populate *`s_objectID`* with a product specific value such as "prod 123789 home page" or "prod 123789 search." Once completed, [!UICONTROL Activity Map] reports on those links at an individual product basis.

**Miglioramento[!UICONTROL Activity Map]precisione**{#section_08B3406821294DCCABEEB99C90CF5C52}

In alcuni casi, i browser diversi da Internet Explorer, Firefox, Netscape, Opera e Safari non vengono segnalati. Anche se si tratta di una percentuale ridotta, è utile per alcuni clic e altre metriche. Use *`s_objectID`* within links to uniquely identify the addresses the browser reporting issue. The following is an example of how to update your links to use *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**Sintassi e valori possibili**{#section_85841DF9F06A4680953D9B2A884A1A5A}

s_ objectid può contenere qualsiasi identificatore di testo.

```js
s_objectID="unique_id" 
```

There are no limitations on *`s_objectID`* outside of the standard variable limitations.

**Esempi** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**Impostazioni di configurazione**{#section_95396657D55B41ECB66B83D0534EA827}

Nessuno

## server {#concept_BF77952603BA454BAFC9A0A81D06A7D2}

La variabile viene utilizzata per mostrare il dominio di una pagina Web (per mostrare quali domini arrivano) o il server che distribuisce la pagina (per un riferimento rapido al bilanciamento del carico).

<!-- 

server.xml

 -->

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | server | Server | "" |

If your site has more than one domain serving the same content, the *`server`* variable can be used to track which of those domains visitors are using. Il seguente javascript comporrà il dominio della pagina nella variabile server.

```js
s.server=window.location.hostname
```

Se utilizzate la variabile server per fornire una guida rapida al bilanciamento del carico, potete inserire un nome o un numero server nella variabile server. Consultate il seguente esempio:

```js
s.server="server 14"
```

While the [!UICONTROL Most Popular Servers] report may be used as a load balancing quick reference, it is not a precise measure of server load. Ad esempio, il traffico sul retro non aumenta il carico del server, ma viene visualizzato nei report. Il rapporto non mostra quali server distribuire immagini o file di grandi dimensioni.

**Sintassi e valori possibili**{#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

There are no limitations on the *`server`* variable outside of the standard variable limitations.

**Esempi** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**Impostazioni di configurazione**{#section_969DB379D5BD469FBEE8D505D3000E49}

Nessuno

**Insidie, domande e suggerimenti**{#section_42A28F9B01574F38891D9D54B411D8FE}

The *`server`* variable can be used to show which domains are most popular or which servers are serving the most pages.

## state {#concept_82295D22888947BF8B1C76182C635C6C}

Le variabili e le variabili sono variabili di conversione.

<!-- 

state.xml

 -->

Sono come evar in quanto acquisiscono eventi, ma a differenza delle evar non persistono. The *`zip`* and *`state`* variables are like eVars that expire immediately.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 50 byte | state | Conversione &gt; Profilo visitatore &gt; Stato visitatore | "" |

Because the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events that are fired on the same page on which they are populated. For example, if you are using *`state`* to compare conversion rates by state, you should populate the *`state`* variable on every page of the checkout process. Per i siti di conversione, Adobe consiglia di utilizzare l'indirizzo di fatturazione come origine per il codice postale, ma potete scegliere di utilizzare l'indirizzo di spedizione (presupposto che sia presente un solo indirizzo di spedizione per l'ordine). A media site may choose to use *`zip`* and *`state`* for registration or ad click-through tracking.

**Sintassi e valori possibili**{#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

The *`state`* variable does not impose any special value or format restrictions. There are no limitations on *`state`* outside of the standard variable limitations.

**Esempi** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**Impostazioni di configurazione**{#section_DB0D6DC3F4764AC59C11B10D27D2806C}

Nessuno

**Insidie, domande e suggerimenti**{#section_02F1620D0BB14AA6A838966FDB9A234F}

* Populate *`state`* on every page that a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

## timestamp {#concept_D997A2FF4D134C80A614C0BC7A4D7507}

Questa variabile consente di personalizzare la marca temporale di un hit simile alle librerie appmeasurement per altre piattaforme.

<!-- 

timestamp.xml

 -->

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 4 byte | Data/ora | Non segnalati direttamente. | Impostato dai server di raccolta dati. |

**Sintassi** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

The *`timestamp`* variable must be in the format explained in the next section.

>[!IMPORTANT]
>
>Your report suite must be timestamp-enabled by Customer Care before you can use the *`timestamp`* variable. After timestamp support is enabled, all hits sent to this report suite from JavaScript must have a timestamp manually set (using *`s.timestamp`*) or the hits will not be recorded.
>
>Additionally, if you enable timestamp support on a report suite to support offline tracking, all hits sent to this report suite from JavaScript must also have a timestamp manually set (using *`s.timestamp`*). Non puoi inviare hit con marca temporale e senza marca temporale alla stessa suite di rapporti.
>
>You can also use the [Timestamps Optional](../../../implement/js-implementation/timestamps-overview.md#concept_1A7DF6F7BDA34467B51A6F61E08BB73F)setting to mix timestamped and non-timestamped data in the same global report suite, send timestamped data from a mobile app to a global report suite, and upgrade apps to employ timestamps without having to create a new report suite.

**Formati marca temporale**{#section_C12CBCECCD7047D38EF63A5800761CE9}

Le marche temporali devono essere in UNIX (secondi dal 1 ° gennaio 1970) o ISO -8601, con le seguenti limitazioni nel formato ISO -8601 accettato:

* Data e ora devono essere fornite, separate da "T"
* La data deve essere una data di calendario con precisione totale (anno, mese e giorno). Date di settimana e date ordinali non sono supportate.
* The date can be in standard or extended format ( `YYYY-MM-DD` or `YYYYMMDD`), but they must include the hour and minute. Seconds are optional ( `HH:MM`, `HH:MM:SS`, `HHMM`, or `HHMMSS`). I minuti frazionari e i secondi possono essere trasmessi, ma la parte frazionale viene ignorata.

* An optional time zone can be specified in standard or extended format ( `±HH`, `±HH:MM`, `±HH`, `±HHMM`, or Z)

Le marche temporali UNIX continueranno a essere supportate (secondi dal 1 ° gennaio 1970).

**Esempi** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

Nell'elenco seguente sono riportati alcuni esempi di marche temporali in formato ISO -8601 valide:

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Impostazioni di configurazione**{#section_5275D206F2CB4009B3681E8C4457124A}

Prima di poter utilizzare questa variabile, una suite di rapporti deve essere abilitata per accettare marche temporali personalizzate da parte dell'Assistenza clienti. Quando sono abilitate le marche temporali personalizzate, tutti gli hit inviati alla suite di rapporti devono contenere una marca temporale o vengono eliminati.

**Insidie, domande e suggerimenti**{#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* Le marche temporali vengono utilizzate principalmente per tenere traccia dei dati offline sulle piattaforme mobili. Le marche temporali personalizzate vengono generalmente disattivate, a meno che tu non stia raccogliendo dati sia per l'app Web che offline nella stessa suite di rapporti.
* I dati vengono contrassegnati con marca temporale quando i dati offline sono attivati nell'SDK di Mobile (impostazione predefinita) o in qualsiasi momento in cui una suite di rapporti è configurata per accettare dati con marca temporale. I dati raccolti offline sui dispositivi mobili possono essere inviati ore o settimane dopo la data in cui sono stati eseguiti. Questi hit possono essere messi in coda nella piattaforma Analytics per minuti o ore più lunghi rispetto a quelli senza marca temporale:

   * Per i dati con marca temporale inviati in prossimità dell'ora corrente, il ritardo probabile è di 10-15 minuti.
   * Per i dati con marca temporale inviati da ieri, il probabile ritardo è circa 2 ore.
   * Per i dati con marca temporale inviati in precedenza, ogni giorno aggiunge circa 1 ora di ritardo, fino a 15 giorni prima, quando il ritardo si interrompe.

* I dati delle sessioni abilitati per marca temporale vengono conservati per un massimo di 92 giorni.

## trackingServer {#concept_45EE91B1A99B4A37AFAEF1C0A8A6B02F}

La variabile viene utilizzata per l'implementazione dei cookie di prime parti per specificare il dominio in cui viene scritto il cookie e la richiesta immagine.

<!-- 

trackingServer.xml

 -->

Utilizzato per pagine non sicure. If *`trackingServer`* is defined, nothing goes to 2o7.net. If *`trackingServer`* is not defined (and dc is not defined), data goes to 112.2o7.net.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | "" |

A list of Adobe data centers can be found [here](https://helpx.adobe.com/analytics/kb/determining-data-center.html).

## trackingServerSecure {#concept_28132A2606E34A2F87BEC9E7ACADC7DD}

La variabile viene utilizzata per l'implementazione dei cookie di prime parti per specificare il dominio in cui viene scritto il cookie e la richiesta immagine.

<!-- 

trackingServerSecure.xml

 -->

Utilizzato per le pagine sicure. If *`trackingServerSecure`* is not defined, SSL data goes to *`trackingServer`*.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | "" |

## transactionID {#concept_FBFA55E137E644A2BD97B41E92F6AFEF}

[!UICONTROL Integration Data Sources] utilizzare un collegamento [!UICONTROL transaction ID] per collegare dati offline a una transazione online (come un lead o un acquisto generato online).

<!-- 

transactionID.xml

 -->

Each unique *`transactionID`* sent to Adobe is recorded in preparation for a [!UICONTROL Data Sources] upload of offline information about that transaction. See [Data Sources](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | xact | n/d | "" |

**Abilita archiviazione ID transazione**{#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Before *`transactionID`* values are recorded, [!UICONTROL Transaction ID Storage] must be enabled for the report suite selected in the Report Suite Manager. Questa impostazione si trova in

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

To see whether *`transactionID Storage`* is enabled for a report suite, go to

```
Analytics > Admin > Data Sources > Manage
```

**Sintassi e valori possibili**{#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

The *`transactionID`* should contain only alphanumeric characters. If multiple [!UICONTROL transactionIDs] should be recorded in a single hit, you can use a comma to delimit multiple values.

**Esempi** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Insidie, domande e suggerimenti**{#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* *`transactionID`* Se la registrazione non è abilitata, *`transactionID`* i valori verranno eliminati e non possono essere utilizzati. [!UICONTROL Integration Data Sources] Make sure to set a conversion variable or event (an eVar or the events variable) on the page where *`transactionID`* is set. Otherwise, no data is recorded for the *`transactionID`*.

* If you are recording [!UICONTROL transactionIDs] for multiple systems, such as purchases and leads, make sure the value in *`transactionID`* is always unique. Questo può essere ottenuto aggiungendo un prefisso all'ID, ad esempio lead_ 1234 e purchase_ 1234. [!UICONTROL Integration Data Sources] non funziona come previsto ( [!UICONTROL Data Source] i dati si collegeranno ai dati errati) se un unico *`transactionID`* viene visualizzato due volte.

* By default, *`transactionID`* values are remembered for 90 days. Se il processo di interazione offline è più lungo di 90 giorni, contatta l'Assistenza clienti per estendere il limite.

>[!NOTE]
>
>The *`transactionID`* variable can contain any character other than a comma. Deve trovarsi nello stesso percorso in cui viene specificato il limite di caratteri (100 byte). If multi-byte characters are used, multi-byte character support must be enabled in order to avoid problems with unexpected characters in the *`transactionID`*.

## visitorID {#concept_CD273CC915CC4ABD8F52E4209FF9557E}

I visitatori possono essere identificati dalla variabile o da indirizzo IP/Agente utente.

<!-- 

visitorID.xml

 -->

The *`visitorID`* can be up to 100 alpha-numeric characters and must not contain a hyphen.

Se imposti esplicitamente un ID personalizzato, verrà sempre usato prima degli altri metodi ID.

Questo è l'ordine di utilizzo: s. visitorid &gt; s_ vi &gt; s_ fid &gt; IP/UA.

| ** Dimensione max** | ** Parametro Debugger** | ** Report compilati** | ** Valore predefinito** |
|---|---|---|---|
| 100 byte | vid | n/d | "" |

**Sintassi e valori possibili**{#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

>[!NOTE]
>
>The *`visitorID`* variable should not contain a hyphen.

**Esempi** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**Impostazioni di configurazione**{#section_582B376FE55C4BCA8F978E0F62B5DB54}

Nessuno

## visitorNamespace {#concept_8369DDB3830C4BF2905F1CFC8C8B0D92}

La variabile viene utilizzata per identificare il dominio con cui sono impostati i cookie.

<!-- 

visitorNamespace.xml

 -->

If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. If *`visitorNamespace`* changes, all visitors reported in Analytics may become new visitors. La cronologia dei visitatori viene disconnessa dal traffico corrente e futuro. Non modificate questa variabile senza l'approvazione da parte di un rappresentante Adobe.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | ns | N/D | "" |

Analytics usa un cookie per identificare in modo univoco i visitatori del sito. If *`visitorNamespace`* is not used, the cookie is associated 2o7.net. If *`visitorNamespace`* is used, the cookie is associated with a sub-domain of 2o7.net. Tutti i visitatori del sito devono avere i cookie associati allo stesso dominio o sottodominio.

The reason for using the *`visitorNamespace`* variable is to avoid the possibility of overloading a browser's cookie limit. Internet Explorer impone un limite di 20 cookie per dominio. By using the *`visitorNamespace`* variable, other companies' Analytics cookies will not conflict with your visitors' cookies.

**Sintassi e valori possibili**{#section_EE247FE371784CA4B6058182181F3EA1}

The value of *`visitorNamespace`* must be provided by Adobe and is a string of ASCII characters that don't contain commas, periods, spaces, or special characters.

```js
s.visitorNamespace="company_specific_value"
```

**Identificazione dei visitatori nelle suite di rapporti**{#section_7AC5A97FC8C045DD8850245A62BB09F4}

If you do not specify a `visitorNamespace`, each report suite in your company receives its own visitor ID cookie written as `s_vi_[random string]`. If you specify `visitorNamespace`, the same `s_vi` cookie will be used for all report suites that send data to the specified `trackingServer`. Se avete implementato un tag per più suite, specificate lo spazio dei nomi del visitatore in modo che lo stesso cookie sia utilizzato da ogni suite di rapporti.

**Esempi** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**Impostazioni di configurazione**{#section_1128A2531ECC43DFA6749ECC21F050A2}

Nessuno

## zip {#concept_C1DF93083553410DA36EAB61FBFDF69A}

Le variabili e le variabili sono variabili di conversione.

<!-- 

zip.xml

 -->

Sono come evar in quanto acquisiscono eventi, ma a differenza delle evar non persistono. The *`zip`* and *`state`* variables are like eVars that expire immediately.

| Dimensioni massime | Parametro Debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 50 byte | zip | Conversione &gt; Profilo visitatore &gt; CAP/CAP | "" |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. For example, if you are using *`zip`* to compare conversion rates by Zip Code, you should populate *`zip`* on every page of the checkout process. Adobe consiglia di utilizzare l'indirizzo di fatturazione come origine per il codice postale. Potete scegliere di utilizzare l'indirizzo di spedizione (supponendo che sia presente un solo indirizzo di spedizione per l'ordine). A media site may choose to use *`zip`* and *`state`* for registration or ad click-through tracking.

**Sintassi e valori possibili**{#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

The *`zip`* variable does not impose any value or format restrictions. There are no limitations on *`zip`* outside of the standard variable limitations.

**Esempi** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Impostazioni di configurazione**{#section_7987084EECC34DD38B643B94F82385CA}

Nessuno

**Insidie, domande e suggerimenti**{#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Populate [!UICONTROL zip] on every page in which a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

