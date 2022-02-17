---
title: Licenze di certificati SSL
description: Procedure dei certificati per i certificati gestiti dal cliente
feature: Regional Data Collection
exl-id: 7d1373c8-6f7b-4ce7-a555-d3d506e08d17
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 5%

---

# Licenze di certificati SSL/TLS

L’Adobe consiglia di gestire il certificato senza costi aggiuntivi tramite [Programma di certificazione gestito di Adobe](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it). Il programma di certificazione gestito di Adobe è completamente automatizzato e garantisce il rinnovo dei certificati in modo tempestivo, in modo che non vi sia alcun impatto a causa dei certificati scaduti.

Se utilizzi , scegli di non utilizzare il [Programma di certificazione gestito di Adobe](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html) devi fornire un certificato SSL/TLS da utilizzare per i cookie di prime parti.

Se fornisci il tuo certificato, è tua responsabilità acquistarlo e gestirlo.  Il certificato SSL/TLS deve includere una licenza server illimitata.

Per garantire la sicurezza del certificato, ottieni una richiesta di firma del certificato [CSR] dall’Adobe e organizza con l’autorità di certificazione desiderata la firma del certificato.  Fornisci un Adobe del certificato firmato per l’implementazione.  Seguendo questa procedura, viene mantenuta la sicurezza della chiave del certificato.  L’Assistenza clienti di Adobe assisterà in questo processo.

Per la manutenzione del certificato, almeno un mese prima della scadenza del certificato, rivolgiti all’autorità di certificazione desiderata per ottenere un nuovo certificato e fornirlo ad Adobe.  Questo certificato deve utilizzare la stessa CSR utilizzata in precedenza.  Contatta l’Adobe se hai bisogno di una copia della CSR o se desideri generare una nuova CSR con una nuova chiave.

L’Assistenza clienti può essere raggiunta all’indirizzo customercare@adobe.com o 1-800-497-0335.

Le autorità di certificazione comunemente utilizzate includono DigiCert, Comodo e GeoTrust.
