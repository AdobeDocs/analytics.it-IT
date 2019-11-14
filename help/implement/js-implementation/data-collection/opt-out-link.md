---
description: Specificate un collegamento di rinuncia e personalizzate il marchio del collegamento. I visitatori del sito Web possono scegliere di non tenere traccia dell'attività nei prodotti Adobe Analytics visitando la pagina di rifiuto del dominio di raccolta dati.
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: Aggiungere un collegamento di rinuncia
topic: Developer and implementation
uuid: c12092be-3be7-4621-b838-d6b78d074f84
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Aggiungere un collegamento di rinuncia

Specificate un collegamento di rinuncia e personalizzate il marchio del collegamento. I visitatori del sito Web possono scegliere di non tenere traccia dell'attività nei prodotti Adobe Analytics visitando la pagina di rifiuto del dominio di raccolta dati.

Se un utente sceglie di non essere monitorato e viene impostato un cookie di rinuncia, il file JavaScript continuerà a inviare dati ai server Adobe, ma tali dati non saranno elaborati o segnalati in futuro.

La sezione collection_domain della struttura URL è il trackingServer utilizzato nel file JavaScript. Il dominio di raccolta utilizzato per l'implementazione di Adobe Analytics può essere visualizzato nel debugger DigitalPulse nella prima riga della tabella di Adobe Analytics, etichettato come "Cookie di prime parti" o "Cookie di terze parti" a seconda dell'implementazione. Il dominio di raccolta per il sito Web può contenere 2o7.net, omtrdc.net o il dominio del sito Web, ad esempio metriche.example.com.

Per rifiutare, i visitatori fanno clic sul collegamento nella pagina di rifiuto, causando l’impostazione di un cookie nel browser. Disponendo del `omniture_optout` cookie per il dominio di tracciamento applicabile, le attività dell'utente non saranno segnalate da Adobe Analytics. Potete fornire il vostro collegamento al cookie di rinuncia, oppure potete seguire i passaggi descritti di seguito per impostare il cookie di rinuncia.

Adobe offre opzioni di rifiuto per tutti i tipi di implementazione. L'Utente è responsabile della propria informativa sulla privacy e del rispetto dei termini firmati. Il collegamento alla pagina di rifiuto cambia in base al tipo di implementazione, come illustrato di seguito.

Se implementate prodotti e servizi Adobe Analytics con cookie impostati sui domini di proprietà di Adobe (ad es. 207.net o omtrdc.net), potete indirizzare i visitatori del vostro sito Web al meccanismo di rifiuto fornito in [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html) per tutti i siti che utilizzano i cookie Adobe per i prodotti e i servizi Adobe Analytics. Il collegamento diretto al meccanismo di rinuncia di Adobe è `https:// *collection_domain* /optout.html`.

Per ulteriori informazioni sulle pratiche sulla privacy di Adobe Analytics, consultate [https://www.adobe.com/privacy/advertising-services.html](https://www.adobe.com/privacy/advertising-services.html).

* [Struttura URL pagina di rifiuto](/help/implement/js-implementation/data-collection/opt-out-link.md#section_E0462428D2E440E7863E24D2F6DBF748)
* [Esempio di URL di rifiuto](/help/implement/js-implementation/data-collection/opt-out-link.md#section_258DE5226AA0483CA790D2C9C5318B2E)
* [Aggiunta del marchio all’URL di rifiuto](/help/implement/js-implementation/data-collection/opt-out-link.md#section_674AB62E810B414AB8F1615C0E3061F8)

## Struttura URL pagina di rifiuto {#section_E0462428D2E440E7863E24D2F6DBF748}

La pagina di rifiuto si trova nel seguente URL:

```
https://collection_domain/optout.html[?optional_parameters]
```

Sono `optional_parameters` inclusi:

`locale=[code]`: Fornisce una versione convertita della pagina di rifiuto. Sono supportate le seguenti impostazioni internazionali:

* en_US (predefinito)
* de_DE
* es_ES
* fr_FR
* jp_JP
* ko_KR
* zh_CN
* zh_TW

`popup=1`: Tratta la pagina come se fosse una finestra a comparsa e offre un pulsante "Chiudi finestra".

## Esempio di URL di rifiuto {#section_258DE5226AA0483CA790D2C9C5318B2E}

Una pagina Web in inglese in una finestra completa contenente un collegamento che, quando viene fatto clic su di essa, impedisce al visitatore di essere tracciato su metriche.example.com:

```
https://metrics.example.com/optout.html
```

Una pagina Web francese in una finestra completa, contenente un collegamento che, se selezionato, impedisce al visitatore di essere tracciato su example.d3.sc.omtrdc.net:

```
https://example.d3.sc.omtrdc.net/optout.html?locale=fr_FR
```

Una pagina Web tedesca, in una finestra a comparsa, contenente un collegamento che, se selezionato, impedisce al visitatore di essere tracciato su example.112.2o7.net:

```
https://example.112.2o7.net/optout.html?popup=1&locale=de_DE
```

## Aggiunta del marchio all’URL di rifiuto {#section_674AB62E810B414AB8F1615C0E3061F8}

Potete fornire un collegamento, ad esempio il seguente da qualche parte sul vostro sito Web:

```
 <a href=" https://stats.adobe.com/optout.html?optout=1&confirm_change=1">
Click Here to Opt Out! </a>
```

Dove *`stats.adobe.com`* viene sostituito con qualsiasi *`s.trackingServer`* variabile impostata su.

Inoltre, se desiderate fornire un collegamento per l’opzione di consenso, usate lo stesso URL, ma sostituite `?optout=1` con `?optin=1`, e mantenete il `confirm_change=1`.
