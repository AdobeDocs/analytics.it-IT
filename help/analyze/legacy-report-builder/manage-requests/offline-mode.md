---
description: Scopri come utilizzare la modalità offline per restituire i dati dei segnaposto.
title: Abilitare la modalità offline
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
TQID: https://experienceleague.adobe.com/HKk--fSRTABpRb8Q9yOeySHyAVSR-W2Ktzldmp7UeJQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 185
ht-degree: 28%

---

# Modalità offline per la creazione e la modifica delle richieste

{{legacy-arb}}

La modalità offline restituisce i dati dei segnaposto per accelerare il processo di creazione e modifica delle richieste.

Quando crei o modifichi una nuova richiesta, vengono effettuate chiamate API per i rapporti per recuperare la risposta. A volte queste chiamate rallentano il processo di creazione della richiesta perché devi aspettare la restituzione dei dati prima di passare al passaggio successivo. La modalità offline restituisce solo i dati segnaposto e non vengono create API.

Per attivare la modalità offline

1. Fai clic su **[!UICONTROL Options]** nel menu Report Builder.

   ![Schermata della schermata Opzioni con modalità offline selezionata.](assets/offline_mode.png)

1. Spunta la casella di controllo accanto a **[!UICONTROL Turn on offline mode for creating and editing requests]**.
1. Nel campo **[!UICONTROL Display Metric Data as]** immettere i dati segnaposto da restituire nella richiesta. Ad esempio, immettere “1”.
1. Fai clic su **[!UICONTROL OK]**.
1. Creare ed eseguire la richiesta in modalità offline utilizzando la Creazione guidata richieste. La schermata seguente mostra un esempio di richiesta con &quot;1&quot; come dati segnaposto.

   ![Schermata che mostra l&#39;esempio della modalità offline utilizzando 1 come segnaposto.](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Assicurati di disabilitare la modalità offline prima di eseguire le richieste con dati reali.
