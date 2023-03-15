---
title: Algoritmi di crittografia HTTPS supportati
description: Il 23 giugno 2022 verrà rimosso il supporto per le crittografie TLS 1.2 che utilizzano SHA1 o CBC per i clienti con livello di sicurezza crittografato impostato su "Elevato".
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
source-git-commit: 84a8dc9c6052d34e9dea370e444c83e84bf17852
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 5%

---

# Algoritmi di crittografia HTTPS supportati

Adobe offre due livelli di protezione crittografata per soddisfare le diverse esigenze dei clienti in materia di sicurezza nella raccolta dati di prime parti. Questi livelli determinano quali algoritmi di crittografia sono supportati per le connessioni HTTPS con i nostri server. Per impostazione predefinita, i clienti utilizzano ‘Standard’, che supporta solo algoritmi di crittografia moderni. ‘Elevato’ supporta un elenco più ristretto di algoritmi di crittografia per i clienti che sono più preoccupati per queste connessioni. Per entrambi i livelli di sicurezza, Adobe aggiorna regolarmente il set di algoritmi supportati in base alle procedure di sicurezza correnti. Se desideri modificare le impostazioni di protezione crittografata, contatta l’Assistenza clienti.

Il 23 giugno 2022 verrà rimosso il supporto per le crittografie TLS 1.2 che utilizzano SHA1 o CBC per i clienti con livello di sicurezza crittografato impostato su &quot;Elevato&quot;.  Questa modifica influirà sulla raccolta sicura dei dati per gli utenti finali sui sistemi operativi meno recenti.

Le seguenti crittografie TLS 1.2 non saranno più supportate:

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_GCM_SHA256
* TLS_RSA_WITH_AES_256_GCM_SHA384

I seguenti client sono notoriamente interessati da questa modifica perché non supportano gli standard di crittografia correnti:

* Windows 8.1 e versioni precedenti (ultimo aggiornamento: 2018)
* Windows Phone 8.1 e versioni precedenti (ultimo aggiornamento: 2016)
* OS X 10.10 e versioni precedenti (ultimo aggiornamento: 2017)
* iOS 8.4 e versioni precedenti (ultimo aggiornamento: 2015)

I dispositivi Android non sono interessati da questa modifica.

I clienti con il livello di sicurezza crittografato impostato su &quot;Standard&quot; non sono interessati da questa modifica.
