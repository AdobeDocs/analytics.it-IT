---
title: Risolvere i problemi relativi alle implementazioni del codice H
description: Scopri alcuni problemi comuni con le implementazioni JavaScript legacy.
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# Risolvere i problemi relativi alle implementazioni del codice H

Di seguito sono riportati i passaggi per la risoluzione dei problemi specifici per le implementazioni del codice H.

## Inserimento del codice Analytics nel tag head

>[!NOTE]
>
>Anche se le implementazioni del codice H richiedono un riferimento al codice nel `<body>` tag, altre implementazioni (come l&#39;utilizzo di tag in Adobe Experience Platform) richiedono che il codice sia referenziato nel `<head>` tag .

Il codice di Analytics crea un&#39;immagine invisibile da 1 pixel x 1. In precedenza, una pratica comune di implementazione era quella di inserire la variabile `s_code.js` nel `<head>` tag . Posizionare il codice in questo punto impediva all&#39;immagine di influenzare il layout di pagina in qualsiasi modo. Viene inoltre eseguito prima, consentendo di contare le visualizzazioni di pagina per il caricamento parziale della pagina in modo più efficace.

Tuttavia, alcuni elementi del codice richiedono l&#39;esistenza di `<body>` oggetto. Se il codice JavaScript di Analytics si trova nella variabile `<head>` viene eseguito prima del `<body>` oggetto esistente. Di conseguenza, l’implementazione non raccoglie [!UICONTROL ClickMap] dati, tracciamento automatico dei file scaricati o dei collegamenti di uscita o dei dati del tipo di connessione. Inserimento del riferimento allo script in `s_code.js` in `<head>` Il tag funziona, ma il risultato è una versione molto limitata di Analytics.

Il codice Analytics può essere posizionato ovunque all&#39;interno della `<body>` tag di una pagina HTML ben formata. Adobe consiglia di posizionare il codice Analytics nella parte superiore della `<body>` tag il più possibile. Assicurati che tutte le variabili di pagina siano impostate dopo la `s_code.js` viene caricato il file.

>[!TIP]
>
>Se desideri integrare Adobe Analytics con Adobe Target, il file di inclusione JavaScript deve trovarsi nella parte inferiore della pagina.
