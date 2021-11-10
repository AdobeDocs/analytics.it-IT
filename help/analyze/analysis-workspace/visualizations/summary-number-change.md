---
description: Utilizza le visualizzazioni Numero di riepilogo e Variazione di riepilogo per visualizzare punti dati importanti in un progetto.
title: Numero di riepilogo e Variazione di riepilogo
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: c4f6a7a3d81160a1c86ebfa70d1e376882ccfee2
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 84%

---

# [!UICONTROL Summary Number] e [!UICONTROL Summary Change]

Ecco un video sulle due visualizzazioni:

>[!VIDEO](https://video.tv.adobe.com/v/335564/?quality=12)

## [!UICONTROL Summary Number] visualizzazione {#summary-number}

Utilizza la [!UICONTROL Summary Number] visualizzazione per evidenziare un numero elevato importante in un progetto. Questa visualizzazione si comporta come segue:

* Se non è selezionata alcuna cella, viene selezionato il totale della colonna.
* Se è selezionata una cella, viene visualizzato il riepilogo per tale cella.
* Se sono selezionate più celle, viene visualizzata la prima cella selezionata.
* Se è selezionata la colonna, viene preso il valore della prima cella della colonna.

Fai clic sull’ingranaggio delle **impostazioni di visualizzazione** in alto a destra per configurare le impostazioni del Numero di riepilogo:

| Impostazione | Definizione |
|--- |--- |
| [!UICONTROL Percentages] | Visualizza le percentuali invece dei numeri. |
| [!UICONTROL Legend visible] | Mostra informazioni sulla metrica visualizzata. |
| [!UICONTROL Abbreviate value] | Scegli di abbreviare i valori e visualizzare fino a 3 posizioni decimali. |
| [!UICONTROL Summarize value by] | Scegli di visualizzare il massimo, il minimo, la media, la mediana o la somma per una selezione di dati. |

## [!UICONTROL Summary Change] visualizzazione {#summary-change}

Utilizza la [!UICONTROL Summary Change] visualizzazione per mostrare il delta (cambiamento) tra due numeri. Il colore verde e rosso del [!UICONTROL Summary Change] può essere controllato tramite [polarità degli eventi personalizzati](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html?lang=it) o di una metrica calcolata [Mostra tendenza verso l’alto come](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=it) opzione .

Questa visualizzazione si comporta come segue:

* Se non è selezionata alcuna cella, vengono confrontati i valori delle prime due celle della colonna.
* Se è selezionata una cella, viene riportato 0 perché il valore della cella viene confrontato con se stesso e quindi non si verifica alcuna variazione nei valori.
* Se sono selezionate due celle, la prima cella selezionata funge da numeratore e la seconda da denominatore.
* Se sono selezionate più celle, per il confronto vengono considerate solo le prime due celle.
* Se è selezionato un intervallo di celle, vengono confrontate la prima e l’ultima cella selezionata nell’intervallo.
* Se è selezionata la colonna, il primo valore viene confrontato con se stesso, e la variazione risulta quindi pari a 0.


![](assets/summary-change.png)


Fai clic sull’ingranaggio delle **impostazioni di visualizzazione** in alto a destra per configurare le impostazioni della Variazione di riepilogo:

| Impostazione | Definizione |
| --- | --- |
| [!UICONTROL Percentages] | Visualizza le percentuali invece dei numeri. |
| [!UICONTROL Legend visible] | Mostra informazioni sulla metrica visualizzata. |
| [!UICONTROL Show Percent Change] | Mostra la variazione percentuale tra i 2 numeri. |
| [!UICONTROL Show Raw Difference] | Mostra la differenza grezza tra i 2 numeri. Con questa opzione è inoltre possibile abbreviare i valori e visualizzare fino a 3 posizioni decimali. |
