---
title: Risoluzione dei problemi delle sessioni in Adobe Analytics
description: Scopri come risolvere i problemi relativi alla disconnessione da Adobe Analytics.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Risoluzione dei problemi delle sessioni in Adobe Analytics

Questa pagina contiene informazioni sulle sessioni di risoluzione dei problemi, ovvero potete effettuare l’accesso con successo ma con problemi durante l’accesso. If you are having issues logging in to Adobe Analytics, see [Troubleshoot logging in to Adobe Analytics](troubleshoot-login.md).

Quasi tutti i problemi relativi alle sessioni derivano dalla rete aziendale personalizzata di un&#39;organizzazione. Se siete in grado di accedere ad Adobe Analytics ma non riuscite a effettuare l&#39;accesso, utilizzate questo articolo per determinare la causa.

## Determinare se il problema è dovuto alla rete aziendale

Molte organizzazioni implementano funzionalità di rete aggiuntive per migliorare la sicurezza, ad esempio server proxy o firewall. A volte queste personalizzazioni possono interferire con la possibilità di mantenere una sessione attiva in Adobe Analytics.

Per determinare se la rete aziendale a cui siete connessi causa problemi con l&#39;utilizzo di Adobe Analytics, utilizzate le credenziali di accesso di Experience Cloud su un dispositivo esterno alla rete aziendale. Examples of devices can be through your home network or a mobile device&#39;s data plan. Se sei in grado di passare da una pagina all&#39;altra senza essere disconnesso, è probabile che la rete della tua organizzazione sia il motivo per cui ti disconnetti da Adobe Analytics.

## Problemi dovuti al proxy

Adobe utilizza un&#39;intestazione di autorizzazione quando effettua richieste ad Adobe. Some proxies, such as Bluecoat (now owned by Symantec), strip critical authorization header information used by Adobe Analytics. Se Adobe non visualizza l&#39;intestazione dell&#39;autorizzazione, la sessione scade.

Per risolvere questo problema, Adobe consiglia di collaborare con il team IT dell&#39;organizzazione per consentire l&#39;intestazione dell&#39;autorizzazione tramite il proxy dell&#39;organizzazione.

>[!NOTE] Sebbene i membri della comunità Analytics abbiano trovato utili i seguenti collegamenti, non sono di proprietà di Adobe. Tenete presente questa nota quando ne visualizzate il contenuto.

Informazioni sui proxy Symantec e sulle intestazioni di autenticazione sono disponibili qui:

* [Configurare l&#39;autenticazione proxy upstream in una distribuzione a catena di proxy su un accessorio ProxySG o ASG](https://support.symantec.com/en_US/article.TECH246122.html)
* [Consenti a ProxySG di inoltrare sempre l&#39;autorizzazione del server a monte](https://support.symantec.com/en_US/article.TECH244708.html)
