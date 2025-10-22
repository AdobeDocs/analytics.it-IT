---
title: Identificazione dei visitatori tramite AppMeasurement
description: Identifica correttamente i visitatori quando implementi Adobe Analytics utilizzando AppMeasurement.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---

# Identificazione dei visitatori tramite AppMeasurement

AppMeasurement è la libreria JavaScript legacy di Adobe Analytics per la raccolta dei dati. Anche se AppMeasurement offre da sola una modalità nativa per identificare i visitatori, molti browser moderni rifiutano i cookie di terze parti che tenta di impostare. Adobe consiglia vivamente di utilizzare il servizio ID visitatore di Adobe Experience Cloud in tutte le implementazioni per conformarsi ai moderni standard sulla privacy dei browser. Tutte le versioni di AppMeasurement sono fornite in bundle con `VisitorAPI.js`, la libreria JavaScript utilizzata per implementare il servizio ID visitatori.

## Identificazione dei visitatori tramite il servizio ID visitatori (scelta consigliata)

Assicurati di essere preparato con quanto segue:

* Scarica la [versione più recente di AppMeasurement](https://github.com/adobe/appmeasurement). La libreria scaricata include sia `AppMeasurement.js` che `VisitorAPI.js`.
* [ID suite di rapporti](/help/admin/tools/manage-rs/new-rs/new-report-suite.md) per lo sviluppo.
* Il dominio Edge desiderato per [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md).
* ID organizzazione IMS:
   1. Accedi a [experience.adobe.com](https://experience.adobe.com) utilizzando le credenziali Adobe ID.
   1. In qualsiasi punto dell&#39;interfaccia di Experience Cloud, premere `[Cmd]` + `[I]` (iOS) o `[Ctrl]` + `[I]` (Windows).
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

Se la tua organizzazione non utilizza il servizio ID visitatore, AppMeasurement utilizza la propria forma di identificazione dei visitatori. Quando un visitatore arriva al tuo sito per la prima volta, la libreria controlla la presenza di un cookie [`s_vi`](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/cookies/analytics). Questo cookie è impostato nel dominio corrispondente a [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) (per HTTPS) o [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) (per HTTP).

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
