---
title: Risoluzione dei problemi relativi alle implementazioni del codice H
description: Scopri alcuni problemi comuni relativi alle implementazioni legacy di JavaScript.
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Risoluzione dei problemi relativi alle implementazioni del codice H

Di seguito sono riportati i passaggi di risoluzione dei problemi specifici per le implementazioni del codice H.

## Inserimento del codice Analytics nel tag head

>[!NOTE]
>
>Mentre le implementazioni del codice H richiedono che si faccia riferimento al codice nel `<body>` , altre implementazioni (come l’utilizzo di tag in Adobe Experience Platform) richiedono che venga fatto riferimento al codice nel `<head>` tag.

Il codice di Analytics crea un’immagine invisibile di 1x1 pixel. Precedentemente, una pratica comune di implementazione prevedeva di collocare `s_code.js` riferimento in `<head>` tag. Inserendo qui il codice si evita che l’immagine influisca in alcun modo sul layout della pagina. Viene anche eseguito prima, il che consente di contare le visualizzazioni di pagina per i caricamenti di pagina parziali in modo più efficace.

Tuttavia, alcuni elementi del codice richiedono l&#39;esistenza di `<body>` oggetto. Se il codice JavaScript di Analytics si trova in `<head>` , viene eseguito prima del `<body>` l&#39;oggetto esiste. Di conseguenza, l’implementazione non raccoglie [!UICONTROL ClickMap] dati, tracciamento automatico dei download di file o dei collegamenti di uscita o dati del tipo di connessione. Inserimento del riferimento script in `s_code.js` nel `<head>` funziona, ma il risultato è una versione molto limitata di Analytics.

Il codice Analytics può essere posizionato ovunque all’interno del `<body>` di una pagina HTML ben formata. L’Adobe consiglia di posizionare il codice Analytics il più vicino possibile alla parte superiore del `<body>` tag il più possibile. Assicurati che tutte le variabili di pagina siano impostate dopo il `s_code.js` caricamenti di file.

>[!TIP]
>
>Se desideri integrare Adobe Analytics con Adobe Target, il file di inclusione JavaScript deve essere posizionato nella parte inferiore della pagina.
