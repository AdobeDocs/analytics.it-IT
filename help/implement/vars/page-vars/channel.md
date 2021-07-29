---
title: channel
description: Popolare la dimensione "Sezioni del sito".
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 1%

---

# canale

La variabile `channel` in genere memorizza la sezione del sito su cui si trova una determinata pagina. È utile determinare quali gruppi del sito sono più popolari. Questa variabile popola la dimensione &quot;Sezioni del sito&quot;.

## Canale che utilizza i tag in Adobe Experience Platform

Puoi impostare il canale sia durante la configurazione dell’estensione Analytics (variabili globali) che in regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Channel] .

Puoi impostare il canale su qualsiasi valore stringa o elemento dati.

## s.channel in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.channel` è una stringa che in genere contiene la sezione del sito della pagina. ha un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
s.channel = "Example site section";
```

Se utilizzi il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
