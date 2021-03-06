---
title: pageName
description: Nome della pagina del sito.
feature: Variables
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# pageName

La `pageName` in genere memorizza il nome di una determinata pagina. È utile determinare quali singole pagine sono più popolari. Questa variabile popola il [Pagina](/help/components/dimensions/page.md) dimensione.

Se questa variabile non è definita in una determinata chiamata di tracciamento della pagina, la variabile [`pageURL`](pageurl.md) viene invece utilizzata.

>[!NOTE]
>
>Adobe server di raccolta dati elimina questa dimensione da tutti [tracciamento dei collegamenti](/help/implement/vars/functions/tl-method.md) richieste di immagini. Se vuoi che questa dimensione venga visualizzata negli hit di tracciamento dei collegamenti, prova a copiare questa dimensione in un [eVar](evar.md).

## Nome pagina con l’SDK per web

La pagina è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) nel campo XDM `web.webPageDetails.name`.

## Nome pagina utilizzando l’estensione Adobe Analytics

Puoi impostare il nome della pagina sia durante la configurazione dell’estensione Analytics (variabili globali) che in regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Page name] sezione .

Puoi impostare il nome della pagina su qualsiasi valore stringa, inclusi gli elementi dati.

## s.pageName in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.pageName` è una stringa che in genere contiene il nome della pagina. ha un valore massimo di 100 byte; i valori più lunghi vengono troncati. Questo troncamento include le istanze in cui rientra `pageURL` se questa variabile è vuota.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Se utilizzi `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
