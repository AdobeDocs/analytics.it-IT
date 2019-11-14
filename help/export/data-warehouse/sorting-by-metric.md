---
description: Fornisce report di suddivisione classificati in Data Warehouse, ordinati per valore di metrica decrescente.
solution: Analytics
title: Ordina per metrica
uuid: 07da2607-b3fd-463b-90d4-6884a93c7e25
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Ordina per metrica

Fornisce report di suddivisione classificati in Data Warehouse, ordinati per valore di metrica decrescente.

L'ordinamento in base alle metriche semplifica l'interpretazione dei rapporti di Data Warehouse e consente di confrontare questi rapporti con altre viste di reporting dettagliato di Analytics.

Di seguito viene illustrato come abilitare l'opzione "Ordinamento metriche" per riordinare le righe in un report Data Warehouse.

È possibile organizzare i rapporti di Data Warehouse in quattro modi, in base alla configurazione della granularità della data, delle dimensioni di reporting o delle metriche e all'impostazione di "Numero massimo di righe":

* **Layout 1**: Le voci sono ordinate in ordine dizionario (impostazione predefinita). Se è impostato il valore "Max rows", nel rapporto vengono fornite solo le prime righe N.
* **Layout 2**: Data Warehouse applica un ordinamento delle metriche su tutte le righe del report. I legami nel primo valore della metrica sono interrotti per la seconda metrica, quindi per il terzo e così via. Quando tutte le metriche sono legate, viene applicato l'ordine standard dei dizionari degli elementi di suddivisione.
* **Layout 3**: Come Layout 2, con solo le prime N righe (ovvero il numero impostato in "max rows") in uscita nel report.
* **Layout 4**: Come Layout 2, ad eccezione del fatto che le voci per ciascun periodo di granularità della data sono raggruppate e ordinate all'interno di tale intervallo di tempo.

Fare riferimento alla colonna "Layout rapporto" in questa tabella per determinare in che modo "Ordinamento metriche" interagisce con altre opzioni di reporting di Data Warehouse.

| Ordina per metrica? | Metriche? | Sono previste suddivisioni? | Granularità data? | Numero massimo di righe impostato? | Layout report |
|---|---|---|---|---|---|
| No | Sì o No | Sì o No | Sì o No | Sì o No | 1 |
| Sì | No | Sì o No | Sì o No | Sì o No | 1 |
| Sì | Sì | No | No | N/D | 1 |
| Sì | Sì | No | Sì o No | No | 1 |
| Sì | Sì | Sì | No | No | 2 |
| Sì | Sì | No | Sì | Sì | 3 |
| Sì | Sì | Sì | Sì o No | Sì | 3 |
| Sì | Sì | Sì | Sì | No | 4 |

