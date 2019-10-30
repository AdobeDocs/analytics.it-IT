---
description: Analytics conta ogni singolo ID visitatore effettivo come visitatore unico.
keywords: Implementazione di Analytics
seo-description: Analytics conta ogni singolo ID visitatore effettivo come visitatore unico.
seo-title: Visitatori
solution: Analytics
subtopic: Visitatori
title: Visitatori
topic: Sviluppatore e implementazione
uuid: 16cfdb64-a3c6-4056-97da-3227cdcf1cd
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Visitatori

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Fai riferimento alla documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud Device Co-op.

Analytics conta ogni singolo ID visitatore effettivo come visitatore unico.

Se si osserva la tabella [](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA)precedente, si è verificato 3 volte: ai punti 1, 9 e 10. Ciò si verifica perché l’effetto effettivo [!UICONTROL visitor ID] è lo stesso per entrambe le chiamate server e si verifica anche se le visite potrebbero essere diverse ore di distanza e su dispositivi diversi.

Questo può aumentare il numero di visitatori univoci che vengono visualizzati quando è abilitata l'identificazione dei visitatori su più dispositivi. Il visitatore potrebbe essere conteggiato due volte nella stessa visita: una volta per la visita iniziale e una volta autenticato l’utente.

Quando un nuovo visitatore visualizza il sito, il `s_vi`cookie viene popolato e memorizzato. Nel server di raccolta dati, viene creato un nuovo profilo visitatore per questo ID visitatore e l'efficacia [!UICONTROL visitor ID] del profilo viene impostata in modo che corrisponda al cookie.

Quando è abilitata l'identificazione dei visitatori tra dispositivi, se una [!UICONTROL visitor ID] variabile viene fornita in un hit successivo (ad esempio, dopo l'autenticazione), l'effettiva [!UICONTROL visitor ID] viene aggiornata per corrispondere al valore personalizzato. Questo può causare la modifica diretta [!UICONTROL visitor ID] dell’effettivo dopo l’autenticazione, generando così più conteggi dei visitatori.

![](assets/visitors.png)

Dopo l'associazione iniziale, il conteggio delle visite torna alla normalità perché il visitatore è associato tramite il [!UICONTROL visitor ID] cookie. Se il visitatore visualizza in un secondo momento il sito e quindi si autentica, il conteggio dei visitatori non viene ingrandito perché l’effetto [!UICONTROL visitor ID] non cambia dopo l’autenticazione.

![](assets/visitors_2.png)

