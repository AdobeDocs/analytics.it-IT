---
title: dynamicVariablePrefix
description: Consente di personalizzare la stringa che identifica le variabili dinamiche.
translation-type: tm+mt
source-git-commit: 03a4c0d5e080219a7fd96dff33ce122669351ac3

---


# dynamicVariablePrefix

Le variabili dinamiche sono concetti abbreviati che consentono di copiare i valori da una variabile all’altra. Sono utili per valori variabili lunghi, in quanto consentono di ridurre la lunghezza URL di una richiesta di immagine. Per ulteriori informazioni su questo concetto, consultate Variabili [](../page-vars/dynamic-variables.md) dinamiche.

Per impostazione predefinita, le variabili dinamiche usano il prefisso `D=`. La `dynamicVariablePrefix` variabile consente di personalizzare la stringa che identifica le variabili dinamiche. Fa distinzione tra maiuscole e minuscole.

## Prefisso variabile dinamico in Adobe Experience Platform Launch

Prefisso variabile dinamico è un campo situato sotto la struttura di [!UICONTROL Global Variables] navigazione durante la configurazione dell’estensione Adobe Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante in Adobe Analytics.
4. Espandere la [!UICONTROL Global Variables] struttura a soffietto, che mostra il [!UICONTROL Dynamic Variable Prefix] campo.

Questo campo contiene `D=` per impostazione predefinita. È possibile modificare il valore se si desidera utilizzare un diverso prefisso di variabile dinamica. È possibile utilizzare qualsiasi valore desiderato, purché corrisponda alla codifica dei caratteri sul sito.

## s.dynamicVariablePrefix nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.dynamicVariablePrefix` variabile è una stringa che può contenere qualsiasi sequenza di caratteri. Se questa variabile non è definita, AppMeasurement utilizza la stringa `D=` per impostazione predefinita.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
