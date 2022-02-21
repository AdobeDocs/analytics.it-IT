---
title: forceOnline
description: Imposta manualmente lo stato online di AppMeasurement.
feature: Variables
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 1%

---

# forceOnline

La `forceOnline()` consente di ignorare lo stato rilevato automaticamente di AppMeasurement.

>[!IMPORTANT]
>
>Usa questo metodo solo quando [`trackOffline`](../config-vars/trackoffline.md) è abilitato. L&#39;utilizzo di questa funzione al di fuori del tracciamento offline può causare la perdita di dati.

AppMeasurement rileva automaticamente lo stato online del dispositivo. È possibile utilizzare `forceOnline()` per forzare AppMeasurement a trattare gli hit come se il dispositivo fosse online. Questo metodo non accetta argomenti e non restituisce alcun valore. L’unico scopo è quello di ignorare lo stato online in AppMeasurement.

## Force Online using tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.forceOnline() in AppMeasurement e nell&#39;editor di codice personalizzato

Puoi chiamare il `s.forceOnline()` in qualsiasi punto dell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.forceOnline();
```
