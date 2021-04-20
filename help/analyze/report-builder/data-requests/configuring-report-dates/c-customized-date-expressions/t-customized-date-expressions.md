---
description: Puoi specificare un intervallo di date complesso creando un’espressione personalizzata.
title: 'Espressioni data personalizzate: panoramica'
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 4%

---


# Espressioni data personalizzate: panoramica

Puoi specificare un intervallo di date complesso creando un’espressione personalizzata.

È consigliabile fare riferimento a un calendario durante la creazione di espressioni al fine di specificare correttamente il numero di settimane e giorni. Excel dispone di diverse funzioni integrate che consentono di calcolare il numero di giorni, giorni lavorativi, mesi e anni tra le date. È possibile utilizzare queste funzioni nelle formule per calcolare altri intervalli, ad esempio settimane e trimestri.

**Per abilitare espressioni personalizzate**

Questo è un esempio che utilizza **[!UICONTROL Rolling Dates]**.

1. In [!UICONTROL Request Wizard: Step 1], invece di utilizzare **[!UICONTROL Preset Dates]**, selezionare **[!UICONTROL Rolling Dates]**.

   ![](assets/rolldates1.png)

1. Passa a settimanale, mensile, trimestrale o annuale. Osserva come cambiano le opzioni riportate di seguito.
1. Per ulteriori opzioni di personalizzazione, fai clic su **[!UICONTROL Show Advanced Options]**.

   ![](assets/rolldates2.png)

1. Ad esempio, se modifichi le date di cui sopra in continuo mensile dal primo giorno tre mesi fa al primo giorno di questo mese, le date nella porzione Opzioni anticipo si aggiornano per riflettere che:

   ![](assets/rolldatesfor3.png)

1. Abilita **[!UICONTROL Customize Expression]**. Selezionando le opzioni in **[!UICONTROL Rolling Dates]**, è possibile visualizzare facilmente la sintassi per le espressioni data personalizzate.

   ![](assets/rolldatesfor5.png)

   È possibile utilizzare Opzioni avanzate per combinare e abbinare espressioni di data personalizzate. Ad esempio, se desideri visualizzare i dati dal primo dell’anno alla fine dell’ultimo mese completo, puoi immettere quanto segue: `From: cy` `To: cm-1d`. Nella procedura guidata, tali date sono visualizzate come 01/01/2020-1/31/2020.
