---
description: Scopri come l’ordinamento per metrica semplifica l’interpretazione e il confronto dei rapporti di Data Warehouse con altre visualizzazioni di rapporti di suddivisione di Analytics.
title: Ordina per metrica
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
TQID: https://experienceleague.adobe.com/YPqL6i9RWACubLdf2ywm8xuPyeQkZ30L6rO6FAbhpJI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 337
ht-degree: 12%

---

# Ordina per metrica

Fornisce rapporti con raggruppamenti classificati in Data Warehouse, ordinati per valore di metrica decrescente.

L’ordinamento per metrica semplifica l’interpretazione dei rapporti di Data Warehouse e il confronto con altre visualizzazioni di rapporti di suddivisione di Analytics.

Di seguito viene illustrato come l’abilitazione dell’opzione &quot;Ordinamento metriche&quot; riordinerà le righe in un rapporto di Data Warehouse.

Esistono quattro possibili modi per organizzare i rapporti di Data Warehouse con &quot;Ordinamento metriche&quot;, in base alla configurazione della granularità delle date, delle dimensioni di reporting o delle metriche e all’impostazione di &quot;Righe massime&quot;:

* **Layout 1**: gli elementi riga vengono ordinati in base all&#39;ordine del dizionario (impostazione predefinita). Se è impostato &quot;Max rows&quot; (Max righe), nel rapporto vengono fornite solo le prime N righe.
* **Layout 2**: Data Warehouse applica un ordinamento metrico a tutte le righe del rapporto. I legami nel primo valore della metrica vengono interrotti dalla seconda metrica, quindi dalla terza e così via. Quando tutte le metriche sono legate, viene applicato l’ordinamento standard del dizionario per gli elementi suddivisi.
* **Layout 3**: come Layout 2, con solo le N righe superiori (ovvero il numero impostato in &quot;righe massime&quot;) restituite nel report.
* **Layout 4**: come Layout 2, con l&#39;eccezione che gli elementi riga per ogni periodo di granularità della data sono raggruppati e ordinati all&#39;interno del rispettivo intervallo di tempo.

Fai riferimento alla colonna &quot;Layout rapporto&quot; in questa tabella per determinare come &quot;Ordinamento metriche&quot; interagisce con altre opzioni di reporting di Data Warehouse.

| Ordinare per metrica? | Ha delle metriche? | Sono presenti raggruppamenti? | Granularità data? | Numero massimo di righe impostate? | Layout rapporto |
|---|---|---|---|---|---|
| No | Sì o No | Sì o No | Sì o No | Sì o No | 1 |
| Sì | No | Sì o No | Sì o No | Sì o No | 1 |
| Sì | Sì | No | No | N/D | 1 |
| Sì | Sì | No | Sì o No | No | 1 |
| Sì | Sì | Sì | No | No | 2 |
| Sì | Sì | No | Sì | Sì | 3 |
| Sì | Sì | Sì | Sì o No | Sì | 3 |
| Sì | Sì | Sì | Sì | No | 4 |
