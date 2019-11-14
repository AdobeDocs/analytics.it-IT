---
description: La segmentazione dei percorsi in base al tipo di utente è una richiesta comune per cercare di capire in che modo specifici tipi di utente si trovano sul sito.
keywords: Analytics Implementation
solution: Analytics
title: Percorsi di segmento per tipo di utente
topic: Developer and implementation
uuid: 5c298f39-381d-453b-a608-109e3276b361
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Percorsi di segmento per tipo di utente

La segmentazione dei percorsi in base al tipo di utente è una richiesta comune per cercare di capire in che modo specifici tipi di utente si trovano sul sito.

È possibile concatenare il tipo utente e il nome della pagina in un percorso [!UICONTROL sprop] e abilitare il percorso sul [!UICONTROL sprop].

Ad esempio, supponiamo che siano disponibili due tipi di utente: Utenti _registrati_ e utenti _non registrati_ . È necessario distinguere tra questi due tipi di utente su ciascuna pagina e inserire questi valori nel gruppo [!UICONTROL sprop]designato. Quando compilate il prop, dovrebbe essere visualizzato come mostrato di seguito:

```js
 s.prop1="Registered : " + s.pageName;
```

Se l’utente è registrato e ha visitato la pagina principale, il valore nella proprietà viene visualizzato come segue:

```js
 "Registered : Home Page"
```

Se fanno clic su un'altra pagina denominata "Pagina 2", il valore di tale pagina viene visualizzato come segue:

```js
 "Registered : Page 2"
```

Con [!UICONTROL Pathing] attivato, questi due valori vengono visualizzati in successione. Per sapere come si spostano gli utenti registrati dalla home page, trovate il valore "Registrato: Home Page" in uno dei rapporti sui percorsi e vedere le pagine successive che hanno visitato. In questo caso, passarono poi a "Pagina 2".
