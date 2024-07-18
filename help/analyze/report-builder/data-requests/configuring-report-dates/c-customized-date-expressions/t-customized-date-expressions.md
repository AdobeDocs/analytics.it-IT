---
description: Per specificare un intervallo di date complesso, crea un’espressione personalizzata.
title: 'Espressioni data personalizzate: panoramica'
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: User, Admin
exl-id: b3bdc07e-5c2d-4be3-86c9-b4b7380be0f6
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 1%

---

# Espressioni data personalizzate

Per specificare un intervallo di date complesso, crea un’espressione personalizzata.

Quando crei espressioni, fai riferimento a un calendario per specificare correttamente il numero di settimane e giorni. In Excel sono disponibili diverse funzioni incorporate che consentono di calcolare il numero di giorni, giorni lavorativi, mesi e anni tra le date. È possibile utilizzare queste funzioni nelle formule per calcolare altri intervalli, ad esempio settimane e trimestri.

**Per abilitare le espressioni personalizzate**

Nell&#39;esempio seguente viene illustrato come abilitare un&#39;espressione personalizzata per **[!UICONTROL Rolling Dates]**.

1. In [!UICONTROL Request Wizard: Step 1], invece di utilizzare **[!UICONTROL Preset Dates]**, selezionare **[!UICONTROL Rolling Dates]**.

   ![Schermata che mostra le date continue selezionate.](assets/rolldates1.png)

1. Passa a continuo settimanale, mensile, trimestrale o annuale. Osserva come cambiano le opzioni qui sotto.
1. Per ulteriori opzioni di personalizzazione, fare clic su **[!UICONTROL Show Advanced Options]**.

   ![Schermata che evidenzia le opzioni avanzate di Mostra.](assets/rolldates2.png)

1. Ad esempio, se modifichi le date di cui sopra in mensili continui dal primo giorno di tre mesi fa al primo giorno di questo mese, le date nella sezione delle opzioni di anticipo si aggiornano automaticamente in modo da riflettere quanto segue:

   ![Schermata che mostra le date continue dal primo giorno di tre mesi fa al primo giorno di questo mese.](assets/rolldatesfor3.png)

1. Abilita **[!UICONTROL Customize Expression]**. Selezionando le opzioni in **[!UICONTROL Rolling Dates]**, è possibile visualizzare facilmente la sintassi per le espressioni data personalizzate.

   ![Schermata che mostra l&#39;espressione personalizzata selezionata.](assets/rolldatesfor5.png)

   Puoi utilizzare le Opzioni avanzate per combinare e abbinare espressioni data personalizzate. Se ad esempio si desidera visualizzare i dati dal primo dell&#39;anno fino alla fine dell&#39;ultimo mese completo, è possibile immettere quanto segue: `From: cy` `To: cm-1d`. Nella procedura guidata, tali date vengono visualizzate come 1/1/2020-1/31/2020.
