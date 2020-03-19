---
title: visitorNameSpace
description: Variabile ritirata che ha determinato il dominio del cookie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# visitorNamespace

> [!IMPORTANT] Questa variabile è ritirata. Usa [`trackingServer`](trackingserver.md) invece.

Nelle versioni precedenti di Adobe Analytics, AppMeasurement utilizzava la `visitorNameSpace` variabile per determinare il sottodominio di `2o7.net` dove vengono memorizzati i cookie dei visitatori. L&#39;aumento delle pratiche di privacy nei browser moderni rende meno affidabili i cookie di terze parti. Con l&#39;introduzione delle `trackingServer` variabili e delle [`trackingServerSecure`](trackingserversecure.md) variabili, non `visitorNameSpace` è più necessario.

> [!TIP] Adobe consiglia di utilizzare cookie di prime parti sul sito. I cookie di prime parti non utilizzano questa variabile.

## Spazio dei nomi dei visitatori in Adobe Experience Platform Launch

[!UICONTROL Visitor Namespace] è un campo situato sotto la [!UICONTROL Cookies] struttura di navigazione durante la configurazione dell’estensione Adobe Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante in Adobe Analytics.
4. Espandere la [!UICONTROL Cookies] struttura a soffietto, che mostra il [!UICONTROL Visitor Namespace] campo.

Adobe consiglia di non utilizzare questo campo. Usa `trackingServer` e `trackingServerSecure` invece.

## s.visitorNamespace nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.visitorNamespace` variabile è una stringa che contiene un valore univoco per organizzazione. Le vecchie librerie AppMeasurement includevano automaticamente questo valore univoco quando venivano scaricate dalle versioni precedenti di Adobe Analytics. Le librerie AppMeasurement correnti non utilizzano questa variabile a meno che `trackingServer` e non `trackingServerSecure` siano impostate.

Se la vostra organizzazione richiede ancora questa variabile, scegliete un valore che rappresenti la vostra organizzazione. È possibile memorizzare questo valore in un documento [di progettazione di una](../../prepare/solution-design.md)soluzione.

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
