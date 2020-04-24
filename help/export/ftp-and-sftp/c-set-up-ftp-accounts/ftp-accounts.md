---
description: Configurare e utilizzare account FTP ospitati da Adobe.
keywords: ftp;sftp
title: 'Configurare account FTP: panoramica'
uuid: e5524619-248a-4aae-9f64-cd7d33f3c407
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Configurare account FTP: panoramica

Configurare e utilizzare account FTP ospitati da Adobe.

Adobe gestisce cluster FTP a disponibilità elevata e ad alte prestazioni, progettati specificatamente per migliorare l&#39;affidabilità nel trasferimento dei file, assicurando nel contempo prestazioni di alto livello.

I clienti Adobe ricevono notifiche relative agli interventi di manutenzione attraverso una procedura standard, man mano che questi vengono programmati. Per assicurarsi che i sistemi Adobe FTP funzionino correttamente e continuino ad assicurare un trasferimento ad elevate prestazioni, sicuro e affidabile, Adobe richiede il rispetto delle seguenti linee guida:

* La maggior parte degli account Adobe FTP (classificazioni, Origini dati e altri) vengono attivati automaticamente alla configurazione di tale funzionalità. Per account Feed dati e di consegna file generici, l&#39;Assistenza clienti Adobe può configurarti un nuovo account FTP. Questa procedura viene applicata per assicurare la sicurezza e un adeguato spazio disponibile per l&#39;account FTP.
* Gli utenti devono rimuovere i dati inviati da Adobe all&#39;account FTP dopo che questi sono stati correttamente trasferiti sui loro sistemi.
* Informare Adobe nel caso gli account FTP non dovessero più servire, in modo che possano essere disattivati.

The Adobe FTP host name is [!DNL ftp.omniture.com] or [!DNL ftp2.omniture.com].

Queste informazioni, insieme al nome utente e alla password devono essere fornite all&#39;interno di [!UICONTROL Experience Cloud] (per classificazioni e Origini dati) o dal rappresentante Adobe responsabile della configurazione dell&#39;account su tua richiesta. Se non sai che indirizzo FTP utilizzare, contatta il tuo Adobe Account Manager per conoscere l&#39;indirizzo corretto. Inoltre, per account classificazioni e Origini dati, Adobe non ha stabilito una specifica ora del giorno per l&#39;elaborazione dei file FTP, ma utilizza uno script che esegue un costante polling degli account FTP, alla ricerca di nuovi file da elaborare. I file caricati in questi account vengono elaborati il prima possibile.
