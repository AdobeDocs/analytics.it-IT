---
title: useBeacon
description: useBeacon consente di forzare AppMeasurement a utilizzare l'API sendBeacon dei browser
keywords: Analytics Implementation
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# s.useBeacon

La `s.useBeacon` variabile forza la richiesta successiva a utilizzare l'API [](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)sendBeacon del browser. Utilizzando `s.sendBeacon` è possibile inviare una richiesta HTTP all’esterno del contesto di una pagina. È utile per i collegamenti di uscita e altre situazioni in cui si desidera inviare informazioni prima che la pagina venga scaricata.

L'impostazione di questo valore si applica solo alla richiesta successiva attivata da AppMeasurement. Dopo l'attivazione della richiesta, `s.useBeacon` viene reimpostata su false. Questa variabile si applica sia alle richieste `s.t()` che alle richieste di `s.tl()` immagini.

L'utilizzo della `s.useBeacon` variabile richiede AppMeasurement 2.17.0 o versione successiva.

> [!NOTE] La variabile [Exit Links](s-linktrackvars.md) viene utilizzata automaticamente senza ulteriori configurazioni.

## Sintassi

```js
s.useBeacon = true;
```
