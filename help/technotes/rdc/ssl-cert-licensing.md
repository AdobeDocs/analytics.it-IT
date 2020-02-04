---
title: Licenze certificato SSL
description: Procedure dei certificati per i certificati gestiti dal cliente
translation-type: tm+mt
source-git-commit: 290838566b86f71902abd303b5c43dd2661d3ce1

---


# Licenze certificato SSL/TLS

Adobe consiglia di gestire il certificato senza costi aggiuntivi tramite il programma [di certificazione gestito di](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html)Adobe.  Il programma di certificazione gestito di Adobe è completamente automatizzato e garantisce che i certificati vengano rinnovati in modo tempestivo, in modo che non vi sia alcun impatto a causa dei certificati scaduti.

Se utilizzate l&#39;opzione di non utilizzare il programma [di certificazione gestito di](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) Adobe, dovete fornire un certificato SSL/TLS da utilizzare per i cookie di prime parti.

Se fornisci il tuo certificato, è tua responsabilità acquistarlo e gestirlo.  Il certificato SSL/TLS deve includere una licenza server illimitata.

Per garantire la sicurezza dei certificati, ottenere un [CSR] di richiesta di firma dei certificati da Adobe e organizzare con l&#39;autorità di certificazione richiesta la firma del certificato.  Fornire ad Adobe il certificato firmato per l&#39;implementazione.  Seguendo questa procedura, viene mantenuta la protezione della chiave del certificato.  L&#39;Assistenza clienti Adobe fornirà assistenza in questo processo.

Nel quadro della manutenzione dei certificati, almeno un mese prima della scadenza del certificato, organizzare con l&#39;autorità di certificazione desiderata per ottenere un certificato rinnovato e fornirlo ad Adobe.  Questo certificato dovrebbe utilizzare lo stesso CSR utilizzato in precedenza.  Contattate Adobe se avete bisogno di una copia del CSR o volete generare un nuovo CSR con una nuova chiave.

L&#39;Assistenza clienti è disponibile all&#39;indirizzo customercare@adobe.com o 1-800-497-0335.

Le autorità di certificazione utilizzate comunemente includono DigiCert, Comodo e GeoTrust.
