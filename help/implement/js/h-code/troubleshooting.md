---
title: Risoluzione dei problemi di implementazione del codice H
description: Scopri alcuni problemi comuni con le implementazioni JavaScript precedenti.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%

---


# Risoluzione dei problemi di implementazione del codice H

Di seguito sono riportati i passaggi per la risoluzione dei problemi specifici per le implementazioni del codice H.

## Inserimento del codice Analytics nel tag head

>[!NOTE]
>
>Mentre per le implementazioni del codice H è necessario fare riferimento al codice nel `<body>` tag, altre implementazioni (come l&#39;utilizzo  lancio del Adobe Experience Platform) richiedono che il codice sia incluso nel `<head>` tag .

 codice Analytics crea un’immagine invisibile di 1 x 1 pixel. Precedentemente, una pratica di implementazione comune era quella di inserire il `s_code.js` riferimento nel `<head>` tag . L’inserimento del codice in questo campo ha impedito all’immagine di influenzare il layout di pagina in qualsiasi modo. Inoltre, viene eseguito prima, consentendo di contare in modo più efficace le visualizzazioni di pagina per i caricamenti parziali delle pagine.

Tuttavia, alcuni elementi del codice richiedono l&#39;esistenza dell&#39; `<body>` oggetto. Se il codice JavaScript di Analytics  è presente nel `<head>` tag, viene eseguito prima dell&#39;esistenza dell&#39; `<body>` oggetto. Di conseguenza, l&#39;implementazione non raccoglie [!UICONTROL ClickMap] dati, il tracciamento automatico dei download di file o dei collegamenti di uscita, o i dati del tipo di connessione. L&#39;inserimento del riferimento allo script `s_code.js` nel `<head>` tag funziona, ma il risultato è una versione molto limitata di  Analytics.

Il codice Analytics  può essere posizionato ovunque all&#39;interno del `<body>` tag di una pagina HTML ben formata. Adobe consiglia di posizionare  codice Analytics il più vicino possibile alla parte superiore del `<body>` tag . Accertatevi che tutte le variabili di pagina siano impostate dopo il caricamento del `s_code.js` file.

>[!TIP]
>
>Se desiderate integrare Adobe  Analytics con  Adobe Target, il file JavaScript include deve essere posizionato in fondo alla pagina.
