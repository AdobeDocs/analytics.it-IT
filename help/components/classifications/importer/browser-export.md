---
title: Esportazione browser
description: L’esportazione del browser consente di esportare i dati di classificazione in un file delimitato da tabulazioni.
feature: Classifications
exl-id: f4c709b2-f707-4e3c-82ba-6b43def3e698
TQID: https://experienceleague.adobe.com/ANvaOLL9nnb1tnG-gsmzSzkZk2ame-SJfQzyT6rGq2w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 640
ht-degree: 2%

---

# Esportazione browser (legacy)

{{classification-importer-deprecation}}

L’esportazione del browser consente di esportare i dati di classificazione in un file delimitato da tabulazioni.

[!UICONTROL Admin] > [!UICONTROL Classification Importer]

Il file del set di dati è un file di dati delimitato da tabulazioni (estensione del nome file .tab) supportato dalla maggior parte delle applicazioni per fogli di calcolo.

>[!NOTE]
>Le esportazioni del browser hanno un limite di 30 colonne.

## Descrizioni dei campi

| Elemento | Descrizioni |
| --- | --- |
| Seleziona suite di rapporti | Seleziona la suite di rapporti da cui desideri esportare i dati del rapporto. |
| Set di dati da classificare | Dal menu a discesa, seleziona il set di dati da classificare. |
| Seleziona numero di righe | Specifica quante righe di dati esportare.<ul><li>Selezionare **[!UICONTROL All]** per scaricare tutti i dati del report (fino a 50.000 righe).</li><li>Selezionare **[!UICONTROL Limit Data Rows To]** se si desidera specificare un numero specifico di righe da scaricare.</li></ul>Se desideri scaricare più di 50.000 righe di dati, utilizza l’opzione di download FTP. |
| Filtra per data di ricezione | (Facoltativo) Filtra i dati in base alla data di ricezione. Specifica l’intervallo di date per il quale desideri scaricare i dati. |
| Applica filtro dati | (Facoltativo) Filtra il set di dati in base a criteri di dati. Puoi filtrare il download per includere righe di dati che includono un valore specifico o righe di dati con valori di colonna (classificazione) non assegnati. Quando applichi i filtri dati, considera i seguenti problemi:<ul><li>È possibile utilizzare caratteri jolly durante la definizione del filtro dati. Utilizzare un asterisco per far corrispondere zero o più caratteri e un punto interrogativo `?` per far corrispondere esattamente un carattere. Utilizza `?*` per trovare uno o più caratteri.</li><li>In genere, quando si applicano entrambi i tipi di filtri dati a un download, vengono scaricate solo le righe che corrispondono a entrambe le regole. Tuttavia, si applicano le seguenti eccezioni:<ul><li>Se Rows with empty column = All Columns (Righe con colonna vuota) = All Columns (Tutte le colonne), vengono controllate tutte le colonne ad eccezione di quella specificata nella prima regola per verificare che non siano vuote. Questa eccezione assicura che il sistema scarichi qualsiasi riga con una colonna corrispondente alla prima regola che ha anche tutte le altre colonne vuote.</li><li>Quando si scaricano righe di dati basate su colonne vuote, vengono controllate la presenza di vuoti in tutte le colonne, ad eccezione di quelle specificate nella prima regola.</li><li>Se viene specificata la stessa colonna per entrambe le regole di filtro (è quasi impossibile soddisfare entrambi i criteri) vengono scaricate solo le righe che corrispondono alla prima regola.</li></ul></ul> |
| Filtro dati | (Facoltativo) Filtra i dati per dati della campagna. Puoi scaricare i dati solo dalle campagne attive, oppure selezionare le campagne avviate (o terminate) in un intervallo di date specifico.<br>**Importante**: questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione. |
| Esporta numerico 2 | Puoi importare le classificazioni numeriche 2 nel sistema utilizzando l’importazione. Le classificazioni numeriche 2 sono utili per le variabili che cambiano nel tempo per elementi diversi, come i valori di costo e budget per il rapporto Canale di marketing. Per informazioni sul caricamento di dati utilizzando classificazioni numeriche 2, consulta Classificazioni numeriche 2. |
| Codifica | Selezionare la codifica dei caratteri per il file di dati. Il formato di codifica predefinito è UTF-8 o ISO-8859-1, in base alla codifica caricata per la classificazione. Da UTF-8 a UTF-16 converte le classificazioni con codifica UTF-8 in codifica UTF-16. ISO-8859-1 in UTF-16 converte le classificazioni con codifica ISO-8859-1 nella codifica UTF-16.<br>**Nota:** Se si sceglie di convertire in UTF-16, la codifica di origine deve corrispondere alla codifica del caricamento originale oppure è possibile ottenere risultati imprevisti. È consigliabile codificare tutti i file caricati in UTF-8 senza DBA. |
| Output preventivo | Specifica la versione 2.1 per il file di classificazione. Questa impostazione racchiude tra virgolette i caratteri speciali per garantire che le esportazioni funzionino in Excel quando è presente un’interruzione di riga nei valori di eVar. Per identificare se un file di classificazione è nella versione 2.1, apri il file scaricato. Vedrai la versione 2.1 nell’intestazione. Ad esempio: `## SC SiteCatalyst SAINT Import File v:2.1` |

## Esportare i dati di classificazione utilizzando il browser

1. Fai clic su [!UICONTROL Admin] > [!UICONTROL Classification Importer].
1. Fai clic sulla scheda [!UICONTROL Browser Export].
1. Specifica i dettagli del set di dati.
1. Fai clic su [!UICONTROL Export File].
1. Salva il set di dati nel sistema locale.
