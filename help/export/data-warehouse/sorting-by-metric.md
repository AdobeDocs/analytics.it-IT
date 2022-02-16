---
description: Fornisce rapporti di suddivisione classificati nella Data Warehouse, ordinati per valore di metrica decrescente.
title: Ordina per metrica
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 15%

---

# Ordina per metrica

Fornisce rapporti di suddivisione classificati nella Data Warehouse, ordinati per valore di metrica decrescente.

L’ordinamento per metrica semplifica l’interpretazione dei rapporti sulle Date Warehouse e facilita il confronto con altre visualizzazioni di reporting con suddivisione di Analytics.

Di seguito viene illustrato come abilitare l’opzione &quot;Ordinamento metriche&quot; per riordinare le righe in un rapporto di Data Warehouse.

Esistono quattro modi possibili per organizzare i rapporti di Data Warehouse con &quot;Ordinamento metriche&quot;, in base alla configurazione della granularità della data, delle dimensioni di reporting o delle metriche e all’impostazione di &quot;Numero massimo di righe&quot;:

* **Layout 1**: Gli elementi riga vengono ordinati in ordine dizionario (impostazione predefinita). Se è impostato il valore &quot;Max rows&quot;, nel rapporto vengono fornite solo le prime N righe.
* **Layout 2**: Data Warehouse applica un ordinamento metrico su tutte le righe del rapporto. I legami nel primo valore della metrica vengono interrotti per la seconda metrica, quindi per il terzo e così via. Quando tutte le metriche sono legate, viene applicato l’ordine standard del dizionario degli elementi della riga di suddivisione.
* **Layout 3**: Come Layout 2, con solo le prime N righe (ovvero il numero impostato in &quot;max rows&quot;) in uscita nel report.
* **Layout 4**: Come Layout 2, con l’eccezione che le voci di riga per ciascun periodo di granularità della data sono raggruppate e ordinate all’interno del rispettivo intervallo di tempo.

Fai riferimento alla colonna &quot;Layout dei rapporti&quot; in questa tabella per determinare in che modo &quot;Ordinamento delle metriche&quot; interagisce con altre opzioni di reporting delle Date Warehouse.

| Ordina per metrica? | Ha delle metriche? | Ha suddivisioni? | Granularità della data? | Numero massimo di righe impostate? | Layout dei rapporti |
|---|---|---|---|---|---|
| No | Sì o No | Sì o No | Sì o No | Sì o No | 1 |
| Sì | No | Sì o No | Sì o No | Sì o No | 1 |
| Sì | Sì | No | No | N/D | 1 |
| Sì | Sì | No | Sì o No | No | 1 |
| Sì | Sì | Sì | No | No | 2 |
| Sì | Sì | No | Sì | Sì | 3 |
| Sì | Sì | Sì | Sì o No | Sì | 3 |
| Sì | Sì | Sì | Sì | No | 4 |
