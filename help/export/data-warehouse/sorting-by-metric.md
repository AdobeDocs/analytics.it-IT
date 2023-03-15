---
description: Fornisce rapporti con raggruppamenti classificati in Date Warehouse, ordinati per valore di metrica decrescente.
title: Ordina per metrica
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 15%

---

# Ordina per metrica

Fornisce rapporti con raggruppamenti classificati in Date Warehouse, ordinati per valore di metrica decrescente.

L’ordinamento per metrica semplifica l’interpretazione dei rapporti Data Warehouse e ne agevola la comparazione con altre visualizzazioni di reporting di suddivisione di Analytics.

Di seguito viene illustrato come l’abilitazione dell’opzione &quot;Ordinamento metriche&quot; riordinerà le righe in un rapporto di Data Warehouse.

Esistono quattro possibili modi per organizzare i rapporti Date Warehouse con &quot;Ordinamento metriche&quot;, in base alla configurazione della granularità delle date, delle dimensioni di reporting o delle metriche e all’impostazione di &quot;Righe massime&quot;:

* **Layout 1**: gli elementi riga vengono ordinati in ordine di dizionario (impostazione predefinita). Se è impostato &quot;Max rows&quot; (Max righe), nel rapporto vengono fornite solo le prime N righe.
* **Layout 2**: Data Warehouse applica un ordinamento metrico su tutte le righe del rapporto. I legami nel primo valore della metrica vengono interrotti dalla seconda metrica, quindi dalla terza e così via. Quando tutte le metriche sono legate, viene applicato l’ordinamento standard del dizionario per gli elementi suddivisi.
* **Layout 3**: come Layout 2, con solo le N righe superiori (ovvero il numero impostato in &quot;max rows&quot;) generate nel rapporto.
* **Layout 4**: come Layout 2, con l’eccezione che gli elementi riga per ogni periodo di granularità della data sono raggruppati e ordinati all’interno del rispettivo intervallo di tempo.

Fai riferimento alla colonna &quot;Layout rapporto&quot; in questa tabella per determinare come &quot;Ordinamento metriche&quot; interagisce con altre opzioni di reporting per Date Warehouse.

| Ordina per metrica? | Ha delle metriche? | Sono presenti raggruppamenti? | Granularità data? | Numero massimo di righe impostate? | Layout rapporto |
|---|---|---|---|---|---|
| No | Sì o No | Sì o No | Sì o No | Sì o No | 1 |
| Sì | No | Sì o No | Sì o No | Sì o No | 1 |
| Sì | Sì | No | No | N/D | 1 |
| Sì | Sì | No | Sì o No | No | 1 |
| Sì | Sì | Sì | No | No | 2 |
| Sì | Sì | No | Sì | Sì | 3 |
| Sì | Sì | Sì | Sì o No | Sì | 3 |
| Sì | Sì | Sì | Sì | No | 4 |
