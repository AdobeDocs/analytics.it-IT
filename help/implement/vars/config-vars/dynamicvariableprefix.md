---
title: dynamicVariablePrefix
description: Consente di personalizzare la stringa che identifica le variabili dinamiche.
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# dynamicVariablePrefix

Le variabili dinamiche sono concetti abbreviati che consentono di copiare i valori da una variabile all’altra. Sono utili per valori variabili lunghi, in quanto consentono di ridurre la lunghezza dell’URL di una richiesta di immagine. Per ulteriori informazioni su questo concetto, consulta [Variabili dinamiche](../page-vars/dynamic-variables.md) .

Per impostazione predefinita, le variabili dinamiche utilizzano il prefisso `D=`. La variabile `dynamicVariablePrefix` ti consente di personalizzare la stringa che identifica le variabili dinamiche. Fa distinzione tra maiuscole e minuscole.

## Prefisso variabile dinamico tramite tag in Adobe Experience Platform

Dynamic Variable Prefix è un campo sotto il pannello a soffietto [!UICONTROL Global Variables] durante la configurazione dell’estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Global Variables] pannello a soffietto, che mostra il campo [!UICONTROL Dynamic Variable Prefix] .

Questo campo contiene `D=` per impostazione predefinita. Puoi modificare il valore se desideri utilizzare un prefisso di variabile dinamica diverso. È possibile utilizzare qualsiasi valore desiderato, purché corrisponda alla codifica dei caratteri sul sito.

## s.dynamicVariablePrefix in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.dynamicVariablePrefix` è una stringa che può contenere qualsiasi sequenza di caratteri. Se questa variabile non è definita, AppMeasurement utilizza la stringa `D=` per impostazione predefinita.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
