---
title: channel
description: Popolare la dimensione "Sezioni del sito".
feature: Appmeasurement Implementation
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 24%

---

# channel

La variabile `channel` in genere memorizza la sezione del sito in cui si trova una determinata pagina. È utile determinare quali gruppi del sito sono più popolari. Questa variabile popola la dimensione &quot;Sezioni del sito&quot;.

## Canale tramite Web SDK

Il canale è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `web.webPageDetails.siteSection`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.channel` o `data.__adobe.analytics.ch`

## Canale tramite l’estensione Adobe Analytics

Puoi impostare il canale sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Channel].

Puoi impostare il canale su qualsiasi valore stringa o elemento dati.

## s.channel in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.channel` è una stringa che in genere contiene la sezione del sito della pagina. Ha un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
s.channel = "Example site section";
```

Se si utilizza il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
