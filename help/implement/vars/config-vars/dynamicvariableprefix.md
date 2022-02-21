---
title: dynamicVariablePrefix
description: Consente di personalizzare la stringa che identifica le variabili dinamiche.
feature: Variables
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# dynamicVariablePrefix

Le variabili dinamiche sono concetti abbreviati che consentono di copiare i valori da una variabile all’altra. Sono utili per valori variabili lunghi, in quanto consentono di ridurre la lunghezza dell’URL di una richiesta di immagine. Vedi [Variabili dinamiche](../page-vars/dynamic-variables.md) per ulteriori informazioni su questo concetto.

Per impostazione predefinita, le variabili dinamiche utilizzano il prefisso `D=`. La `dynamicVariablePrefix` ti consente di personalizzare la stringa che identifica le variabili dinamiche. Fa distinzione tra maiuscole e minuscole.

## Prefisso variabile dinamico tramite tag in Adobe Experience Platform

Prefisso variabile dinamico è un campo sotto [!UICONTROL Global Variables] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
4. Espandi la [!UICONTROL Global Variables] fisarmonica, che rivela [!UICONTROL Dynamic Variable Prefix] campo .

Questo campo contiene `D=` per impostazione predefinita. Puoi modificare il valore se desideri utilizzare un prefisso di variabile dinamica diverso. È possibile utilizzare qualsiasi valore desiderato, purché corrisponda alla codifica dei caratteri sul sito.

## s.dynamicVariablePrefix in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.dynamicVariablePrefix` è una stringa che può contenere qualsiasi sequenza di caratteri. Se questa variabile non è definita, AppMeasurement utilizza la stringa `D=` per impostazione predefinita.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
