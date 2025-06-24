---
title: dynamicVariablePrefix
description: Consente di personalizzare la stringa che identifica le variabili dinamiche.
feature: Appmeasurement Implementation
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 14%

---

# dynamicVariablePrefix

Le variabili dinamiche sono un concetto abbreviato che consente di copiare i valori da una variabile all’altra. Sono utili per valori di variabili lunghi, in quanto aiutano a ridurre la lunghezza dell’URL di una richiesta di immagine. Per ulteriori informazioni su questo concetto, vedere [Variabili dinamiche](../page-vars/dynamic-variables.md).

Per impostazione predefinita, le variabili dinamiche utilizzano il prefisso `D=`. La variabile `dynamicVariablePrefix` consente di personalizzare la stringa che identifica le variabili dinamiche. È sensibile a maiuscole e minuscole.

## Prefisso della variabile dinamica tramite Web SDK

Il Web SDK non utilizza la formattazione dinamica delle variabili. È invece possibile utilizzare la mappatura dello stream di dati per compilare più campi di destinazione utilizzando un singolo campo Source. Per ulteriori informazioni, vedere [Variabili dinamiche tramite Web SDK](../page-vars/dynamic-variables.md#dynamic-variables-using-the-web-sdk).

Se invii dati direttamente ad Adobe Analytics senza essere conforme a uno schema, utilizza la variabile seguente:

* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.dynamicVariablePrefix`

## Prefisso della variabile dinamica tramite l’estensione Adobe Analytics

Il prefisso della variabile dinamica è un campo nel pannello a soffietto [!UICONTROL Global Variables] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi il pannello a soffietto [!UICONTROL Global Variables], che mostra il campo [!UICONTROL Dynamic Variable Prefix].

Questo campo contiene `D=` per impostazione predefinita. È possibile modificare il valore se si desidera utilizzare un prefisso di variabile dinamica diverso. Puoi utilizzare qualsiasi valore desiderato, purché corrisponda alla codifica dei caratteri sul sito.

## s.dynamicVariablePrefix in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.dynamicVariablePrefix` è una stringa che può contenere qualsiasi sequenza di caratteri. Se questa variabile non è definita, AppMeasurement utilizza la stringa `D=` per impostazione predefinita.

```js
// An example that changes the dynamic variable prefix
s.dynamicVariablePrefix="..";

// This eVar uses the above customized dynamic variable prefix to set eVar to page URL
s.eVar1="..g";
```
