---
title: forceOnline
description: Imposta manualmente lo stato online di AppMeasurement.
feature: Appmeasurement Implementation
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 15%

---

# forceOnline

Il metodo `forceOnline()` consente di ignorare lo stato rilevato automaticamente di AppMeasurement.

>[!WARNING]
>
>Utilizzare questo metodo solo quando [`trackOffline`](../config-vars/trackoffline.md) è abilitato. L’utilizzo di questa funzione al di fuori del tracciamento offline può causare la perdita di dati.

AppMeasurement rileva automaticamente lo stato online del dispositivo. È possibile utilizzare il metodo `forceOnline()` per forzare AppMeasurement a trattare gli hit come se il dispositivo fosse online. Questo metodo non accetta argomenti e non restituisce alcun valore. Il suo unico scopo è quello di ignorare lo stato online in AppMeasurement.

## Forza in linea tramite Web SDK

Il Web SDK non supporta il tracciamento offline.

## Forza in linea utilizzando l&#39;estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.forceOnline() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Puoi chiamare il metodo `s.forceOnline()` in qualsiasi punto dell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.forceOnline();
```
