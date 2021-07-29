---
title: visitorNameSpace
description: È stata ritirata la variabile che determinava il dominio dei cookie.
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# visitorNamespace

>[!IMPORTANT]
>
>Questa variabile è ritirata. Utilizza invece [`trackingServer`](trackingserver.md) .

Nelle versioni precedenti di Adobe Analytics, AppMeasurement utilizzava la variabile `visitorNameSpace` per determinare il sottodominio di `2o7.net` in cui sono memorizzati i cookie del visitatore. L’aumento delle pratiche di privacy nei browser moderni rende i cookie di terze parti meno affidabili. Con l’introduzione delle variabili `trackingServer` e [`trackingServerSecure`](trackingserversecure.md), `visitorNameSpace` non è più necessario.

>[!TIP]
>
>Adobe consiglia di utilizzare cookie di prime parti sul sito. I cookie di prime parti non utilizzano questa variabile.

## Spazio dei nomi dei visitatori che utilizza i tag in Adobe Experience Platform

[!UICONTROL Visitor Namespace] è un campo a  [!UICONTROL Cookies] soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL Cookies] pannello a soffietto, che mostra il campo [!UICONTROL Visitor Namespace] .

L’Adobe sconsiglia di utilizzare questo campo. Utilizza invece `trackingServer` e `trackingServerSecure` .

## s.visitorNamespace in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.visitorNamespace` è una stringa che contiene un valore univoco per organizzazione. Le vecchie librerie AppMeasurement includevano automaticamente questo valore univoco quando vengono scaricate dalle versioni precedenti di Adobe Analytics. Le librerie AppMeasurement correnti non utilizzano questa variabile a meno che `trackingServer` e `trackingServerSecure` non siano impostate.

Se la tua organizzazione richiede ancora questa variabile, scegli un valore che rappresenta la tua organizzazione. Puoi memorizzare questo valore in un [documento di progettazione della soluzione](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
