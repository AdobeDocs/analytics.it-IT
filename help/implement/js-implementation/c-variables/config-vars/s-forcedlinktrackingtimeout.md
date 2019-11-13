---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---



# s.forzatoLinkTrackingTimeout

Il numero massimo di millisecondi di attesa del termine del tracciamento prima di eseguire l'oggetto doneAction passato in `s.tl`. Questo valore specifica il tempo massimo di attesa. Se la chiamata di tracciamento dei collegamenti viene completata prima di questo timeout, l’azione done viene eseguita immediatamente. Se noti che le chiamate di tracciamento dei collegamenti non vengono completate, potresti dover aumentare questo timeout.

Valore predefinito = 250

Esempio: `s.forcedLinkTrackingTimeout = 500`
