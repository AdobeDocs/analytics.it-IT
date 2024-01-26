---
title: usePlugins
description: Attiva o disattiva la funzione doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 1%

---

# usePlugins

Se `usePlugins` è attivato, il [`doPlugins()`](../functions/doplugins.md) la funzione viene eseguita subito prima della compilazione di AppMeasurement e invia un hit a Adobe. Abilita questa variabile se utilizzi il `doPlugins()` funzione.

## Utilizza il `onBeforeEventSend` callback tramite Web SDK

Anche se l’SDK per web non dispone di un valore booleano per gestire l’esecuzione di una logica aggiuntiva prima che i dati vengano inviati all’Adobe, puoi registrare `onBeforeEventSend` callback per modificare i dati. Consulta [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

## Utilizzare i plug-in tramite l’estensione Adobe Analytics

L’Adobe fornisce un’estensione denominata &quot;Common Analytics Plugins&quot; che consente di chiamare la maggior parte dei [Plug-in](../plugins/impl-plugins.md). Installa l’estensione e chiama il plug-in desiderato all’interno di una regola.

Se il plug-in desiderato non è incluso nell’estensione Adobe, utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.usePlugins in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.usePlugins` è un valore booleano che determina se AppMeasurement chiama `doPlugins()` funzione. Il valore predefinito è `false`. Imposta questa variabile su `true` se utilizza `doPlugins()` nell&#39;implementazione.

```js
s.usePlugins = true;
```
