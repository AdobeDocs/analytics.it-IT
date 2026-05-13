---
title: Risoluzione dei problemi relativi alle implementazioni del codice H
description: Scopri alcuni problemi comuni relativi alle implementazioni legacy di JavaScript.
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
role: Developer
TQID: https://experienceleague.adobe.com/DootwtTj5kDIRHKhFPeY3Fnt3bWdVLsXc6J3UEc5LPI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 245
ht-degree: 0%

---

# Risoluzione dei problemi relativi alle implementazioni del codice H

Di seguito sono riportati i passaggi di risoluzione dei problemi specifici per le implementazioni del codice H.

## Inserimento del codice Analytics nel tag head

>[!NOTE]
>
>Mentre le implementazioni del codice H richiedono che nel tag `<body>` venga fatto riferimento al codice, altre implementazioni (come l&#39;utilizzo di tag in Adobe Experience Platform) richiedono che nel tag `<head>` venga fatto riferimento al codice.

Il codice di Analytics crea un’immagine invisibile di 1x1 pixel. In precedenza, una pratica comune di implementazione prevedeva di inserire il riferimento `s_code.js` nel tag `<head>`. Inserendo qui il codice si evita che l’immagine influisca in alcun modo sul layout della pagina. Viene anche eseguito prima, il che consente di contare le visualizzazioni di pagina per i caricamenti di pagina parziali in modo più efficace.

Tuttavia, alcuni elementi del codice richiedono l&#39;esistenza dell&#39;oggetto `<body>`. Se il codice JavaScript di Analytics si trova nel tag `<head>`, viene eseguito prima dell&#39;esistenza dell&#39;oggetto `<body>`. Di conseguenza, l&#39;implementazione non raccoglie i dati di [!UICONTROL ClickMap], il tracciamento automatico dei download di file o dei collegamenti di uscita, né i dati del tipo di connessione. L&#39;inserimento del riferimento script in `s_code.js` nel tag `<head>` funziona, ma il risultato è una versione di Analytics molto limitata.

Il codice Analytics può essere posizionato ovunque all&#39;interno del tag `<body>` di una pagina HTML ben formata. Adobe consiglia di posizionare il codice Analytics il più vicino possibile alla parte superiore del tag `<body>`. Verificare che tutte le variabili di pagina siano impostate dopo il caricamento del file `s_code.js`.

>[!TIP]
>
>Se desideri integrare Adobe Analytics con Adobe Target, il file di inclusione JavaScript deve essere posizionato nella parte inferiore della pagina.
