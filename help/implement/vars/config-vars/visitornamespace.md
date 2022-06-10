---
title: visitorNameSpace
description: È stata ritirata la variabile che determinava il dominio dei cookie.
feature: Variables
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# visitorNamespace

>[!IMPORTANT]
>
>Questa variabile è ritirata. Utilizzo [`trackingServer`](trackingserver.md) invece.

Nelle versioni precedenti di Adobe Analytics, AppMeasurement utilizzava il `visitorNameSpace` per determinare il sottodominio di `2o7.net` dove vengono memorizzati i cookie dei visitatori. L’aumento delle pratiche di privacy nei browser moderni rende i cookie di terze parti meno affidabili. Con l&#39;introduzione del `trackingServer` e [`trackingServerSecure`](trackingserversecure.md) variabili, `visitorNameSpace` non è più necessario.

>[!TIP]
>
>Adobe consiglia di utilizzare cookie di prime parti sul sito. I cookie di prime parti non utilizzano questa variabile.

## Spazio dei nomi del visitatore che utilizza l’estensione Adobe Analytics

[!UICONTROL Visitor Namespace] è un campo sotto [!UICONTROL Cookies] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto Adobe Analytics.
4. Espandi la [!UICONTROL Cookies] fisarmonica, che rivela [!UICONTROL Visitor Namespace] campo .

L’Adobe sconsiglia di utilizzare questo campo. Utilizzo `trackingServer` e `trackingServerSecure` invece.

## s.visitorNamespace in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.visitorNamespace` è una stringa che contiene un valore univoco per organizzazione. Le vecchie librerie AppMeasurement includevano automaticamente questo valore univoco quando vengono scaricate dalle versioni precedenti di Adobe Analytics. Le librerie AppMeasurement correnti non utilizzano questa variabile a meno che `trackingServer` e `trackingServerSecure` non sono impostati.

Se la tua organizzazione richiede ancora questa variabile, scegli un valore che rappresenta la tua organizzazione. Puoi memorizzare questo valore in un [documento di progettazione della soluzione](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
