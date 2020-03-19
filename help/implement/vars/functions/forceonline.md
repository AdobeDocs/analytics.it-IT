---
title: forceOnline
description: Imposta manualmente lo stato online di AppMeasurement.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# forceOnline

Il `forceOnline()` metodo consente di ignorare lo stato rilevato automaticamente di AppMeasurement.

> [!IMPORTANT] Utilizzare questo metodo solo se [`trackOffline`](../config-vars/trackoffline.md) è abilitato. L&#39;utilizzo di questa funzione al di fuori del tracciamento offline può causare la perdita di dati.

AppMeasurement rileva automaticamente lo stato online del dispositivo. Puoi usare il `forceOnline()` metodo per forzare AppMeasurement a trattare gli hit come se il dispositivo fosse online. Questo metodo non accetta argomenti e non restituisce alcun valore. Il suo unico scopo è quello di ignorare lo stato online in AppMeasurement.

## Forza online sul lancio di Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.forceOnline() in AppMeasurement e Avvia editor di codice personalizzato

Puoi chiamare il `s.forceOnline()` metodo ovunque nell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.forceOnline();
```
