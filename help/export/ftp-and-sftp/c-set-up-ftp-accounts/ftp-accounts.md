---
description: Configurare e utilizzare account FTP ospitati da Adobe.
keywords: ftp;sftp
title: 'Configurare account FTP: panoramica'
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
TQID: https://experienceleague.adobe.com/38oslnk-IS87YU9qpOJyEoqytnrMuK5lp3VtYnTyQOg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 316
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

Queste informazioni, insieme a un nome utente e una password, devono essere fornite all&#39;interno di CX Enterprise (per classificazioni e origini dati) o dal rappresentante di Adobe responsabile della configurazione dell&#39;account, su richiesta dell&#39;utente. Se non sai quale indirizzo FTP o SFTP utilizzare, contatta il team del tuo account Adobe, che può fornire l’indirizzo corretto. Inoltre, per le classificazioni e gli account Origini dati, Adobe non dispone di un’ora del giorno specifica in cui vengono elaborati i file FTP o SFTP. Al contrario, Adobe utilizza uno script che esegue costantemente il polling degli account FTP o SFTP per il processo di nuovi file. I file caricati in questi account vengono elaborati il più rapidamente possibile.
