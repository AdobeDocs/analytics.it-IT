---
title: usePlugins
description: Attiva o disattiva la funzione doPlugins().
feature: Appmeasurement Implementation
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
TQID: https://experienceleague.adobe.com/nv3QjXjcqA6WZhF6GxsGxoHTcvH-2pl4Xd7EY4cIlzA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 1%

---

# usePlugins

Se `usePlugins` è abilitato, la funzione [`doPlugins()`](../functions/doplugins.md) viene eseguita immediatamente prima della compilazione di AppMeasurement e invia un hit ad Adobe. Abilitare questa variabile se si utilizza la funzione `doPlugins()`.

## Utilizza il callback `onBeforeEventSend` tramite Web SDK

Sebbene il Web SDK non disponga di un valore booleano per gestire l&#39;esecuzione di una logica aggiuntiva prima che i dati vengano inviati ad Adobe, è possibile registrare il callback `onBeforeEventSend` per modificare i dati. Per ulteriori informazioni, vedere [Modifica globale degli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=it#modifying-events-globally) nella documentazione di Web SDK.

## Utilizzare i plug-in tramite l’estensione Adobe Analytics

Adobe fornisce un&#39;estensione denominata &#39;Common Analytics Plugins&#39; che consente di chiamare la maggior parte dei [plug-in](../plugins/impl-plugins.md). Installa l’estensione e chiama il plug-in desiderato all’interno di una regola.

Se il plug-in desiderato non è incluso nell’estensione Adobe, utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.usePlugins in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.usePlugins` è un valore booleano che determina se AppMeasurement chiama la funzione `doPlugins()`. Il valore predefinito è `false`. Impostare questa variabile su `true` se si utilizza la funzione `doPlugins()` nell&#39;implementazione.

```js
s.usePlugins = true;
```
