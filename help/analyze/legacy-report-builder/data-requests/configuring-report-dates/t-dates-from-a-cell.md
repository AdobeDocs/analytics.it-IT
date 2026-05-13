---
description: È possibile specificare un intervallo di date selezionando le celle da un foglio di lavoro che contiene una richiesta. Report Builder utilizza le informazioni specifiche sull’intervallo di date in tali richieste. Se selezioni la data odierna, verranno visualizzati dati parziali in base all’ora del giorno in cui viene eseguita la richiesta.
title: Date da una cella
uuid: 0d9bf08d-d39d-4f37-94f1-232da0813245
feature: Report Builder
role: User, Admin
exl-id: e10573cc-984e-4202-a797-c2c9bec2af96
TQID: https://experienceleague.adobe.com/9-U5bdrNbEahhtBuJA4ylaXzGEgH01q1z7FBR2w5sPs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 4%

---

# Date da una cella

{{legacy-arb}}

È possibile specificare un intervallo di date selezionando le celle da un foglio di lavoro che contiene una richiesta. Report Builder utilizza le informazioni specifiche sull’intervallo di date in tali richieste. Se selezioni la data odierna, verranno visualizzati dati parziali in base all’ora del giorno in cui viene eseguita la richiesta.

**Per configurare le date da una cella**

1. In [!UICONTROL Request Wizard: Step 1], selezionare **[!UICONTROL Dates From Cell]**.
1. Immettere i riferimenti di cella nei campi **[!UICONTROL From]** e **[!UICONTROL To]** oppure fare clic sul selettore e selezionare le celle contenenti le richieste con le date di inizio e di fine.

   Ad esempio, crea una richiesta Report Builder con intervallo di date impostato su &quot;ieri&quot; e genera la data della richiesta nella stessa cella di &quot;oggi()-1&quot;.

Elenco dei formati di data supportati:

![Schermata con i formati di data supportati.](assets/date-formats.png)

