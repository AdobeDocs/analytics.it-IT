---
description: Le classificazioni numeriche 2 offrono metriche personalizzate e flessibili da importare in Adobe Marketing Cloud tramite l'importazione.
seo-description: Le classificazioni numeriche 2 offrono metriche personalizzate e flessibili da importare in Adobe Marketing Cloud tramite l'importazione.
seo-title: Panoramica classificazioni numeriche 2
solution: Analytics
subtopic: Classificazioni
title: Panoramica classificazioni numeriche 2
topic: Strumenti di amministrazione
uuid: cbea 7 cd 1-3 a 92-4 e 9 d-b 671-646 e 9 add 1 ee 6
translation-type: tm+mt
source-git-commit: 49e149fe57d5d66b8eda22b1bdf60e7c6200761c

---


# Panoramica classificazioni numeriche 2

Le classificazioni numeriche 2 offrono metriche personalizzate e flessibili da importare in Adobe Marketing Cloud tramite l'importazione.

>[!IMPORTANT]
>
>La possibilità di importare le classificazioni Numeriche 2 e Abilitate per data è stata rimossa dal codebase. Questa modifica entrerà in vigore con la versione di manutenzione di luglio 2019. Se nel file di importazione sono presenti colonne numeriche o abilitate per data, tali celle verranno automaticamente ignorate e gli altri dati del file verranno importati come di consueto. Le classificazioni esistenti possono ancora essere esportate attraverso il flusso di lavoro di classificazione standard e continueranno a essere disponibili nei rapporti.

>[!NOTE]
>
>Nella versione del 10 maggio 2018 di Analytics, Adobe ha iniziato a limitare la funzionalità delle classificazioni numeriche e abilitate per le date. Questi tipi di classificazione sono stati rimossi dalle interfacce Admin (Amministratore) e Classification Importer (Importazione classificazione). Non è possibile aggiungere nuove classificazioni numeriche e abilitate per le date. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti.

Un modo comune per utilizzare classificazioni numeriche 2 è per le variabili numeriche che cambiano nel tempo per elementi diversi, ad esempio i costi di beni venduti. In admin, you can create classifications on the [!UICONTROL Conversion Classification] page, and then use the importer to export a file, make edits, and then import the file back in to Adobe. Dopo aver importato i dati, potete utilizzare le classificazioni numeriche durante la creazione di metriche calcolate.

>[!IMPORTANT]
>
>Analysis Workspace e Analisi ad hoc non supportano le classificazioni numeriche 2.

La tabella seguente illustra le differenze tra i tipi di classificazione:

| FEATURE | TEXT | NUMERIC 1.0 | NUMERIC 2.0 |
|---|---|---|---|
| Visualizzato come rapporto | Sì | No | No |
| Può essere usato come metrica | No | Sì | Sì |
| Può essere creato nel rapporto di base | Sì | No | Sì |
| Calcolato in base agli eventi | No | Sì | Sì |
| Righe multiple per chiave | No | No | Sì |
| Può avere valori diversi per periodi di tempo diversi | No | No | Sì |
| Può essere usato nelle metriche calcolate | No | Sì | Sì |

