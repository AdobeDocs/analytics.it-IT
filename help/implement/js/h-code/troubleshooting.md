---
title: Risolvere i problemi relativi alle implementazioni del codice H
description: Scopri alcuni problemi comuni con le implementazioni JavaScript legacy.
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# Risolvere i problemi relativi alle implementazioni del codice H

Di seguito sono riportati i passaggi per la risoluzione dei problemi specifici per le implementazioni del codice H.

## Inserimento del codice Analytics nel tag head

>[!NOTE]
>
>Anche se per le implementazioni del codice H è necessario fare riferimento al codice nel tag `<body>` , altre implementazioni (come l&#39;utilizzo di tag in Adobe Experience Platform) richiedono che il codice sia referenziato nel tag `<head>` .

Il codice di Analytics crea un&#39;immagine invisibile da 1 pixel x 1. In precedenza, una pratica comune di implementazione consisteva nell’inserire il riferimento `s_code.js` nel tag `<head>` . Posizionare il codice in questo punto impediva all&#39;immagine di influenzare il layout di pagina in qualsiasi modo. Viene inoltre eseguito prima, consentendo di contare le visualizzazioni di pagina per il caricamento parziale della pagina in modo più efficace.

Tuttavia, alcuni elementi del codice richiedono l’esistenza dell’oggetto `<body>` . Se il codice JavaScript di Analytics si trova nel tag `<head>` , viene eseguito prima che l&#39;oggetto `<body>` esista. Di conseguenza, l’implementazione non raccoglie dati [!UICONTROL ClickMap], il tracciamento automatico dei file scaricati o dei collegamenti di uscita o dei dati del tipo di connessione. L’inserimento del riferimento allo script in `s_code.js` nel tag `<head>` funziona, ma il risultato è una versione molto limitata di Analytics.

Il codice Analytics può essere posizionato ovunque all&#39;interno del tag `<body>` di una pagina HTML ben formata. Adobe consiglia di posizionare il codice Analytics il più vicino possibile alla parte superiore del tag `<body>` . Assicurati che tutte le variabili di pagina siano impostate dopo il caricamento del file `s_code.js` .

>[!TIP]
>
>Se desideri integrare Adobe Analytics con Adobe Target, il file di inclusione JavaScript deve trovarsi nella parte inferiore della pagina.
