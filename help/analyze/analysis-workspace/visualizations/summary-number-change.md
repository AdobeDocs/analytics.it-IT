---
description: nulle
seo-description: nulle
seo-title: Numero di riepilogo e Variazione di riepilogo
title: Numero di riepilogo e Variazione di riepilogo
uuid: 177 c 1 b 89-6 d 98-473 d -8447-6 b 4 cdc 479565
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Numero di riepilogo e Variazione di riepilogo

## Visualizzazione Numero di riepilogo

* Se non è selezionata alcuna cella, viene selezionato il totale della colonna.
* Se è selezionata una cella, viene visualizzato il riepilogo per tale cella.
* Se sono selezionate più celle, viene visualizzata la prima cella selezionata.
* Se è selezionata la colonna, viene preso il valore della prima cella della colonna.

![](assets/summary-number.png)

## Visualizzazione Variazione di riepilogo

* Se non è selezionata alcuna cella, vengono confrontati i valori delle prime due celle della colonna.
* Se è selezionata una cella, viene riportato 0 perché il valore della cella viene confrontato con se stesso e quindi non si verifica alcuna variazione nei valori.
* Se sono selezionate due celle, la prima cella selezionata funge da numeratore e la seconda da denominatore.
* Se sono selezionate più celle, per il confronto vengono considerate solo le prime due celle.
* Se è selezionato un intervallo di celle, vengono confrontate la prima e l’ultima cella selezionata nell’intervallo.
* Se è selezionata la colonna, il primo valore viene confrontato con se stesso, e la variazione risulta quindi pari a 0.
* È possibile controllare il colore verde e rosso della variazione di riepilogo tramite:

   * [Polarità di un evento personalizzato](https://marketing.adobe.com/resources/help/en_US/reference/success_event.html).
   * Opzione [Show Upward Trend As](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_build_metrics.html) (Mostra tendenza ascendente come) per una metrica calcolata.

## Summary Change settings {#section_2581AC0107634FB4990AB8347E5897AA}

Fai clic sull’icona dell’ingranaggio accanto alla visualizzazione per configurare le impostazioni Riepilogo:

| Impostazione | Definizione |
|--- |--- |
| Percentuali | Usa le percentuali invece dei numeri. |
| Visualizzazione legenda | Mostra le metriche utilizzate. |
| Opzioni di Numero di riepilogo: Abbrevia valore | Puoi scegliere da 0 a 3 cifre decimali per i valori abbreviati. |
| Opzioni Variazione di riepilogo: Mostra variazione percentuale | Mostra la variazione tra 2 numeri, espressa in percentuale. |
| Opzioni Variazione di riepilogo: Mostra differenza raw | Mostra la differenza grezza tra 2 numeri. |