---
description: La modalità offline restituisce dati segnaposto per velocizzare il processo di creazione e di modifica delle richieste.
seo-description: La modalità offline restituisce dati segnaposto per velocizzare il processo di creazione e di modifica delle richieste.
seo-title: Modalità offline per la creazione e la modifica delle richieste
solution: Analytics
title: Modalità offline per la creazione e la modifica delle richieste
topic: Generatore di report
uuid: 4 eb 1 f 754-b 6 da -4896-a 64 f-b 737563925 b 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Modalità offline per la creazione e la modifica delle richieste

La modalità offline restituisce dati segnaposto per velocizzare il processo di creazione e di modifica delle richieste.

Quando create o modificate una nuova richiesta, vengono chiamate chiamate API Report per recuperare la risposta. Questo rallenta il processo di creazione della richiesta, perché è necessario attendere che i dati restituiscano prima di passare al passaggio successivo. La modalità offline restituisce solo dati segnaposto, pertanto non è necessario effettuare chiamate API.

Per abilitare la modalità offline:

1. Click **[!UICONTROL Options]** in the Report Builder menu.

   ![](assets/offline_mode.png)

1. Check the checkbox next to **[!UICONTROL Turn on offline mode for creating and editing requests]**.
1. In the **[!UICONTROL Display Metric Data as]** field, enter the placeholder data that you want returned in your request. Ad esempio, immettete "1".
1. Fai clic su **[!UICONTROL OK]**.
1. Ora create ed eseguite la richiesta (in modalità offline) tramite la richiesta guidata.
1. La richiesta con "1" come dati segnaposto sarà simile a quella riportata di seguito:

   ![](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Prima di eseguire le richieste con dati reali, disattivate la modalità offline. To do so, just go back to **[!UICONTROL Options]** and remove the checkmark.

