---
title: usePlugins
description: Attiva o disattiva la funzione doPlugins() .
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# usePlugins

Se `usePlugins` è abilitato, [`doPlugins()`](../functions/doplugins.md) viene eseguita immediatamente prima della compilazione di AppMeasurement e invia un hit ad Adobe. Abilita questa variabile se utilizzi la variabile `doPlugins()` funzione .

## Utilizza la `onBeforeEventSend` callback utilizzando l’SDK per web

Anche se l’SDK web non dispone di un valore booleano per gestire l’esecuzione di una logica aggiuntiva prima che i dati vengano inviati ad Adobe, puoi registrare il `onBeforeEventSend` callback per modificare i dati. Vedi [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione SDK per web .

## Utilizzare i plug-in utilizzando l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.usePlugins in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.usePlugins` è una variabile booleana che determina se AppMeasurement chiama il `doPlugins()` funzione . Il valore predefinito è `false`. Imposta questa variabile su `true` se utilizzi `doPlugins()` nella tua implementazione.

```js
s.usePlugins = true;
```
