---
title: Risoluzione dei problemi delle sessioni in Adobe  Analytics
description: Scoprite come risolvere i problemi relativi alla disconnessione da Adobe  Analytics.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---


# Risoluzione dei problemi delle sessioni in Adobe  Analytics

Questa pagina contiene informazioni sulle sessioni di risoluzione dei problemi, ovvero potete effettuare l’accesso con successo ma con problemi durante l’accesso. In caso di problemi durante l&#39;accesso ad Adobe  Analytics, consulta [Risoluzione dei problemi di accesso ad Adobe  Analytics](troubleshoot-login.md).

Quasi tutti i problemi relativi alle sessioni derivano dalla rete aziendale personalizzata di un&#39;organizzazione. Se siete in grado di accedere ad Adobe  Analytics ma non riuscite a effettuare l&#39;accesso, utilizzate questo articolo per determinare la causa.

## Determinare se il problema è dovuto alla rete aziendale

Molte organizzazioni implementano funzionalità di rete aggiuntive per migliorare la sicurezza, ad esempio server proxy o firewall. Queste personalizzazioni possono a volte interferire con la possibilità di mantenere una sessione attiva in Adobe  Analytics.

Per determinare se la rete aziendale a cui siete connessi causa problemi con l&#39;utilizzo di Adobe  Analytics, utilizzate le credenziali di accesso  Experience Cloud su un dispositivo esterno alla rete aziendale. Esempi di dispositivi possono essere la rete domestica o il piano dati di un dispositivo mobile. Se siete in grado di passare da una pagina all’altra senza essere disconnessi, è probabile che la rete della vostra organizzazione sia il motivo per cui vi siete disconnessi da Adobe  Analytics.

## Problemi dovuti al proxy

Adobe utilizza un&#39;intestazione di autorizzazione quando effettua richieste ad Adobe. Alcuni proxy, come Bluecoat (ora di proprietà di Symantec), rimuovono le informazioni di intestazione dell&#39;autorizzazione critiche utilizzate da Adobe  Analytics. Se Adobe non visualizza l&#39;intestazione dell&#39;autorizzazione, la sessione scade.

Per risolvere questo problema, Adobe consiglia di collaborare con il team IT dell&#39;organizzazione per consentire l&#39;intestazione dell&#39;autorizzazione tramite il proxy dell&#39;organizzazione.

>[!NOTE]
>
>Sebbene i membri della comunità di Analytics  abbiano trovato utili i seguenti collegamenti, questi non sono di proprietà di Adobe. Tenete presente questa nota quando ne visualizzate il contenuto.

Informazioni sui proxy Symantec e sulle intestazioni di autenticazione sono disponibili qui:

* [Configurare l&#39;autenticazione proxy upstream in una distribuzione a catena di proxy su un accessorio ProxySG o ASG](https://support.symantec.com/en_US/article.TECH246122.html)
* [Consenti a ProxySG di inoltrare sempre l&#39;autorizzazione del server a monte](https://support.symantec.com/en_US/article.TECH244708.html)
