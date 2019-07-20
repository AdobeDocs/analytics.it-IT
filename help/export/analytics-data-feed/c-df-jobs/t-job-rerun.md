---
description: Potete eseguire nuovamente uno o più processi nell'elenco Processi.
keywords: Feed dati; processo; rerun
seo-description: Potete eseguire nuovamente uno o più processi nell'elenco Processi.
seo-title: Ripristino di un processo
solution: Analytics
title: Ripristino di un processo
uuid: 5 caf 95 da-dd 88-4 b 1 a-a 081-684 f 4 fd 1 f 714
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Ripristino di un processo

Potete eseguire nuovamente uno o più processi nell'elenco Processi.

1. Selezionate uno o più processi da ripetere.
1. Fai clic su **[!UICONTROL Rerun Job]**.

   Il processo di ripristino dipende dallo stato corrente del processo:

   | Stato | Nome file memorizzato nella cache sul server | Processo |
   |---|---|---|
   | Completato | Sì | Il file viene inviato nuovamente. |
   | Completato | No | Il processo viene rielaborato e quindi inviato nuovamente. |
   | Non riuscito | No | Il processo viene rielaborato e quindi inviato nuovamente. |
   | Altro stato | N/D | Non supportato. |

