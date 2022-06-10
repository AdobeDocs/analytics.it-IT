---
title: forceOnline
description: Imposta manualmente lo stato online di AppMeasurement.
feature: Variables
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# forceOnline

La `forceOnline()` consente di ignorare lo stato rilevato automaticamente di AppMeasurement.

>[!WARNING]
>
>Usa questo metodo solo quando [`trackOffline`](../config-vars/trackoffline.md) è abilitato. L&#39;utilizzo di questa funzione al di fuori del tracciamento offline può causare la perdita di dati.

AppMeasurement rileva automaticamente lo stato online del dispositivo. È possibile utilizzare `forceOnline()` per forzare AppMeasurement a trattare gli hit come se il dispositivo fosse online. Questo metodo non accetta argomenti e non restituisce alcun valore. L’unico scopo è quello di ignorare lo stato online in AppMeasurement.

## Forza l&#39;utilizzo dell&#39;SDK per web

L&#39;SDK per web non supporta il tracciamento offline.

## Force online using the Adobe Analytics extension

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.forceOnline() in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

Puoi chiamare il `s.forceOnline()` in qualsiasi punto dell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.forceOnline();
```
