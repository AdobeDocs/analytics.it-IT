---
title: channel
description: Compilate la dimensione "Sezioni del sito".
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 2%

---


# channel

La `channel` variabile memorizza in genere la sezione del sito su cui è collocata una determinata pagina. È utile determinare quali gruppi del sito sono più popolari. Questa variabile popola la dimensione &quot;Sezioni del sito&quot;.

## Canale in  Adobe Experience Platform Launch

Puoi impostare il canale sia durante la configurazione dell&#39;estensione Analytics (variabili globali), sia in base alle regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su  Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL Channel] sezione.

Puoi impostare il canale su qualsiasi valore di stringa o elemento dati.

## s.channel in AppMeasurement e Launch editor di codice personalizzato

La `s.channel` variabile è una stringa che in genere contiene la sezione del sito della pagina. Ha un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
s.channel = "Example site section";
```

Se si utilizza il livello `digitalData` [](../../prepare/data-layer.md)dati:

```js
s.channel = digitalData.page.category.primaryCategory;
```
