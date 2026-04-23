---
description: Configurare e utilizzare account FTP ospitati da Adobe.
keywords: ftp;sftp
title: 'Configurare account FTP: panoramica'
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
source-git-commit: 6008cd51b86e403668c15bbfb9d50513e46ddf4d
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 2%

---

# Configurare account FTP o SFTP: panoramica

Configurare e utilizzare account FTP o SFTP ospitati da Adobe.

Adobe mantiene cluster FTP o SFTP ad alta disponibilità e prestazioni che sono progettati specificamente per migliorare l’affidabilità del trasferimento dei file, continuando al contempo a garantire prestazioni elevate.

I clienti di Adobe ricevono notifiche di manutenzione tramite la procedura standard, man mano che vengono pianificati gli eventi di manutenzione. Per garantire che i sistemi Adobe FTP o SFTP funzionino come progettati e continuino a fornire un trasferimento dati sicuro e affidabile ad alte prestazioni, Adobe richiede di attenersi alle seguenti linee guida:

* La maggior parte degli account FTP o SFTP di Adobe (classificazioni, origini dati e altri) vengono abilitati automaticamente quando la funzione specificata viene impostata. Per gli account Feed dati e di consegna file generici, l’Assistenza clienti di Adobe può impostare un nuovo account FTP o SFTP per te. Questo processo garantisce sia la sicurezza che lo spazio disponibile per l’account FTP o SFTP.
* Gli utenti devono rimuovere i dati consegnati da Adobe all’account FTP o SFTP dopo che il trasferimento dei dati ai propri sistemi è stato completato correttamente.
* Notifica ad Adobe quando gli account FTP o SFTP non sono più necessari per consentirne la disattivazione.

Il nome host FTP di Adobe è `ftp://ftp.omniture.com` o `ftp://ftp2.omniture.com`.

Queste informazioni, insieme a un nome utente e una password, devono essere fornite all&#39;interno di [!UICONTROL Experience Cloud] (per classificazioni e origini dati) o dal rappresentante di Adobe responsabile della configurazione dell&#39;account su richiesta dell&#39;utente. Se non sai quale indirizzo FTP o SFTP utilizzare, contatta il team del tuo account Adobe, che può fornire l’indirizzo corretto. Inoltre, per le classificazioni e gli account Origini dati, Adobe non dispone di un’ora del giorno specifica in cui vengono elaborati i file FTP o SFTP. Al contrario, Adobe utilizza uno script che esegue costantemente il polling degli account FTP o SFTP per il processo di nuovi file. I file caricati in questi account vengono elaborati il più rapidamente possibile.
