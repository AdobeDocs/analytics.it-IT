---
description: Scopri come applicare la formattazione standard e limitata agli intervalli di celle.
title: Come formattare la data in Report Builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
TQID: https://experienceleague.adobe.com/8FuosvmSvi-bRNaG5QbwUExuDffOIXbrkuiQLh0NZXM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 259
ht-degree: 8%

---

# Formattare la data

{{legacy-arb}}

Oltre alle opzioni di formattazione standard delle celle disponibili tramite la funzione Formato > Celle di Excel (Ctrl+1), è possibile applicare una formattazione limitata agli intervalli di celle con Report Builder. Queste scelte di formattazione dipendono dalla metrica scelta.

Dopo aver [aggiunto le dimensioni](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) alla griglia delle etichette di riga, fare clic su **[!UICONTROL Format]**.

Nel menu **[!UICONTROL Format]**, fare clic su **[!UICONTROL Custom Format]** per applicare formati personalizzati per date simili alla funzione di aggiunta e aggiunta. Ad esempio, puoi immettere testo che si verifica sempre dopo la data (ad esempio A.D. B.C.E. A.H. ecc.). È possibile aggiungere testo prima della data, ad esempio [!UICONTROL Start Date] e [!UICONTROL Start and End Date]. È inoltre possibile creare un&#39;espressione di data personalizzata utilizzando le abbreviazioni di giorno, mese e anno e utilizzare un separatore personalizzato tra parti della data. Tutti i formati di data devono essere composti da tre abbreviazioni racchiuse tra parentesi quadre.

Nella tabella seguente viene descritto come utilizzare le abbreviazioni di data nel campo [!UICONTROL Custom Format]:

| Abbreviazione | Significato | Esempio con mercoledì 14 marzo 2012 |
|--- |--- |--- |
| dd/MM/yyyy | Data numerica completa | 03/14/2012 |
| M | Numero di mesi | 3 |
| MM | Numero di mesi con riempimento 0 per mesi &lt; 10 | 03 |
| MMM | Nome breve del mese | Mar |
| MMMM | Nome lungo del mese | Marzo |
| D | Nome lungo della data | giovedì 14 marzo 2012 |
| d | Numero di giorni | 14 |
| gg | Numero di giorni con riempimento 0 per giorni &lt; 10 | 01 - 09 |
| ddd | Nome breve del giorno | Mer |
| dddd | Nome lungo del giorno | Mercoledì |
| aa | Anno a 2 cifre | 10 |
| aaaa | Anno a 4 cifre | 2012 |
