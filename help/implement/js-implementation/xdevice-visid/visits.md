---
description: Analytics conta una visita ogni volta che si verifica una chiamata al server con un numero di pagina visita uguale a 1.
keywords: Implementazione di Analytics
seo-description: Analytics conta una visita ogni volta che si verifica una chiamata al server con un numero di pagina visita uguale a 1.
seo-title: Visite
solution: Analytics
subtopic: Visitatori
title: Visite
topic: Sviluppatore e implementazione
uuid: 3035be8f-6adc-45df-a3f2-5de6d3ed99ce
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Visite

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Fai riferimento alla documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud Device Co-op.

Analytics conta una visita ogni volta che si verifica una chiamata al server con un numero di pagina visita uguale a 1.

Se si osserva la tabella [](/help/implement/js-implementation/xdevice-visid/visit-example.md)precedente, si è verificato 4 volte: alle hit 1, 9, 11 e 12. Simile ai visitatori, questo valore torna alla normalità dopo l'associazione iniziale perché [!UICONTROL Visit Page Number] viene reimpostato su 1 a causa di una modifica nell'effetto [!UICONTROL visitor ID].
