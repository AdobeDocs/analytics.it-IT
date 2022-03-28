---
title: Algoritmi di crittografia HTTPS supportati
description: Il 23 giugno 2022 verrà rimosso il supporto per i crittografia TLS 1.2 che utilizzano SHA1 o CBC per i clienti con un livello di sicurezza più elevato.
feature: Regional Data Collection
source-git-commit: ce607610516a94e4d0fbbc53a1f8f53f5977a777
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Algoritmi di crittografia HTTPS supportati

Adobe offre due livelli di sicurezza cifratura per soddisfare le diverse esigenze dei clienti in materia di sicurezza nella raccolta dati di prime parti. Questi livelli determinano quali algoritmi di cifratura sono supportati per le connessioni HTTPS con i nostri server. Per impostazione predefinita, i clienti utilizzano &quot;Standard&quot;, che supporta solo algoritmi di cifratura moderni. &quot;High&quot; supporta un elenco più piccolo di algoritmi di crittografia per i clienti più preoccupati di queste connessioni. Per entrambi i livelli di sicurezza, Adobe aggiorna regolarmente il set di algoritmi supportati in base alle procedure di sicurezza correnti. Se desideri modificare le impostazioni di sicurezza della crittografia, contatta l’Assistenza clienti.

Il 23 giugno 2022 verrà rimosso il supporto per i crittografia TLS 1.2 che utilizzano SHA1 o CBC per i clienti con un livello di sicurezza più elevato.  Questa modifica avrà un impatto sulla raccolta dati sicura per gli utenti finali che utilizzano sistemi operativi meno recenti.

I seguenti crittografia TLS 1.2 non saranno più supportati:

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA

I seguenti client sono notoriamente interessati da questa modifica perché non supportano gli standard di crittografia correnti:

* Windows 8.1 e versioni precedenti (ultimo aggiornamento nel 2018)
* Windows Phone 8.1 e versioni precedenti (ultimo aggiornamento nel 2016)
* OS X 10.10 e versioni precedenti (ultimo aggiornamento nel 2017)
* iOS 8.4 e versioni precedenti (ultimo aggiornamento nel 2015)

I dispositivi Android non sono interessati da questa modifica.

I clienti con livello di sicurezza crittografato impostato su &quot;Standard&quot; non sono interessati da questa modifica.

