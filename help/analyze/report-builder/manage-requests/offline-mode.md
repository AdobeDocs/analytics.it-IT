---
description: La modalità offline restituisce i dati segnaposto per accelerare il processo di creazione e modifica delle richieste.
solution: Analytics
title: Modalità offline per la creazione e la modifica delle richieste
topic: Report builder
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Modalità offline per la creazione e la modifica delle richieste

La modalità offline restituisce i dati segnaposto per accelerare il processo di creazione e modifica delle richieste.

Quando create o modificate una nuova richiesta, vengono effettuate chiamate API report per recuperare la risposta. Ciò rallenta il processo di creazione della richiesta, perché è necessario attendere la restituzione dei dati prima di passare al passaggio successivo. La modalità offline restituisce solo i dati segnaposto, pertanto non è necessario effettuare chiamate API.

Per attivare la modalità offline:

1. Fate clic **[!UICONTROL Options]** nel menu Generatore di report.

   ![](assets/offline_mode.png)

1. Selezionare la casella di controllo accanto a **[!UICONTROL Turn on offline mode for creating and editing requests]**.
1. Nel **[!UICONTROL Display Metric Data as]** campo, inserite i dati segnaposto che desiderate vengano restituiti nella richiesta. Ad esempio, immettete "1".
1. Fai clic su **[!UICONTROL OK]**.
1. Create ed eseguite la richiesta (in modalità offline) tramite la Richiesta guidata.
1. La tua richiesta con "1" come dati segnaposto sarà simile a quella riportata di seguito:

   ![](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Prima di eseguire le richieste con dati reali, disattivate la modalità offline. Per farlo, basta tornare indietro **[!UICONTROL Options]** e rimuovere il segno di spunta.

