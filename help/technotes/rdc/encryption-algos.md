---
title: Algoritmi di crittografia HTTPS supportati
description: Impostazioni di sicurezza della crittografia TLS e tipi di certificato.
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
source-git-commit: 299de03c05f6a8af4f6c5d98c76bae54eec4c088
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# Algoritmi di crittografia HTTPS supportati

## Livelli di sicurezza dei crittografi

Adobe offre due livelli di protezione crittografata per soddisfare le diverse esigenze dei clienti in materia di sicurezza nella raccolta dati di prime parti. Questi livelli determinano quali algoritmi di cifratura sono supportati per le connessioni HTTPS con i nostri server. Adobe esamina e aggiorna regolarmente il set di algoritmi supportati in base alle procedure di sicurezza correnti. Se desideri modificare le impostazioni di sicurezza della crittografia, contatta l’Assistenza clienti.

&quot;Standard&quot; richiede TLS 1.2 o successivo e almeno la crittografia a 128 bit. È progettato per fornire la massima compatibilità con il dispositivo mantenendo la crittografia sicura.

Il livello di sicurezza cifratura &quot;alto&quot; richiede TLS 1.2 o successivo e rimuove il supporto per i crittografia più deboli. È progettato per i clienti che desiderano la crittografia più potente e non sono interessati al supporto per dispositivi meno recenti.

I seguenti client non sono in grado di connettersi con la protezione crittografata impostata su &quot;Alta&quot;.

* Windows 8.1 e versioni precedenti (ultimo aggiornamento nel 2018)
* Windows Phone 8.1 e versioni precedenti (ultimo aggiornamento nel 2016)
* OS X 10.10 e versioni precedenti (ultimo aggiornamento nel 2017)
* iOS 8.4 e versioni precedenti (ultimo aggiornamento nel 2015)

## Tipi di certificati HTTPS supportati

L’Adobe supporta sia i tipi di certificato RSA che ECC per soddisfare le diverse esigenze dei clienti. I certificati RSA sono più ampiamente supportati per i client, ma i certificati ECC utilizzano meno elaborazione sia sul lato server che su quello client. Ad Adobe, i certificati gestiti vengono forniti sia RSA che ECC. Per i certificati gestiti dai clienti, si consiglia sia RSA che ECC. I client moderni supportano sia RSA che ECC. I seguenti client supportano solo i certificati RSA:

* Windows Vista e versioni precedenti (ultimo aggiornamento nel 2012)
* Windows Phone 8.0 e versioni precedenti (ultimo aggiornamento nel 2014)
* OS X 10.8 e versioni precedenti (ultimo aggiornamento nel 2013)
* iOS 5.1 e versioni precedenti (ultimo aggiornamento nel 2012)
* Android 4.3 e versioni precedenti (ultimo aggiornamento nel 2013)
