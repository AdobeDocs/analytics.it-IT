---
title: Esportazione browser
description: L’esportazione del browser consente di esportare i dati di classificazione in un file delimitato da tabulazioni.
feature: Classifications
exl-id: f4c709b2-f707-4e3c-82ba-6b43def3e698
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 2%

---

# Esportazione browser

L’esportazione del browser consente di esportare i dati di classificazione in un file delimitato da tabulazioni.

[!UICONTROL Admin] > [!UICONTROL Classification Importer]

Il file del set di dati è un file di dati delimitato da tabulazioni (estensione del nome del file .tab) supportato dalla maggior parte delle applicazioni per fogli di calcolo.

>[!NOTE]
>Le esportazioni del browser hanno un limite di 30 colonne.

## Descrizioni dei campi

| Elemento | Descrizioni |
| --- | --- |
| Seleziona suite di rapporti | Seleziona la suite di rapporti da cui vuoi esportare i dati del rapporto. |
| Set di dati da classificare | Dal menu a discesa, seleziona il set di dati da classificare. |
| Seleziona numero di righe | Specifica quante righe di dati esportare.<ul><li>Seleziona **[!UICONTROL All]** per scaricare tutti i dati del rapporto (fino a 50.000 righe).</li><li>Seleziona **[!UICONTROL Limit Data Rows To]** per specificare un numero specifico di righe da scaricare.</li></ul>Se desideri scaricare più di 50.000 righe di dati, utilizza l&#39;opzione di download FTP. |
| Filtra per data ricezione | (Facoltativo) Filtrare i dati in base alla data di ricezione. Specifica l’intervallo di date per il quale vuoi scaricare i dati. |
| Applica filtro dati | (Facoltativo) Filtrare il set di dati in base ai criteri di dati. Puoi filtrare il download per includere righe di dati che includono un valore specifico o righe di dati con valori di colonna (classificazione) non assegnati. Quando applichi i filtri dati, considera i seguenti problemi:<ul><li>Puoi utilizzare i caratteri jolly durante la definizione del filtro dati. Usa un asterisco per corrispondere a zero o più caratteri e un punto interrogativo `?` per corrispondere esattamente a un carattere. Utilizzo `?*` per far corrispondere uno o più caratteri.</li><li>In genere, quando si applicano entrambi i tipi di filtri dati a un download, vengono scaricate solo le righe corrispondenti a entrambe le regole. Tuttavia, si applicano le seguenti eccezioni:<ul><li>Se Righe con colonna vuota = Tutte le colonne, tutte le colonne tranne la colonna specificata nella prima regola vengono controllate per verificare la presenza di vuoti. Questa eccezione assicura che il sistema scarichi qualsiasi riga con una colonna che corrisponde alla prima regola con tutte le altre colonne vuote.</li><li>Durante il download di righe di dati basate su colonne vuote, tutte le colonne eccetto quelle specificate nella prima regola vengono controllate se non si verificano problemi.</li><li>Se per entrambe le regole di filtro è specificata la stessa colonna (è quasi impossibile soddisfare entrambi i criteri), vengono scaricate solo le righe che corrispondono alla prima regola.</li></ul></ul> |
| Filtro dati | (Facoltativo) Filtrare i dati per campagna. È possibile scaricare dati solo da campagne attive oppure selezionare campagne iniziate (o terminate) in un intervallo di date specifico.<br>**Importante**: Questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione. |
| Esporta numerico 2 | Puoi importare le classificazioni numeriche 2 nel sistema utilizzando l’importazione. Le classificazioni numeriche 2 sono utili per le variabili che cambiano nel tempo per elementi diversi, ad esempio i valori di costo e budget per il rapporto Canale marketing. Per informazioni sul caricamento di dati utilizzando classificazioni numeriche 2, consulta Classificazioni numeriche 2 . |
| Codifica | Selezionare la codifica dei caratteri per il file di dati. Il formato di codifica predefinito è UTF-8 o ISO-8859-1, in base alla codifica caricata per la classificazione. UTF-8 in UTF-16 converte le classificazioni codificate UTF-8 in codifica UTF-16. La codifica ISO-8859-1 in UTF-16 converte le classificazioni codificate ISO-8859-1 in codifica UTF-16.<br>**Nota:** Se selezioni la conversione in UTF-16, la codifica sorgente deve corrispondere alla codifica del caricamento originale oppure potresti ottenere risultati imprevisti. È consigliabile codificare tutti i file caricati in UTF-8 senza BOM. |
| Output preventivo | Specifica la versione 2.1 del file di classificazione. Questa impostazione consente di posizionare le virgolette intorno ai caratteri speciali per garantire che le esportazioni funzionino in Excel quando esiste un&#39;interruzione di riga nei valori di eVar. Per verificare se un file di classificazione è nella versione 2.1, apri il file scaricato. Vedrai la versione 2.1 nell’intestazione. Ad esempio: `## SC SiteCatalyst SAINT Import File v:2.1` |

## Esportare i dati di classificazione utilizzando il browser

1. Fai clic su [!UICONTROL Admin] > [!UICONTROL Classification Importer].
1. Fai clic sulla scheda [!UICONTROL Browser Export].
1. Specifica i dettagli del set di dati.
1. Fai clic su [!UICONTROL Export File].
1. Salva il set di dati nel sistema locale.
