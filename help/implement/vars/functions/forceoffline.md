---
title: forceOffline
description: Imposta manualmente lo stato online di AppMeasurement.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# forceOffline

Il `forceOffline()` metodo consente di ignorare lo stato rilevato automaticamente di AppMeasurement.

>[!IMPORTANT] Utilizzare questa funzione solo quando [`trackOffline`](../config-vars/trackoffline.md) è abilitata. L&#39;utilizzo di questa funzione al di fuori del tracciamento offline può causare la perdita di dati.

AppMeasurement rileva automaticamente lo stato online del dispositivo. Puoi usare il `forceOffline()` metodo per forzare AppMeasurement a trattare gli hit come se il dispositivo fosse offline. Questo metodo non accetta argomenti e non restituisce alcun valore. Il suo unico scopo è quello di ignorare lo stato online in AppMeasurement.

## Forza offline nel lancio di Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.forceOffline() nell&#39;editor di codice personalizzato AppMeasurement e Launch

Puoi chiamare il `s.forceOffline()` metodo ovunque nell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.forceOffline();
```
