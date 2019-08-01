---
description: Procedura che descrive cosa configurare all'interno di Lyris dopo il completamento della procedura guidata.
seo-description: Procedura che descrive cosa configurare all'interno di Lyris dopo il completamento della procedura guidata.
seo-title: Configurazione all'interno di Lyris emaillabs
solution: Analytics
title: Configurazione all'interno di Lyris emaillabs
uuid: 1276176 d-e 5 e 9-451 a -9 a 7 b -9 f 29 a 340 a 25 b
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configuration within the Lyris EmailLabs{#configuration-within-the-lyris-emaillabs}

Procedura che descrive cosa configurare all'interno di Lyris dopo il completamento della procedura guidata.

1. Una volta completata la procedura guidata di integrazione, dovete collaborare con il team Lyris Professional per completare l'integrazione con il vostro account Lyris HQ e facilitare il test.
1. Aggiungi parametri stringa query URL: Verifica che la stringa append URL sia inserita correttamente nelle aree delle impostazioni Organizzazione dell'interfaccia utente. Deve contenere l'ID livello campagna (hq_ m) e l'ID livello destinatario (hq_ v).

   Esempio di ID stringa:

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >If you are applying Lyris’s native analytics tool, *Click Tracks* tags all of the required variables that are added.

