---
title: channel
description: Popolare la dimensione "Sezioni del sito".
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 1%

---

# canale

La `channel` in genere memorizza la sezione del sito in cui si trova una determinata pagina. È utile determinare quali gruppi del sito sono più popolari. Questa variabile popola la dimensione &quot;Sezioni del sito&quot;.

## Canale che utilizza i tag in Adobe Experience Platform

Puoi impostare il canale sia durante la configurazione dell’estensione Analytics (variabili globali) che in regole.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Channel] sezione .

Puoi impostare il canale su qualsiasi valore stringa o elemento dati.

## s.channel in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.channel` è una stringa che in genere contiene la sezione del sito della pagina. ha un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
s.channel = "Example site section";
```

Se utilizzi `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
