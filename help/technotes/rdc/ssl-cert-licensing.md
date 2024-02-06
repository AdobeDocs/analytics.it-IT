---
title: Licenze certificati SSL
description: Procedure per i certificati gestiti dal cliente
feature: Regional Data Collection
exl-id: 7d1373c8-6f7b-4ce7-a555-d3d506e08d17
role: Admin
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# Licenze certificati SSL/TLS

L’Adobe consiglia di gestire il certificato senza costi aggiuntivi tramite [Programma di certificazione gestito Adobe](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it). Il programma Adobe Managed Certificate è completamente automatizzato e garantisce il rinnovo tempestivo dei certificati in modo che non vi sia alcun impatto dovuto ai certificati scaduti.

Se utilizzi, scegli di non utilizzare il [Programma di certificazione gestito Adobe](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it) L’utente è responsabile della fornitura di un certificato SSL/TLS da utilizzare per i cookie di prime parti.

Se fornisci il tuo certificato, è tua responsabilità acquistarlo e mantenerlo.  Il certificato SSL/TLS deve includere una licenza del server illimitata.

Per garantire la sicurezza del certificato, ottieni una richiesta di firma del certificato [CSR] dall’Adobe e si accorda con l’autorità di certificazione desiderata per far firmare il certificato.  Fornisci ad Adobe il certificato firmato per l’implementazione.  Seguendo questo processo, viene mantenuta la sicurezza della chiave del certificato.  L’Assistenza clienti di Adobe sarà di supporto in questa procedura.

Come parte della manutenzione del certificato, almeno un mese prima della scadenza del certificato, rivolgiti all’autorità di certificazione desiderata per ottenere un certificato rinnovato e fornirlo all’Adobe.  Il certificato deve utilizzare lo stesso CSR utilizzato in precedenza.  Contatta l’Adobe se hai bisogno di una copia della CSR o desideri una nuova CSR generata con una nuova chiave.

L&#39;Assistenza clienti è disponibile al seguente indirizzo: customercare@adobe.com oppure al numero 1-800-497-0335.

Le autorità di certificazione comunemente utilizzate includono DigiCert, Comodo e GeoTrust.
