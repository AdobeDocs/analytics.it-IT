---
title: visitorNameSpace
description: (Ritirato) Ha contribuito a determinare il dominio dei cookie di terze parti.
feature: Appmeasurement Implementation
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 18%

---

# visitorNamespace

>[!IMPORTANT]
>
>Questa variabile viene ritirata. Al suo posto, utilizza [`trackingServer`](trackingserver.md).

Nelle versioni precedenti di Adobe Analytics, AppMeasurement ha utilizzato la variabile `visitorNameSpace` per determinare il sottodominio di `2o7.net` in cui sono memorizzati i cookie dei visitatori. L’aumento delle pratiche di privacy nei browser moderni rende i cookie di terze parti meno affidabili. Con l&#39;introduzione delle variabili `trackingServer` e [`trackingServerSecure`](trackingserversecure.md), `visitorNameSpace` non è più necessario.

>[!TIP]
>
>Adobe consiglia di utilizzare i cookie di prime parti sul sito. I cookie di prime parti non utilizzano questa variabile.

## Spazio dei nomi del visitatore che utilizza l’estensione Adobe Analytics

[!UICONTROL Visitor Namespace] è un campo nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Cookies], che mostra il campo [!UICONTROL Visitor Namespace].

Adobe consiglia di non utilizzare questo campo. Utilizza invece `trackingServer` e `trackingServerSecure`.

## s.visitorNamespace in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.visitorNamespace` è una stringa che contiene un valore univoco per organizzazione. Le vecchie librerie AppMeasurement includevano automaticamente questo valore univoco quando venivano scaricate da versioni precedenti di Adobe Analytics. Le librerie AppMeasurement correnti non utilizzano questa variabile a meno che `trackingServer` e `trackingServerSecure` non siano impostati.

Se l’organizzazione richiede ancora questa variabile, scegli un valore che rappresenti l’organizzazione. È possibile memorizzare questo valore in un [documento di progettazione della soluzione](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
