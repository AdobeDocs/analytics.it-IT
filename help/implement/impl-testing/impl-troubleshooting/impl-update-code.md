---
description: Adobe offre alcune best practice per aggiornare il codice Analytics.
keywords: Implementazione di Analytics
seo-description: Adobe offre alcune best practice per aggiornare il codice Analytics.
seo-title: Sostituzione del codice di Analytics
solution: Analytics
subtopic: Risoluzione dei problemi
title: Sostituzione del codice di Analytics
topic: Sviluppatore e implementazione
uuid: d3ea6585-199f-4dbe-9ee8-15b204689f2f
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Sostituzione del codice di Analytics

Adobe offre alcune best practice per aggiornare il codice Analytics.

Spesso, i clienti usano Adobe [!UICONTROL Code Manager] per sostituire il codice con la versione più recente. Questa pratica è buona da seguire purché si tenga in mente determinate cose.

## Utilizzo dell'ID server di raccolta dati errato {#section_1726CEB1ABEC408492569B06664410C8}

Talvolta, [!DNL s_code.js] i file generici che non sono stati generati da Adobe Code Manager vengono inviati a coloro che implementano il codice sul sito. Di conseguenza, viene utilizzato l'ID server di raccolta dati errato (come mostrato nella [!UICONTROL s.dc] variabile) per l'account. È consigliabile generare nuovo codice direttamente dal [!UICONTROL Code Manager] per una suite di rapporti specifica, anziché riutilizzare il codice da una suite di rapporti diversa. Questo è il modo migliore per garantire che la [!UICONTROL s.dc] variabile venga compilata correttamente.

## Plug-ins {#section_53650E52D6A54A4795F95E491E7548D1}

Alcuni clienti implementano i plug-in per migliorare la propria esperienza con Adobe. Quando sostituite il codice, non dimenticate che nel codice sono presenti plug-in. Il codice creato in [!UICONTROL Code Manager] non contiene alcun codice plug-in, pertanto tutti i plug-in devono effettuare la migrazione manuale alla nuova base di codice. Crea una copia del codice esistente nel caso in cui si verifichi un evento, e devi ripristinare il codice precedente.
