---
title: usePlugins
description: Attiva o disattiva la funzione doPlugins() .
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 41154580c272514e504c5478215bb67795488de3
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 1%

---

# usePlugins

Se `usePlugins` è abilitato, [`doPlugins()`](../functions/doplugins.md) viene eseguita immediatamente prima della compilazione di AppMeasurement e invia un hit ad Adobe. Abilita questa variabile se utilizzi la variabile `doPlugins()` funzione .

## Utilizza la `onBeforeEventSend` callback utilizzando l’SDK per web

Anche se l’SDK web non dispone di un valore booleano per gestire l’esecuzione di una logica aggiuntiva prima che i dati vengano inviati ad Adobe, puoi registrare il `onBeforeEventSend` callback per modificare i dati. Vedi [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione SDK per web .

## Utilizzare i plug-in utilizzando l’estensione Adobe Analytics

Adobe fornisce un&#39;estensione con etichetta &quot;Common Analytics Plugins&quot; che consente di chiamare la maggior parte [Plug-in](../plugins/impl-plugins.md). Installa l&#39;estensione e chiama il plug-in desiderato all&#39;interno di una regola.

Se il plug-in desiderato non è incluso nell&#39;estensione Adobe, utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.usePlugins in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.usePlugins` è una variabile booleana che determina se AppMeasurement chiama il `doPlugins()` funzione . Il valore predefinito è `false`. Imposta questa variabile su `true` se utilizzi `doPlugins()` nella tua implementazione.

```js
s.usePlugins = true;
```
