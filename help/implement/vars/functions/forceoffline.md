---
title: forceOffline
description: Imposta manualmente lo stato online di AppMeasurement.
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 1%

---

# forceOffline

Il metodo `forceOffline()` ti consente di ignorare lo stato rilevato automaticamente di AppMeasurement.

>[!IMPORTANT]
>
>Utilizza questa funzione solo quando [`trackOffline`](../config-vars/trackoffline.md) è abilitato. L&#39;utilizzo di questa funzione al di fuori del tracciamento offline può causare la perdita di dati.

AppMeasurement rileva automaticamente lo stato online del dispositivo. Puoi utilizzare il metodo `forceOffline()` per forzare AppMeasurement a trattare gli hit come se il dispositivo fosse offline. Questo metodo non accetta argomenti e non restituisce alcun valore. L’unico scopo è quello di ignorare lo stato online in AppMeasurement.

## Force Offline using tags in Adobe Experience Platform (Forza offline utilizzando i tag in)

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.forceOffline() in AppMeasurement e nell&#39;editor di codice personalizzato

È possibile chiamare il metodo `s.forceOffline()` in qualsiasi punto dell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.forceOffline();
```
