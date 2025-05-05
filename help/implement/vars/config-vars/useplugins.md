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

Se `usePlugins` è abilitato, la funzione [`doPlugins()`](../functions/doplugins.md) viene eseguita immediatamente prima della compilazione di AppMeasurement e invia un hit a Adobe. Abilitare questa variabile se si utilizza la funzione `doPlugins()`.

## Utilizza il callback `onBeforeEventSend` tramite Web SDK

Sebbene l&#39;SDK Web non disponga di un valore booleano per gestire l&#39;esecuzione di una logica aggiuntiva prima che i dati vengano inviati all&#39;Adobe, è possibile registrare il callback `onBeforeEventSend` per modificare i dati. Per ulteriori informazioni, consulta [Modifica globale degli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=it#modifying-events-globally) nella documentazione di Web SDK.

## Utilizzare i plug-in tramite l’estensione Adobe Analytics

L&#39;Adobe fornisce un&#39;estensione denominata &#39;Common Analytics Plugins&#39; che consente di chiamare la maggior parte dei [plug-in](../plugins/impl-plugins.md). Installa l’estensione e chiama il plug-in desiderato all’interno di una regola.

Se il plug-in desiderato non è incluso nell’estensione Adobe, utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.usePlugins in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.usePlugins` è un valore booleano che determina se AppMeasurement chiama la funzione `doPlugins()`. Il valore predefinito è `false`. Impostare questa variabile su `true` se si utilizza la funzione `doPlugins()` nell&#39;implementazione.

```js
s.usePlugins = true;
```
