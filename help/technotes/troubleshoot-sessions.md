---
title: Risolvere i problemi relativi alle sessioni in Adobe Analytics
description: Scopri come risolvere i problemi relativi alla disconnessione da Adobe Analytics.
feature: Analytics Basics
exl-id: 191250ef-8313-47be-9717-046cce870998
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---

# Risolvere i problemi relativi alle sessioni in Adobe Analytics

Questa pagina contiene informazioni sulla risoluzione dei problemi relativi alle sessioni, ovvero è possibile accedere correttamente ma si sono verificati problemi durante l&#39;accesso. In caso di problemi di accesso ad Adobe Analytics, consulta [Risoluzione dei problemi di accesso ad Adobe Analytics](troubleshoot-login.md).

Quasi tutti i problemi relativi alle sessioni derivano dalla rete aziendale personalizzata di un&#39;organizzazione. Se riesci ad accedere ad Adobe Analytics ma riscontri problemi durante l’accesso, utilizza questo articolo per determinare la causa.

## Determinare se il problema è dovuto alla rete dell’organizzazione {#network}

Molte organizzazioni implementano funzionalità di rete aggiuntive per migliorare la sicurezza, ad esempio server proxy o firewall. A volte queste personalizzazioni possono interferire con la capacità di mantenere una sessione attiva in Adobe Analytics.

Per determinare se la rete aziendale a cui sei connesso causa problemi con l’utilizzo di Adobe Analytics, utilizza le credenziali di accesso di Experience Cloud su un dispositivo esterno alla rete aziendale. Esempi di dispositivi possono essere tramite la rete domestica o il piano dati di un dispositivo mobile. Se riesci a passare da una pagina all’altra senza aver eseguito la disconnessione, è probabile che la rete della tua organizzazione sia il motivo per cui ti sei disconnesso da Adobe Analytics.

## Problemi dovuti al proxy {#proxy}

Adobe utilizza un’intestazione di autorizzazione quando effettua richieste ad Adobe. Alcuni proxy, come Edge Secure Web Gateway (precedentemente Bluecoat), eliminano le informazioni critiche sull’intestazione di autorizzazione utilizzate da Adobe Analytics. Se l’Adobe non visualizza l’intestazione di autorizzazione, la sessione scade.

Per risolvere questo problema, l’Adobe consiglia di collaborare con il team IT della tua organizzazione per consentire l’intestazione di autorizzazione tramite il proxy dell’organizzazione.

>[!NOTE]
>
>Anche se i membri della community di Analytics hanno trovato utili i seguenti collegamenti, non sono di proprietà di Adobe. Prendi in considerazione questa nota durante la visualizzazione del loro contenuto.

Le informazioni sui proxy e sulle intestazioni di autenticazione sono disponibili qui:

* [Configurare l&#39;autenticazione proxy a monte in una distribuzione a catena proxy su un accessorio ProxySG o ASG](https://techdocs.broadcom.com/us/en/symantec-security-software/web-and-network-security/edge-swg/7-3/authentication_co.html)
* [Inoltrare le credenziali utente a un server dietro l&#39;accessorio ProxySG](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)
