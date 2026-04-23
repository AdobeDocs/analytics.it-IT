---
description: Il criterio FTP di Adobe disabilita automaticamente l’accesso agli account FTP che rimangono inattivi per 90 giorni consecutivi.
keywords: ftp;sftp
title: Eliminare account e dati FTP e SFTP
feature: FTP Export
exl-id: accf2f8d-c22c-4684-ba85-73a286325d0c
source-git-commit: 6008cd51b86e403668c15bbfb9d50513e46ddf4d
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Eliminare account e dati FTP e SFTP

I criteri FTP e SFTP di Adobe possono disabilitare l’accesso agli account FTP e SFTP che rimangono inattivi per 90 giorni consecutivi.

Adobe può quindi rimuovere gli account FTP e SFTP disabilitati (e rimuovere definitivamente tutti i dati memorizzati in tali account) dopo un ulteriore periodo di tolleranza di 90 giorni. Ad esempio, un account SFTP che rimane inattivo per 90 giorni (dal 5 luglio 2025 al 2 ottobre 2025) è disabilitato il 3 ottobre 2025. Viene quindi completamente rimosso il 2 gennaio 2026.

Nessun account è disabilitato prima del 5 ottobre 2025 e nessun account viene rimosso prima del 2 gennaio 2026.

Adobe può anche rimuovere definitivamente i dati obsoleti negli account attivi se tali dati non sono stati accessibili per 90 giorni.

Per aiutarci in questo processo e per garantire che l’ambiente FTP o SFTP continui a fornire ai nostri clienti un trasferimento dati sicuro e affidabile, chiediamo ai nostri clienti di effettuare le seguenti operazioni:

* Rimuovi i dati in uscita dai sistemi FTP e SFTP dopo che sono stati trasferiti correttamente all’ambiente interno. Adobe può identificare e rimuovere tutti i file rimasti nel sistema dopo 90 giorni.
* Avvisa Adobe quando gli account FTP e SFTP non sono più necessari, in modo che possano essere disattivati e rimossi.
