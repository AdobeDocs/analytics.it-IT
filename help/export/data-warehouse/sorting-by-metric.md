---
description: Fornisce report di suddivisione classificati in Data Warehouse, ordinati per valore di metrica decrescente.
title: Ordina per metrica
uuid: 07da2607-b3fd-463b-90d4-6884a93c7e25
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ordina per metrica

Fornisce report di suddivisione classificati in Data Warehouse, ordinati per valore di metrica decrescente.

L&#39;ordinamento in base alle metriche semplifica l&#39;interpretazione dei rapporti di Data Warehouse e consente di confrontare questi rapporti con altre viste di reporting dettagliato di Analytics.

Di seguito viene illustrato come abilitare l&#39;opzione &quot;Ordinamento metriche&quot; per riordinare le righe in un report Data Warehouse.

È possibile organizzare i rapporti di Data Warehouse in quattro modi, in base alla configurazione della granularità della data, delle dimensioni di reporting o delle metriche e all&#39;impostazione di &quot;Numero massimo di righe&quot;:

* **Layout 1**: Le voci sono ordinate in ordine dizionario (impostazione predefinita). Se è impostato il valore &quot;Max rows&quot;, nel rapporto vengono fornite solo le prime righe N.
* **Layout 2**: Data Warehouse applica un ordinamento delle metriche su tutte le righe del report. I legami nel primo valore della metrica sono interrotti per la seconda metrica, quindi per il terzo e così via. Quando tutte le metriche sono legate, viene applicato l&#39;ordine standard dei dizionari degli elementi di suddivisione.
* **Layout 3**: Come Layout 2, con solo le prime N righe (ovvero il numero impostato in &quot;max rows&quot;) in uscita nel report.
* **Layout 4**: Come Layout 2, ad eccezione del fatto che le voci per ciascun periodo di granularità della data sono raggruppate e ordinate all&#39;interno di tale intervallo di tempo.

Fare riferimento alla colonna &quot;Layout rapporto&quot; in questa tabella per determinare in che modo &quot;Ordinamento metriche&quot; interagisce con altre opzioni di reporting di Data Warehouse.

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

