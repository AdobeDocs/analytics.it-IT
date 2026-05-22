---
description: Il confronto tra FTP attivo e FTP passivo controlla come vengono stabilite le connessioni delle porte e la scelta ha alcune implicazioni firewall.
keywords: ftp;sftp
title: Utilizzo della modalità FTP passiva
feature: FTP Export
exl-id: 92f39569-ee41-4c1d-b7de-7a0fff42896c
TQID: 'https://experienceleague.adobe.com/r59xjXQj3CYM1r-e1dpNMkLMoW72Io9-PtL-vaRCDNM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 100
ht-degree: 10%

---

# Utilizzo della modalità FTP passiva

Il confronto tra FTP attivo e FTP passivo controlla come vengono stabilite le connessioni delle porte e la scelta ha alcune implicazioni firewall.

Adobe utilizza l’FTP passivo, una forma di trasferimento dei dati più sicura, in cui il flusso di dati viene configurato e avviato dal client FTP (File Transfer Program) anziché dal programma server FTP. In caso di difficoltà nella connessione a Adobe FTP, accertati di utilizzare la modalità passiva.
