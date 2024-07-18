---
title: pageName
description: Il nome della pagina sul sito.
feature: Variables
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 23%

---

# pageName

La variabile `pageName` in genere memorizza il nome di una determinata pagina. È utile determinare quali pagine sono più popolari. Questa variabile popola la dimensione [Pagina](/help/components/dimensions/page.md).

Se questa variabile non è definita in una determinata chiamata di tracciamento della pagina, viene utilizzata la variabile [`pageURL`](pageurl.md).

>[!NOTE]
>
>Adobe di server di raccolta dati che eliminano questa dimensione da tutte le [richieste di immagini di tracciamento dei collegamenti](/help/implement/vars/functions/tl-method.md). Se desideri che questa dimensione venga visualizzata negli hit di tracciamento dei collegamenti, prova a copiarla in un [eVar](evar.md).

## Nome pagina utilizzando il Web SDK

Il nome della pagina è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.name`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageName`

## Nome della pagina utilizzando l’estensione Adobe Analytics

Puoi impostare il nome della pagina sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Page name].

Puoi impostare il nome della pagina su qualsiasi valore stringa, inclusi gli elementi dati.

## s.pageName in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.pageName` è una stringa che in genere contiene il nome della pagina. Può avere un valore massimo di 100 byte; i valori più lunghi vengono troncati. Questo troncamento include le istanze in cui torna a `pageURL` se questa variabile è vuota.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Se si utilizza il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
