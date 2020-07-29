---
description: Le classificazioni numeriche 2 forniscono metriche personalizzate e flessibili che è possibile importare nell'Adobe Experience Cloud tramite l'importazione.
subtopic: Classifications
title: Panoramica delle classificazioni numeriche 2
topic: Admin tools
uuid: cbea7cd1-3a92-4e9d-b671-646e9add1ee6
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 37%

---


# Panoramica delle classificazioni numeriche 2

Le classificazioni numeriche 2 forniscono metriche personalizzate e flessibili che è possibile importare nell&#39;Adobe Experience Cloud tramite l&#39;importazione.

>[!IMPORTANT]
>
>La possibilità di importare le classificazioni Numeriche 2 e Abilitate per data è stata rimossa dal codebase. Questa modifica entrerà in vigore con la versione di manutenzione di luglio 2019. Se nel file di importazione sono presenti colonne numeriche o abilitate per data, tali celle verranno automaticamente ignorate e gli altri dati del file verranno importati come di consueto. Le classificazioni esistenti possono ancora essere esportate attraverso il flusso di lavoro di classificazione standard e continueranno a essere disponibili nei rapporti.

>[!NOTE]
>
>Nella versione di manutenzione di Analytics del 10 maggio 2018,  Adobe ha iniziato a limitare le funzionalità delle classificazioni numeriche e abilitate per le date. Questi tipi di classificazione sono stati rimossi dalle interfacce Admin (Amministratore) e Classification Importer (Importazione classificazione). Non è possibile aggiungere nuove classificazioni numeriche e abilitate per le date. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti.

Un modo comune di utilizzare classificazioni numeriche 2 è per le variabili numeriche che cambiano nel tempo per diversi elementi, come il costo dei beni venduti. In admin, potete creare classificazioni sulla [!UICONTROL Conversion Classification] pagina, quindi utilizzare Importazione per esportare un file, apportare modifiche e quindi importare nuovamente il file nel Adobe . Dopo aver importato i dati, puoi utilizzare le classificazioni numeriche per creare le metriche calcolate.

>[!IMPORTANT]
>
> Analysis Workspace e  Ad hoc analysis non supportano le classificazioni Numeric 2.

Nella tabella seguente sono illustrate le differenze tra i tipi di classificazione:

| FUNZIONALITÀ | TEXT | NUMERICO 1.0 | NUMERICO 2.0 |
|---|---|---|---|
| Visualizzato come rapporto | Sì | No | No |
| Può essere utilizzato come metrica | No | Sì | Sì |
| Può essere creato sul report di base | Sì | No | Sì |
| Calcolato in base agli eventi | No | Sì | Sì |
| Più righe per chiave | No | No | Sì |
| Può avere valori diversi per periodi di tempo diversi | No | No | Sì |
| Può essere utilizzato nelle metriche calcolate | No | Sì | Sì |

