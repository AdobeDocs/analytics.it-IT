---
title: usePlugins
description: Attiva o disattiva la funzione doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 15%

---

# usePlugins

Se `usePlugins` è attivato, il [`doPlugins()`](../functions/doplugins.md) viene eseguita subito prima della compilazione di AppMeasurement e invia un hit all’Adobe. Abilita questa variabile se utilizzi il `doPlugins()` funzione.

## Utilizza il `onBeforeEventSend` callback tramite Web SDK

Anche se l’SDK per web non dispone di un valore booleano per gestire l’esecuzione di una logica aggiuntiva prima che i dati vengano inviati all’Adobe, puoi registrare `onBeforeEventSend` callback per modificare i dati. Consulta [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

## Utilizzare i plug-in tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.usePlugins in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.usePlugins` è un valore booleano che determina se AppMeasurement chiama `doPlugins()` funzione. Il valore predefinito è `false`. Imposta questa variabile su `true` se utilizza `doPlugins()` nell&#39;implementazione.

```js
s.usePlugins = true;
```
