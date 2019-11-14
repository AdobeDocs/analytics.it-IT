---
description: Potete eseguire nuovamente uno o più processi dall’elenco Processi.
keywords: Data Feed;job;rerun
solution: Analytics
title: Ripristino di un processo
uuid: 5caf95da-dd88-4b1a-a081-684f4fd1f714
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Ripristino di un processo

Potete eseguire nuovamente uno o più processi dall’elenco Processi.

1. Selezionate uno o più processi da ripetere.
1. Fai clic su **[!UICONTROL Rerun Job]**.

   Il processo di ripetizione dipende dallo stato corrente del processo:

   | Stato | Nome file memorizzato nella cache del server | Processo |
   |---|---|---|
   | Completato | Sì | File inviato di nuovo. |
   | Completato | No | Il processo viene rielaborato e inviato di nuovo. |
   | Non riuscito | No | Il processo viene rielaborato e inviato di nuovo. |
   | Altro stato | N/D | Non supportato. |

