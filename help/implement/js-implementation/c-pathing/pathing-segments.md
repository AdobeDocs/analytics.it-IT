---
description: La segmentazione dei percorsi per tipo utente è una richiesta comune per capire in che modo i tipi di utente specifici sul sito.
keywords: Implementazione di Analytics
seo-description: La segmentazione dei percorsi per tipo utente è una richiesta comune per capire in che modo i tipi di utente specifici sul sito.
seo-title: Segmenti di segmenti per tipo utente
solution: Analytics
title: Segmenti di segmenti per tipo utente
topic: Sviluppatore e implementazione
uuid: 5 c 298 f 39-381 d -453 b-a 608-109 e 3276 b 361
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Segmenti di segmenti per tipo utente

La segmentazione dei percorsi per tipo utente è una richiesta comune per capire in che modo i tipi di utente specifici sul sito.

You can concatenate the user type and page name into a [!UICONTROL sprop] and enable pathing on the [!UICONTROL sprop].

For example, let's say you have two user types: _Registered_ users and _Non-Registered_ users. You need to distinguish between these two user types on each page and put these values into your designated [!UICONTROL sprop]. Quando si compila il prop, viene visualizzato come mostrato di seguito:

```js
 s.prop1=”Registered : “ + s.pageName;
```

Se l'utente è registrato e accede alla home page, il valore nel prop viene visualizzato come segue:

```js
 “Registered : Home Page”
```

Se fanno clic su un'altra pagina denominata "Page 2", il valore della pagina viene visualizzato come segue:

```js
 “Registered : Page 2”
```

With [!UICONTROL Pathing] turned on, you see those two values in succession. Per sapere in che modo gli utenti registrati si spostano dalla home page, individua il valore «Registrati: Home Page (Pagina iniziale) in uno dei rapporti sul percorso e vedi le pagine successive visitate. In questo caso, questi sono passati a "Page 2".
