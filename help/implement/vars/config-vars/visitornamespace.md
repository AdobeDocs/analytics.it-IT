---
title: visitorNameSpace
description: Variabile ritirata che ha determinato il dominio dei cookie.
feature: Variables
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 19%

---

# visitorNamespace

>[!IMPORTANT]
>
>Questa variabile viene ritirata. Al suo posto, utilizza [`trackingServer`](trackingserver.md).

Nelle versioni precedenti di Adobe Analytics, AppMeasurement utilizzava `visitorNameSpace` variabile per determinare il sottodominio di `2o7.net` dove vengono memorizzati i cookie del visitatore. L’aumento delle pratiche di privacy nei browser moderni rende i cookie di terze parti meno affidabili. Con l&#39;introduzione del `trackingServer` e [`trackingServerSecure`](trackingserversecure.md) variabili, `visitorNameSpace` non è più necessario.

>[!TIP]
>
>L’Adobe consiglia di utilizzare cookie di prime parti sul sito. I cookie di prime parti non utilizzano questa variabile.

## Spazio dei nomi del visitatore che utilizza l’estensione Adobe Analytics

[!UICONTROL Visitor Namespace] è un campo sotto [!UICONTROL Cookies] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Cookies], che mostra il campo [!UICONTROL Visitor Namespace].

L’Adobe consiglia di non utilizzare questo campo. Utilizzare `trackingServer` e `trackingServerSecure` invece.

## s.visitorNamespace in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.visitorNamespace` variabile è una stringa che contiene un valore univoco per organizzazione. Le vecchie librerie AppMeasurement includevano automaticamente questo valore univoco quando venivano scaricate da versioni precedenti di Adobe Analytics. Le librerie AppMeasurement attuali non utilizzano questa variabile a meno che `trackingServer` e `trackingServerSecure` non sono impostati.

Se l’organizzazione richiede ancora questa variabile, scegli un valore che rappresenti l’organizzazione. Puoi memorizzare questo valore in una [documento di progettazione della soluzione](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
