---
description: Il criterio FTP di Adobe disabilita automaticamente l’accesso agli account FTP che rimangono inattivi per 90 giorni consecutivi.
keywords: ftp;sftp
title: Eliminare account e dati FTP e SFTP
feature: FTP Export
exl-id: accf2f8d-c22c-4684-ba85-73a286325d0c
TQID: 'https://experienceleague.adobe.com/i2jpzTOx-CJzWjHMXT14EE761uGvNjcoW3f1dyF0ZlA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 237
ht-degree: 0%

---

# Eliminare account e dati FTP e SFTP

I criteri FTP e SFTP di Adobe possono disabilitare l’accesso agli account FTP e SFTP che rimangono inattivi per 90 giorni consecutivi.

Adobe può quindi rimuovere gli account FTP e SFTP disabilitati (e rimuovere definitivamente tutti i dati memorizzati in tali account) dopo un ulteriore periodo di tolleranza di 90 giorni. Ad esempio, un account SFTP che rimane inattivo per 90 giorni (dal 5 luglio 2025 al 2 ottobre 2025) è disabilitato il 3 ottobre 2025. Viene quindi completamente rimosso il 2 gennaio 2026.

Nessun account è disabilitato prima del 5 ottobre 2025 e nessun account viene rimosso prima del 2 gennaio 2026.

Adobe può anche rimuovere definitivamente i dati obsoleti negli account attivi se tali dati non sono stati accessibili per 90 giorni.

Per aiutarci in questo processo e per garantire che l’ambiente FTP o SFTP continui a fornire ai nostri clienti un trasferimento dati sicuro e affidabile, chiediamo ai nostri clienti di effettuare le seguenti operazioni:

* Rimuovi i dati in uscita dai sistemi FTP e SFTP dopo che sono stati trasferiti correttamente all’ambiente interno. Adobe può identificare e rimuovere tutti i file rimasti nel sistema dopo 90 giorni.
* Avvisa Adobe quando gli account FTP e SFTP non sono più necessari, in modo che possano essere disattivati e rimossi.
