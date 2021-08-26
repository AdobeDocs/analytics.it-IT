---
title: Risolvere i problemi relativi alle sessioni in Adobe Analytics
description: Scopri come risolvere i problemi relativi all’uscita da Adobe Analytics.
exl-id: 191250ef-8313-47be-9717-046cce870998
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Risolvere i problemi relativi alle sessioni in Adobe Analytics

Questa pagina riguarda la risoluzione dei problemi delle sessioni, il che significa che si è in grado di accedere con successo ma che hanno problemi ad accedere. In caso di problemi durante l&#39;accesso ad Adobe Analytics, consulta [Risoluzione dei problemi di accesso ad Adobe Analytics](troubleshoot-login.md).

Quasi tutti i problemi basati su sessioni provengono dalla rete aziendale personalizzata di un&#39;organizzazione. Se riesci ad accedere ad Adobe Analytics ma hai problemi ad accedere, utilizza questo articolo per determinare la causa.

## Determina se il problema è dovuto alla rete della tua organizzazione

Molte organizzazioni utilizzano funzionalità di rete aggiuntive per migliorare la sicurezza, ad esempio server proxy o firewall. Queste personalizzazioni possono a volte interferire con la possibilità di mantenere una sessione attiva in Adobe Analytics.

Per determinare se la rete aziendale a cui sei connesso causa problemi con l’utilizzo di Adobe Analytics, utilizza le credenziali di accesso di Experience Cloud su un dispositivo esterno alla rete aziendale. Esempi di dispositivi possono essere attraverso la rete domestica o il piano dati di un dispositivo mobile. Se riesci a passare da pagina a pagina senza essere disconnesso, è probabile che la rete della tua organizzazione sia la ragione per cui ti sei disconnesso da Adobe Analytics.

## Problemi dovuti al proxy

Adobe utilizza un&#39;intestazione di autorizzazione quando effettua richieste ad Adobe. Alcuni proxy, come Edge Secure Web Gateway (precedentemente Bluecoat), rimuovono le informazioni di intestazione di autorizzazione critiche utilizzate da Adobe Analytics. Quando Adobe non visualizza l’intestazione dell’autorizzazione, la sessione scade.

Per risolvere questo problema, Adobe consiglia di lavorare con il team IT della tua organizzazione per consentire l’intestazione dell’autorizzazione tramite il proxy della tua organizzazione.

>[!NOTE]
>
>Anche se i membri della community di Analytics hanno trovato utili i seguenti collegamenti, non sono di proprietà di Adobe. Prendi in considerazione questa nota quando visualizzi il loro contenuto.

Le informazioni sui proxy e le intestazioni di autenticazione sono disponibili qui:

* [Configurare l&#39;autenticazione proxy a monte in una distribuzione a catena di proxy su un accessorio ProxySG o ASG](https://knowledge.broadcom.com/external/article/169255/configure-upstream-proxy-authentication.html)
* [Come inoltrare le credenziali utente a un server dietro l&#39;accessorio ProxySG](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)
