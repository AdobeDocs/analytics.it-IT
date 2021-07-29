---
title: pageName
description: Nome della pagina del sito.
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# pageName

La variabile `pageName` in genere memorizza il nome di una determinata pagina. È utile determinare quali singole pagine sono più popolari. Questa variabile popola la dimensione [Pagina](/help/components/dimensions/page.md).

Se questa variabile non è definita in una determinata chiamata di tracciamento della pagina, viene usata invece la variabile [`pageURL`](pageurl.md) .

>[!NOTE]
>
>I server di raccolta dati di Adobe rimuovono questa dimensione da tutte le richieste di immagini [tracciamento collegamenti](/help/implement/vars/functions/tl-method.md). Se desideri che questa dimensione venga visualizzata negli hit di tracciamento dei collegamenti, prova a copiare questa dimensione in un [eVar](evar.md).

## Nome pagina con tag in Adobe Experience Platform

Puoi impostare il nome della pagina sia durante la configurazione dell’estensione Analytics (variabili globali) che in regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Page name] .

Puoi impostare il nome della pagina su qualsiasi valore stringa, inclusi gli elementi dati.

## s.pageName in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.pageName` è una stringa che in genere contiene il nome della pagina. ha un valore massimo di 100 byte; i valori più lunghi vengono troncati. Questo troncamento include le istanze in cui torna a `pageURL` se questa variabile è vuota.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Se utilizzi il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
