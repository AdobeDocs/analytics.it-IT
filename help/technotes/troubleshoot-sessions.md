---
title: Risoluzione dei problemi delle sessioni in Adobe Analytics
description: Scopri come risolvere i problemi relativi all'uscita da Adobe Analytics.
seo-title: Risoluzione dei problemi delle sessioni in Adobe Analytics
seo-description: Scopri come risolvere i problemi relativi all'uscita da Adobe Analytics.
translation-type: tm+mt
source-git-commit: b5e3801454dafbcc47b93e65f8b5e7c59c3a8081

---


# Risoluzione dei problemi delle sessioni in Adobe Analytics

Questa pagina descrive le sessioni di risoluzione dei problemi, per cui è possibile effettuare l'accesso ma con problemi di accesso. If you are having issues logging in to Adobe Analytics, see [Troubleshoot logging in to Adobe Analytics](troubleshoot-login.md).

Quasi tutti i problemi basati su sessioni sono originati dalla rete aziendale personalizzata di un'organizzazione. Se siete in grado di accedere ad Adobe Analytics ma riscontrate dei problemi durante l'accesso, utilizzate questo articolo per determinare la causa.

## Determinare se il problema è dovuto alla rete dell'organizzazione

Molte organizzazioni implementano funzioni di rete aggiuntive per migliorare la sicurezza, ad esempio server proxy o firewall. Queste personalizzazioni possono interferire con la capacità di mantenere una sessione attiva in Adobe Analytics.

Per determinare se la rete aziendale a cui siete connessi causa problemi con l'utilizzo di Adobe Analytics, utilizzate le credenziali di accesso di Experience Cloud su un dispositivo esterno alla rete aziendale. Alcuni esempi di dispositivi possono essere attraverso la rete principale o il piano dati di un dispositivo mobile. Se si è in grado di spostarsi da una pagina all'altra senza disconnettersi, la rete dell'organizzazione è probabilmente il motivo per cui si disconnette Adobe Analytics.

## Problemi causati da pool IP

Alcune reti utilizzano una procedura denominata pooling IP, in cui l'indirizzo IP di un dispositivo può spesso cambiare in un intervallo utilizzato dall'organizzazione. Come parte delle pratiche di sicurezza di Adobe, se un indirizzo IP cambia di metà sessione, tale sessione viene scaduta.

Se l'organizzazione utilizza il pool IP, usa le seguenti istruzioni per aggiungere alla whitelist di Adobe gli intervalli IP:

1. Consultate il team IT della vostra organizzazione per ottenere un elenco degli intervalli IP utilizzati nell'organizzazione
2. Chiedete a un delegato di assistenza clienti di contattare l'Assistenza clienti Adobe e fornire ad Adobe gli intervalli IP
3. L'agente immette gli intervalli IP in una whitelist per evitare la scadenza delle sessioni se entrambi gli indirizzi sono all'interno degli intervalli forniti

## Problemi causati da proxy

Adobe utilizza un'intestazione di autorizzazione durante la creazione di richieste ad Adobe. Alcuni proxy, come ad esempio Bluecoat (di proprietà di Symantec), sono in grado di rimuovere le informazioni relative all'intestazione di autorizzazione critica utilizzate da Adobe Analytics. Quando Adobe non visualizza l'intestazione di autorizzazione, la sessione è scaduta.

Per risolvere questo problema, Adobe consiglia di collaborare con il team IT della tua organizzazione per consentire l'intestazione dell'autorizzazione attraverso il proxy aziendale.

> [!NOTE] Nota
>
> I membri della community Analytics hanno scoperto i seguenti collegamenti utili, non sono di proprietà di Adobe. Prendere in considerazione questa nota durante la visualizzazione del contenuto.

Sono disponibili informazioni su proxy Symantec e intestazioni di autenticazione:

* [Configurare l'autenticazione proxy a monte in una catena di riepilogo proxy su un dispositivo proxysg o ASG](https://support.symantec.com/en_US/article.TECH246122.html)
* [Consenti sempre a proxysg di inoltrare l'autorizzazione del server a monte](https://support.symantec.com/en_US/article.TECH244708.html)
