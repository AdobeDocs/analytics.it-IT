---
title: Esportazione dei dati di classificazione tramite FTP
description: L’esportazione FTP offre maggiore flessibilità con i download dei set di dati, inclusi il download di dati da più suite di rapporti e il download di file di set di dati con dimensioni superiori a 50.000 righe di dati
source-git-commit: 32196fc76b2743679516a00f86c4912fac0bb3cf
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 1%

---


# Esportazione dei dati di classificazione tramite FTP

L’opzione FTP offre una maggiore flessibilità nel download dei set di dati, inclusa la possibilità di scaricare dati da più suite di rapporti e di scaricare file di set di dati con dimensioni superiori a 50.000 righe di dati. Prima di scaricare i dati di classificazione tramite FTP, crea un account FTP.

Quando applichi i filtri dati, considera i seguenti problemi:

* Puoi utilizzare i caratteri jolly durante la definizione del filtro dati. Utilizza un asterisco `*` per corrispondere a zero o più caratteri e un punto interrogativo `?` per corrispondere esattamente a un carattere. Utilizza `?*` per far corrispondere uno o più caratteri.
* In genere, quando si applicano entrambi i tipi di filtri dati a un download, vengono scaricate solo le righe corrispondenti a entrambe le regole. Tuttavia, si applicano le seguenti eccezioni:
   * Se Righe con colonna vuota = Tutte le colonne, tutte le colonne tranne la colonna specificata nella prima regola vengono controllate per verificare la presenza di vuoti. Questa eccezione assicura che lo strumento scarica qualsiasi riga con una colonna che corrisponde alla prima regola con tutte le altre colonne vuote.
   * Durante il download di righe di dati basate su colonne vuote, tutte le colonne eccetto quelle specificate nella prima regola vengono controllate se non si verificano problemi.
   * Se per entrambe le regole di filtro è specificata la stessa colonna (è quasi impossibile soddisfare entrambi i criteri), vengono scaricate solo le righe che corrispondono alla prima regola.
   * Le esportazioni FTP hanno un limite di 30 colonne.

## Esportare classificazioni tramite FTP

Questi passaggi descrivono come esportare (scaricare) le classificazioni da Adobe Analytics utilizzando l’FTP.

1. Crea un account FTP.
1. Vai a [!UICONTROL Admin] > [!UICONTROL Classification Importer].
1. Fai clic sulla scheda **[!UICONTROL FTP Import]**.
1. Configura i campi per l&#39;esportazione FTP.
1. Fai clic su **[!UICONTROL Export File]**.
1. Salva il set di dati nel sistema locale.

## Descrizioni dei campi

| Elemento | Descrizioni |
| --- | --- |
| [!UICONTROL Select Report Suite] | Seleziona la suite di rapporti da cui vuoi esportare i dati del rapporto. |
| [!UICONTROL Data Set to be classified] | Dal menu a discesa, seleziona il set di dati da classificare. |
| [!UICONTROL Select Number of Rows] | Specifica quante righe di dati esportare.<ul><li>Seleziona **[!UICONTROL All]** per scaricare tutti i dati del rapporto.</li><li>Seleziona **[!UICONTROL Limit Data Rows To]** se desideri specificare un numero specifico di righe da scaricare.</li></ul> |
| [!UICONTROL Filter by Date Received] | (Facoltativo) Filtrare i dati in base alla data di ricezione. Specifica l’intervallo di date per il quale vuoi scaricare i dati. |
| [!UICONTROL Apply Data Filter] | (Facoltativo) Filtrare il set di dati in base ai criteri di dati. Puoi filtrare il download per includere righe di dati che includono un valore specifico o righe di dati con valori di colonna (classificazione) non assegnati. |
| [!UICONTROL Date Filter] | (Facoltativo) Filtrare i dati in base ai dati della campagna. È possibile scaricare i dati solo da campagne attive o selezionare campagne che iniziano (o terminano) in un intervallo di date specifico. |
| [!UICONTROL Export Numeric 2] | Puoi importare le classificazioni numeriche 2 nel sistema utilizzando l’importazione. Le classificazioni numeriche 2 sono utili per le variabili che cambiano nel tempo per elementi diversi, ad esempio i valori di costo e budget per il rapporto Canale marketing. |
| [!UICONTROL FTP Account] | Specifica le informazioni sul server FTP in cui desideri che Adobe scarichi il file di dati, tra cui il nome host e la porta, il percorso della directory di destinazione, il nome utente e la password. |
| [!UICONTROL Notification] | Specifica l&#39;indirizzo e-mail per ricevere notifiche sul download FTP. |
| [!UICONTROL Encoding] | Selezionare la codifica dei caratteri per il file di dati. Il formato di codifica predefinito è UTF-8 o ISO-8859-1, in base alla codifica caricata per la classificazione. UTF-8 in UTF-16 converte le classificazioni codificate UTF-8 in codifica UTF-16. La codifica ISO-8859-1 in UTF-16 converte le classificazioni codificate ISO-8859-1 in codifica UTF-16.<br>**Nota:** se selezioni la conversione in UTF-16, la codifica sorgente deve corrispondere alla codifica del caricamento originale oppure puoi ottenere risultati imprevisti. È consigliabile codificare tutti i file caricati in UTF-8 senza BOM. |

