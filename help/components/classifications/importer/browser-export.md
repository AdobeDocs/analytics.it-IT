---
title: Esportazione browser
description: L’esportazione del browser consente di esportare i dati di classificazione in un file delimitato da tabulazioni.
source-git-commit: 8a5c7309b5d4061b2e3241219d9bdb1521294535
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 1%

---


# Esportazione browser

L’esportazione del browser consente di esportare i dati di classificazione in un file delimitato da tabulazioni.

Amministratore > Importatore di classificazione

Il file del set di dati è un file di dati delimitato da tabulazioni (estensione del nome del file .tab) supportato dalla maggior parte delle applicazioni per fogli di calcolo.

>[!NOTE]
>Le esportazioni del browser hanno un limite di 30 colonne.

## Descrizioni dei campi

| Elemento | Descrizioni |
| --- | --- |
| Seleziona suite di rapporti | Seleziona la suite di rapporti da cui vuoi esportare i dati del rapporto. |
| Set di dati da classificare | Dal menu a discesa, seleziona il set di dati da classificare. |
| Seleziona numero di righe | Specifica quante righe di dati esportare.<ul><li>Seleziona **[!UICONTROL All]** per scaricare tutti i dati del rapporto (fino a 50.000 righe).</li><li>Seleziona **[!UICONTROL Limit Data Rows To]** se desideri specificare un numero specifico di righe da scaricare.</li></ul>Se desideri scaricare più di 50.000 righe di dati, utilizza l&#39;opzione di download FTP. |
| Filtra per data ricezione | (Facoltativo) Filtrare i dati in base alla data di ricezione. Specifica l’intervallo di date per il quale vuoi scaricare i dati. |
| Applica filtro dati | (Facoltativo) Filtrare il set di dati in base ai criteri di dati. Puoi filtrare il download per includere righe di dati che includono un valore specifico o righe di dati con valori di colonna (classificazione) non assegnati. Quando applichi i filtri dati, considera i seguenti problemi:<ul><li>Puoi utilizzare i caratteri jolly durante la definizione del filtro dati. Usa un asterisco per corrispondere a zero o più caratteri e un punto interrogativo `?` per corrispondere esattamente a un carattere. Utilizza `?*` per far corrispondere uno o più caratteri.</li><li>In genere, quando si applicano entrambi i tipi di filtri dati a un download, vengono scaricate solo le righe corrispondenti a entrambe le regole. Tuttavia, si applicano le seguenti eccezioni:<ul><li>Se Righe con colonna vuota = Tutte le colonne, tutte le colonne tranne la colonna specificata nella prima regola vengono controllate per verificare la presenza di vuoti. Questa eccezione assicura che il sistema scarichi qualsiasi riga con una colonna che corrisponde alla prima regola con tutte le altre colonne vuote.</li><li>Durante il download di righe di dati basate su colonne vuote, tutte le colonne eccetto quelle specificate nella prima regola vengono controllate se non si verificano problemi.</li><li>Se per entrambe le regole di filtro è specificata la stessa colonna (è quasi impossibile soddisfare entrambi i criteri), vengono scaricate solo le righe che corrispondono alla prima regola.</li></ul></ul> |
| Filtro dati | (Facoltativo) Filtrare i dati per campagna. È possibile scaricare dati solo da campagne attive oppure selezionare campagne iniziate (o terminate) in un intervallo di date specifico.<br>**Importante**: Questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione. |

