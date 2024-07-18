---
title: Esportazione dei dati di classificazione tramite FTP
description: L’esportazione FTP offre maggiore flessibilità con i download dei set di dati, tra cui il download di dati da più suite di rapporti e il download di file di set di dati di dimensioni superiori a 50.000 righe di dati
feature: Classifications
exl-id: 6f97f0b2-1a04-407f-9df9-8715da52037d
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 1%

---

# Esportazione dei dati di classificazione tramite FTP

L’opzione FTP offre maggiore flessibilità nel download dei set di dati, inclusa la possibilità di scaricare dati da più suite di rapporti e file di set di dati con dimensioni superiori a 50.000 righe di dati. Prima di scaricare i dati di classificazione tramite FTP, crea un account FTP.

Quando applichi i filtri dati, considera i seguenti problemi:

* È possibile utilizzare caratteri jolly durante la definizione del filtro dati. Utilizzare un asterisco `*` per far corrispondere zero o più caratteri e un punto interrogativo `?` per far corrispondere esattamente un carattere. Utilizza `?*` per trovare uno o più caratteri.
* In genere, quando si applicano entrambi i tipi di filtri dati a un download, vengono scaricate solo le righe che corrispondono a entrambe le regole. Tuttavia, si applicano le seguenti eccezioni:
   * Se Rows with empty column = All Columns (Righe con colonna vuota) = All Columns (Tutte le colonne), vengono controllate tutte le colonne ad eccezione di quella specificata nella prima regola per verificare che non siano vuote. Questa eccezione assicura che lo strumento scarichi qualsiasi riga con una colonna corrispondente alla prima regola che ha anche tutte le altre colonne vuote.
   * Quando si scaricano righe di dati basate su colonne vuote, vengono controllate la presenza di vuoti in tutte le colonne, ad eccezione di quelle specificate nella prima regola.
   * Se viene specificata la stessa colonna per entrambe le regole di filtro (è quasi impossibile soddisfare entrambi i criteri) vengono scaricate solo le righe che corrispondono alla prima regola.
   * Le esportazioni FTP hanno un limite di 30 colonne.

## Esportare le classificazioni tramite FTP

Questi passaggi descrivono come esportare (scaricare) le classificazioni da Adobe Analytics utilizzando l’FTP.

1. Crea un account FTP.
1. Passa a [!UICONTROL Admin] > [!UICONTROL Classification Importer].
1. Fai clic sulla scheda **[!UICONTROL FTP Import]**.
1. Configura i campi per l&#39;esportazione FTP.
1. Fai clic su **[!UICONTROL Export File]**.
1. Salva il set di dati nel sistema locale.

## Descrizioni dei campi

| Elemento | Descrizioni |
| --- | --- |
| [!UICONTROL Select Report Suite] | Seleziona la suite di rapporti da cui desideri esportare i dati del rapporto. |
| [!UICONTROL Data Set to be classified] | Dal menu a discesa, seleziona il set di dati da classificare. |
| [!UICONTROL Select Number of Rows] | Specifica quante righe di dati esportare.<ul><li>Selezionare **[!UICONTROL All]** per scaricare tutti i dati del report.</li><li>Selezionare **[!UICONTROL Limit Data Rows To]** se si desidera specificare un numero specifico di righe da scaricare.</li></ul> |
| [!UICONTROL Filter by Date Received] | (Facoltativo) Filtra i dati in base alla data di ricezione. Specifica l’intervallo di date per il quale desideri scaricare i dati. |
| [!UICONTROL Apply Data Filter] | (Facoltativo) Filtra il set di dati in base a criteri di dati. Puoi filtrare il download per includere righe di dati che includono un valore specifico o righe di dati con valori di colonna (classificazione) non assegnati. |
| [!UICONTROL Date Filter] | (Facoltativo) Filtra i dati in base ai dati della campagna.Puoi scaricare i dati solo dalle campagne attive o selezionare le campagne che iniziano (o terminano) in un intervallo di date specifico. |
| [!UICONTROL Export Numeric 2] | Puoi importare le classificazioni numeriche 2 nel sistema utilizzando l’importazione. Le classificazioni numeriche 2 sono utili per le variabili che cambiano nel tempo per elementi diversi, come i valori di costo e budget per il rapporto Canale di marketing. |
| [!UICONTROL FTP Account] | Specifica le informazioni sul server FTP in cui vuoi che Adobe scarichi il file di dati, tra cui nome host e porta, percorso della directory di destinazione, nome utente e password. |
| [!UICONTROL Notification] | Specifica l&#39;indirizzo e-mail per ricevere notifiche sul download FTP. |
| [!UICONTROL Encoding] | Selezionare la codifica dei caratteri per il file di dati. Il formato di codifica predefinito è UTF-8 o ISO-8859-1, in base alla codifica caricata per la classificazione. Da UTF-8 a UTF-16 converte le classificazioni con codifica UTF-8 in codifica UTF-16. Le classificazioni codificate ISO-8859-1 in UTF-16 convertono le classificazioni codificate ISO-8859-1 nella codifica UTF-16.<br>**Nota:** se si sceglie di convertire in UTF-16, la codifica di origine deve corrispondere alla codifica del caricamento originale oppure è possibile ottenere risultati imprevisti. È consigliabile codificare tutti i file caricati in UTF-8 senza DBA. |
