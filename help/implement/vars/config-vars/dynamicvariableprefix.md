---
title: dynamicVariablePrefix
description: Consente di personalizzare la stringa che identifica le variabili dinamiche.
feature: Appmeasurement Implementation
exl-id: fe208723-0cf2-4899-be7a-8f23c6501c11
role: Admin, Developer
TQID: https://experienceleague.adobe.com/4NlOgI1maQuMHenSZHUnc7ESvlbst09v4CmOMlBbfEE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 270
ht-degree: 15%

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

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
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
