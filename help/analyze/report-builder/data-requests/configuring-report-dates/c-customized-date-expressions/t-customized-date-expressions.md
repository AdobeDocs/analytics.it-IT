---
description: Per specificare un intervallo di date complesso, crea un’espressione personalizzata.
title: 'Espressioni data personalizzate: panoramica'
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: User, Admin
exl-id: b3bdc07e-5c2d-4be3-86c9-b4b7380be0f6
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# Espressioni data personalizzate: panoramica

Per specificare un intervallo di date complesso, crea un’espressione personalizzata.

È consigliabile fare riferimento a un calendario durante la creazione di espressioni per specificare correttamente il numero di settimane e giorni. In Excel sono disponibili diverse funzioni incorporate che consentono di calcolare il numero di giorni, giorni lavorativi, mesi e anni tra le date. È possibile utilizzare queste funzioni nelle formule per calcolare altri intervalli, ad esempio settimane e trimestri.

**Per abilitare le espressioni personalizzate**

Questo è un esempio che utilizza **[!UICONTROL Rolling Dates]**.

1. Il giorno [!UICONTROL Request Wizard: Step 1], invece di utilizzare **[!UICONTROL Preset Dates]**, seleziona **[!UICONTROL Rolling Dates]**.

   ![](assets/rolldates1.png)

1. Passa a continuo settimanale, mensile, trimestrale o annuale. Osserva come cambiano le opzioni qui sotto.
1. Per ulteriori opzioni di personalizzazione, fai clic su **[!UICONTROL Show Advanced Options]**.

   ![](assets/rolldates2.png)

1. Ad esempio, se modifichi le date di cui sopra in mensili continui dal primo giorno di tre mesi fa al primo giorno di questo mese, le date nella sezione delle opzioni di anticipo si aggiornano automaticamente in modo da riflettere quanto segue:

   ![](assets/rolldatesfor3.png)

1. Abilita **[!UICONTROL Customize Expression]**. Selezionando le opzioni in **[!UICONTROL Rolling Dates]**, la sintassi delle espressioni data personalizzate è facilmente visibile.

   ![](assets/rolldatesfor5.png)

   Puoi utilizzare le Opzioni avanzate per combinare e abbinare espressioni data personalizzate. Ad esempio, per visualizzare i dati dal primo dell&#39;anno fino alla fine dell&#39;ultimo mese completo, immettere quanto segue: `From: cy` `To: cm-1d`. Nella procedura guidata, tali date vengono visualizzate come 1/1/2020-1/31/2020.
