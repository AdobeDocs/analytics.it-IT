---
description: Specificate un collegamento di rinuncia e personalizzate il marchio per il collegamento. I visitatori del sito Web potrebbero scegliere di non avere la propria attività tracciata nei prodotti di analisi di Adobe visitando la pagina di rinuncia del dominio di raccolta dati.
keywords: Implementazione di Analytics
seo-description: Specificate un collegamento di rinuncia e personalizzate il marchio per il collegamento. I visitatori del sito Web potrebbero scegliere di non avere la propria attività tracciata nei prodotti di analisi di Adobe visitando la pagina di rinuncia del dominio di raccolta dati.
seo-title: Aggiungere un collegamento di rinuncia
solution: Analytics
subtopic: 'Risoluzione dei problemi   '
title: Aggiungere un collegamento di rinuncia
topic: Sviluppatore e implementazione
uuid: c 12092 be -3 be 7-4621-b 838-d 6 b 78 d 074 f 84
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Aggiungere un collegamento di rinuncia

Specificate un collegamento di rinuncia e personalizzate il marchio per il collegamento. I visitatori del sito Web potrebbero scegliere di non avere la propria attività tracciata nei prodotti di analisi di Adobe visitando la pagina di rinuncia del dominio di raccolta dati.

Se un utente sceglie di non essere tracciato e viene impostato un cookie di rinuncia, il file javascript continuerà a inviare dati ai server Adobe, ma i dati non saranno elaborati o segnalati.

La sezione collection_ domain della struttura URL è il trackingserver utilizzato nel file javascript. Il dominio di raccolta utilizzato per l'implementazione di Adobe Analytics è visibile nel debugger digitalpulse nella prima riga della tabella Adobe Analytics, etichettata «Cookie di prime parti» o «Cookie di terze parti» in base alla tua implementazione. Il dominio di raccolta per il sito Web può contenere 2 o 7. net, omtrdc. net o il dominio del sito Web, ad esempio metriche. esempio. com.

La rinuncia ai visitatori fa clic sul collegamento nella pagina di rifiuto, causando la configurazione di un cookie nel browser. By having the `omniture_optout` cookie for the applicable tracking domain, the user's activities will not be reported by Adobe Analytics. Puoi fornire un collegamento personalizzato al cookie di rinuncia oppure seguire i passaggi indicati di seguito per impostare il cookie di rinuncia.

Adobe offre opt-out per tutti i tipi di implementazione. L'Utente è responsabile della propria informativa sulla privacy e del rimanente rispetto ai termini firmati. Il collegamento alla pagina di rinuncia cambia in base al tipo di implementazione, come descritto qui.

If you implement Adobe Analytics products and services with cookies set on domains owned by Adobe (i.e. 207.net or omtrdc.net), you can point your website visitors to the opt-out mechanism provided in the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html) for all sites that use Adobe cookies for Adobe Analytics products and services. The direct link to the Adobe opt-out mechanism is `https:// *collection_domain* /optout.html`.

More information about Adobe Analytics privacy practices can be found at [https://www.adobe.com/privacy/advertising-services.html](https://www.adobe.com/privacy/advertising-services.html).

* [Struttura URL della pagina di rifiuto](../../../implement/js-implementation/data-collection/opt-out-link.md#section_E0462428D2E440E7863E24D2F6DBF748)
* [URL di rinuncia degli esempi](../../../implement/js-implementation/data-collection/opt-out-link.md#section_258DE5226AA0483CA790D2C9C5318B2E)
* [Personalizzazione dell'URL di rinuncia](../../../implement/js-implementation/data-collection/opt-out-link.md#section_674AB62E810B414AB8F1615C0E3061F8)

## Opt-out Page URL Structure {#section_E0462428D2E440E7863E24D2F6DBF748}

La pagina di rifiuto è al seguente URL:

```
https://collection_domain/optout.html[?optional_parameters]
```

The `optional_parameters` include:

`locale=[code]`: Fornisce una versione convertita della pagina di rifiuto. Sono supportate le seguenti impostazioni internazionali:

* it_ IT (predefinito)
* de_ DE
* es_ ES
* fr_ FR
* jp_ JP
* ko_ KR
* zh_ CN
* zh_ TW

`popup=1`: Tratta la pagina come se fosse una finestra a comparsa e offre un pulsante Chiudi finestra.

## Example Opt-Out URLs {#section_258DE5226AA0483CA790D2C9C5318B2E}

Una pagina Web inglese in una finestra completa contenente un collegamento che, quando è stato fatto clic, impedirà il tracciamento del visitatore su metrics.example.com:

```
https://metrics.example.com/optout.html
```

Una pagina Web francese in una finestra completa contenente un collegamento che, quando è stato fatto clic, impedirà il tracciamento del visitatore su example.d3.sc.om trdc. net:

```
https://example.d3.sc.omtrdc.net/optout.html?locale=fr_FR
```

Una pagina Web tedesca, in una finestra a comparsa contenente un collegamento che, quando è stato fatto clic, impedirà il tracciamento del visitatore ad esempio .112 .2 o 7. net:

```
https://example.112.2o7.net/optout.html?popup=1&locale=de_DE
```

## Branding your Opt-Out URL {#section_674AB62E810B414AB8F1615C0E3061F8}

Puoi fornire un collegamento, ad esempio quanto segue nel sito Web:

```
 <a href=" https://stats.adobe.com/optout.html?optout=1&confirm_change=1">
Click Here to Opt Out! </a>
```

Where *`stats.adobe.com`* is replaced with whatever the *`s.trackingServer`* variable is set to.

Additionally, if you want like to provide a link to opt-in, use the same URL, but replace `?optout=1` with `?optin=1`, and keep the `confirm_change=1`.
