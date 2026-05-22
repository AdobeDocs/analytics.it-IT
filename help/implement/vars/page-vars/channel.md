---
title: channel
description: Popolare la dimensione "Sezioni del sito".
feature: Appmeasurement Implementation
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/8O57DR-hVZaTuPvVFeOabX-OO6t-Ym7XCKogurcI810'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 186
ht-degree: 32%

---

# channel

La variabile `channel` in genere memorizza la sezione del sito in cui si trova una determinata pagina. È utile determinare quali gruppi del sito sono più popolari. Questa variabile popola la dimensione &quot;Sezioni del sito&quot;.

## Canale tramite Web SDK

Il canale è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `web.webPageDetails.siteSection`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.channel` o `data.__adobe.analytics.ch`

## Canale tramite l’estensione Adobe Analytics

Puoi impostare il canale sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Channel].

Puoi impostare il canale su qualsiasi valore stringa o elemento dati.

## s.channel in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.channel` è una stringa che in genere contiene la sezione del sito della pagina. Può avere un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
s.channel = "Example site section";
```

Se si utilizza il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
