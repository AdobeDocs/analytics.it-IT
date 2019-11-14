---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 0c7093518933a88c5057ba95cb3564d6ca0ebcad

---



# s.forzatoLinkTrackingTimeout

Questo valore specifica il tempo massimo di attesa. In particolare, imposta il numero massimo di millisecondi di attesa per il completamento del tracciamento prima di eseguire il `doneAction` passaggio in `s.tl`. Se la chiamata di tracciamento dei collegamenti viene completata prima di questo timeout, l’operazione `doneAction` viene eseguita immediatamente. Se noti che le chiamate di tracciamento dei collegamenti non vengono completate, potresti dover aumentare questo timeout.

Valore predefinito = 250

Esempio: `s.forcedLinkTrackingTimeout = 500`
