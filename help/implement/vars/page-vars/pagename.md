---
title: pageName
description: Il nome della pagina sul sito.
feature: Appmeasurement Implementation
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/UVcun7asSJzB20Q4TD5EAqt1-M1OY4VUhH--rEJRdc4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 24%

---

# pageName

La variabile `pageName` in genere memorizza il nome di una determinata pagina. È utile determinare quali pagine sono più popolari. Questa variabile popola la dimensione [Pagina](/help/components/dimensions/page.md).

Se questa variabile non è definita in una determinata chiamata di tracciamento della pagina, viene utilizzata la variabile [`pageURL`](pageurl.md).

>[!NOTE]
>
>I server di raccolta dati di Adobe eliminano questa dimensione da tutte le [richieste di immagini di tracciamento dei collegamenti](/help/implement/vars/functions/tl-method.md). Se desideri che questa dimensione venga visualizzata negli hit di tracciamento dei collegamenti, prova a copiarla in un [eVar](evar.md).

## Nome della pagina utilizzando il Web SDK

Il nome della pagina è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.name`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageName`

## Nome della pagina utilizzando l’estensione Adobe Analytics

Puoi impostare il nome della pagina sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
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
