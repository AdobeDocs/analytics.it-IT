---
title: Identificazione dei visitatori tramite AppMeasurement
description: Identifica correttamente i visitatori quando implementi Adobe Analytics utilizzando AppMeasurement.
exl-id: 38797ca5-dc53-431e-95df-3c9e68aead94
TQID: https://experienceleague.adobe.com/vWLzF0HXreytCKr01H4-gKzNlO36ySHA2vbcHvT3cIw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 513
ht-degree: 0%

---

# Identificazione dei visitatori tramite AppMeasurement

AppMeasurement è la libreria JavaScript legacy di Adobe Analytics per la raccolta dei dati. Anche se AppMeasurement offre da sola una modalità nativa per identificare i visitatori, molti browser moderni rifiutano i cookie di terze parti che tenta di impostare. Adobe consiglia vivamente di utilizzare il [servizio ID visitatore di Adobe](https://experienceleague.adobe.com/it/docs/id-service/using/home) in tutte le implementazioni per conformarsi ai moderni standard sulla privacy del browser. Tutte le versioni di AppMeasurement sono fornite in bundle con `VisitorAPI.js`, la libreria JavaScript utilizzata per implementare il servizio ID visitatori.

## Identificazione dei visitatori tramite il servizio ID visitatori (scelta consigliata)

Assicurati di essere preparato con quanto segue:

* Scarica la [versione più recente di AppMeasurement](https://github.com/adobe/appmeasurement). La libreria scaricata include sia `AppMeasurement.js` che `VisitorAPI.js`.
* [ID suite di rapporti](/help/admin/tools/manage-rs/new-rs/new-report-suite.md) per lo sviluppo.
* Il dominio Edge desiderato per [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md).
* ID organizzazione IMS:
   1. Accedi a [Adobe CX Enterprise](https://experience.adobe.com) utilizzando le credenziali Adobe ID.
   1. In qualsiasi punto dell&#39;interfaccia di CX Enterprise, premere `[Cmd]` + `[I]` (iOS) o `[Ctrl]` + `[I]` (Windows).
   1. Verrà visualizzato **[!UICONTROL User data debugger]**. Seleziona la scheda **[!UICONTROL Assigned orgs]**.
   1. Espandi l’organizzazione IMS desiderata.
   1. Individua il campo **[!UICONTROL ID]**.

Una volta che disponi delle risorse di cui sopra, la seguente pagina di esempio di base contiene le chiamate minime necessarie per inviare dati ad Adobe Analytics:

```html
<html>
  <head>
    <title>Example AppMeasurement implementation page</title>
    <script src="AppMeasurement.js"></script>
    <script src="VisitorAPI.js"></script>
  </head>
  <body>
    <h1>Hello world!</h1>
    <script>
      var s = s_gi("examplersid"); // Include development report suite ID here
      s.trackingServerSecure = "example.data.adobedc.net"; // Include edge domain here
      s.visitor = Visitor.getInstance("ADB3LETTERSANDNUMBERS@AdobeOrg"); // Include IMS org ID here
      s.pageName = document.title;
      s.t();
    </script>
  </body>
</html>
```

>[!TIP]
>
>È possibile verificare se un hit utilizza il servizio ID visitatore assegnando la presenza di `Visitor` a una variabile personalizzata in [`doPlugins`](/help/implement/vars/functions/doplugins.md):
>
>```js
>s.doPlugins = function() {
>   s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI present" : "VisitorAPI missing";
>};
>```

## Identificazione dei visitatori tramite il cookie `s_vi` (scelta non consigliata)

>[!IMPORTANT]
>
>Adobe consiglia di non utilizzare questo metodo per identificare i visitatori.

Se la tua organizzazione non utilizza il servizio ID visitatori (`VisitorAPI.js`), AppMeasurement utilizza il proprio modulo legacy di identificazione dei visitatori. Quando un visitatore arriva al tuo sito per la prima volta, la libreria controlla la presenza di un cookie [`s_vi`](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/cookies/analytics). Questo cookie è impostato nel dominio corrispondente a [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) (per HTTPS) o `trackingServer` (per HTTP).

* Se partecipi al [programma di certificazione gestito](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/adobe-managed-cert), il server di tracciamento sarà in genere un dominio di prime parti, rendendo `s_vi` cookie di prime parti.
* Se non partecipi al programma di certificazione gestito, il server di tracciamento è in genere un sottodominio di `adobedc.net`, `omtrdc.net` o `2o7.net`, rendendo il cookie `s_vi` un cookie di terze parti. A causa dei moderni standard di privacy del browser, i cookie di terze parti vengono rifiutati dalla maggior parte dei browser. Una volta rifiutato, AppMeasurement tenta di impostare un cookie di fallback di prime parti (`fid`).

Se `trackingServerSecure` è impostato correttamente, non sono necessarie ulteriori misure di identificazione dei visitatori.

## Identificazione dei visitatori tramite `visitorID` (scelta non consigliata)

>[!IMPORTANT]
>
>Adobe consiglia di non utilizzare questo metodo per identificare i visitatori.

L&#39;utilizzo della variabile [`visitorID`](/help/implement/vars/config-vars/visitorid.md) consente all&#39;organizzazione di completare il controllo indipendente per identificare i visitatori. Se utilizzi `visitorID`, tieni presente le seguenti limitazioni:

* Ogni hit deve contenere lo stesso valore `visitorID` per essere conteggiato come un singolo visitatore.
   * Eventuali hit che omettono `visitorID` tentano automaticamente di utilizzare un altro metodo di identificazione visitatore, considerandoli come un visitatore separato.
   * Tutti gli hit che contengono un valore `visitorID` diverso da un hit precedente vengono trattati come un visitatore separato.
   * Adobe non offre un modo per unire gli hit utilizzando ID visitatore diversi in Adobe Analytics.
* I tipi di pubblico condivisi, Analytics for Target e gli attributi del cliente non sono supportati con i visitatori identificati tramite `visitorID`.

Per le istruzioni di implementazione che utilizzano questa variabile, vedere [`visitorID`](/help/implement/vars/config-vars/visitorid.md).
