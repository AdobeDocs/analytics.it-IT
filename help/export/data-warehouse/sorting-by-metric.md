---
description: Fornisce rapporti di suddivisione classificati in Data Warehouse, ordinati in base al valore della metrica decrescente.
seo-description: Fornisce rapporti di suddivisione classificati in Data Warehouse, ordinati in base al valore della metrica decrescente.
seo-title: Ordina per metrica
solution: Analytics
title: Ordina per metrica
uuid: 07 da 2607-b 3 fd -463 b -90 d 4-6884 a 93 c 7 e 25
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Ordina per metrica

Fornisce rapporti di suddivisione classificati in Data Warehouse, ordinati in base al valore della metrica decrescente.

Ordinamento per metrica facilita l'interpretazione dei rapporti Data Warehouse e facilita la confronto di questi report con altre visualizzazioni Analisi analisi analisi Analytics.

Di seguito viene illustrato come abilitare l'opzione «Ordine metriche» per riordinare le righe in un rapporto Data Warehouse.

In quattro modi possibili, i rapporti Data Warehouse possono essere organizzati con «Sort Rics Sort» (Ordina metriche), in base alla configurazione della granularità data, alle dimensioni di reporting o alle metriche e alla configurazione di "Max rows":

* **Layout 1**: Gli elementi della linea vengono ordinati in ordine dizionario (impostazione predefinita). Se è impostata «Max rows», nel rapporto sono incluse solo le prima riga N.
* **Layout 2**: Data Warehouse applica una metrica per tutte le righe del report. Le relazioni nel primo valore della metrica sono interrotte dalla metrica della 2 nd, quindi dalla 3 rd e così via. Quando tutte le metriche sono legate, viene applicato l'ordine dizionario standard degli elementi della linea di suddivisione.
* **Layout 3**: Come Layout 2, con solo le righe N superiore (cioè il numero impostato in «max rows») che viene restituito nel report.
* **Layout 4**: Come Layout 2, con l'eccezione che gli elementi della riga per ogni periodo di granularità data sono raggruppati e ordinati all'interno di tale intervallo di tempo.

Fai riferimento alla colonna «Report layout» (Layout report) in questa tabella per determinare in che modo «Sort Rics Sort» interagisce con altre opzioni di reporting di Data Warehouse.

| Ordina per metrica? | Hai metriche? | Hai suddivisioni? | Granularità data? | Massimo righe impostate? | Layout report |
|---|---|---|---|---|---|
| No | Sì o No | Sì o No | Sì o No | Sì o No | 1 |
| Sì | No | Sì o No | Sì o No | Sì o No | 1 |
| Sì | Sì | No | No | N/D | 1 |
| Sì | Sì | No | Sì o No | No | 1 |
| Sì | Sì | Sì | No | No | 2 |
| Sì | Sì | No | Sì | Sì | 3 |
| Sì | Sì | Sì | Sì o No | Sì | 3 |
| Sì | Sì | Sì | Sì | No | 4 |

