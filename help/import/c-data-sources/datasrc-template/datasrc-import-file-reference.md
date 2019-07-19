---
description: Informazioni sul modello .txt Origine dati.
seo-description: Informazioni sul modello .txt Origine dati.
seo-title: Riferimento file di importazione
solution: Analytics
subtopic: Origini dati
title: Riferimento file di importazione
topic: Sviluppatore e implementazione
uuid: cc 58 f 8 d 8-cb 6 e -4908-846 f -0 a 41 c 6 da 805 d
translation-type: tm+mt
source-git-commit: cce2c1c54f21244f856385aeaad811d89f2fda7f

---


# Riferimento file di importazione

Informazioni sul modello .txt Origine dati.

Utilizza la procedura guidata Origini dati per generare un modello di importazione. Il file di importazione Origini dati include i dati seguenti:

* Un simbolo cancelletto (#) identifica la riga come commento.
* Puoi aggiungere altri commenti al file, in base alle necessità.
* Un commento che elenca il titolo del file modello.
* A comment that lists the external metric and data dimension names specified in the [!UICONTROL Data Source Activation Wizard].

Le intestazioni colonna vengono utilizzate per identificare i dati in ogni colonna del file Origine dati. Esistono tre tipi di intestazioni colonna:

**Data**: (Obbligatorio) una marca temporale per ogni riga di dati nel file.

**Variabili**: i nomi delle variabili di reporting mappate alle dimensioni dati dell'origine dati.

**Eventi**: i nomi degli eventi mappati alle metriche dell'origine dati.

Usa il modello Origine dati per creare un file Origini dati che contiene i dati da caricare. Quando crei un file Origini dati, ricorda quanto segue:

* Di fatto, ogni riga nel file Origini dati contiene un record di dati, in cui ogni record è costituito da una serie di campi separati da tabulazioni. Le intestazioni colonna nel modello Origine dati definiscono l'ordine dei campi. Ad esempio:

   ```
     #Sample data file for mycorp_report_suite 
     #Imported data for ad impressions applied to Event 6
     Date     Tracking Code      Event 6 
     1/1/2009     NYT8453A      8754
     1/1/2009     WSJ4453B      9492
     1/1/2009     BHG44563      10553
     1/2/2009     NYT8453A      6452
     1/2/2009     WSJ4453B      7237
     1/2/2009     BHG44563      9031
   ```

* Se carichi più file di dati, Origini dati li carica in ordine alfabetico. I file da elaborare in ordine cronologico devono essere denominati in modo che l'ordine alfabetico corrisponda all'ordine cronologico. Ad esempio:

   ```
   log_2009-01-01_13:00.txt
   log_2009-01-01_13:15.txt
   log_2009-01-01_13:30.txt
   ```

* Per velocizzare l'elaborazione del file Origini dati, Adobe consiglia di aggregare dati di eventi (metriche) in una sola riga per data.

   Ad esempio, se il file Origini dati mappa dati ad impression all'Evento 6, crea una singola riga di dati che include il numero totale di ad impression per ogni giorno, invece di creare una riga di dati separata per ogni ad impression che si verifica in un giorno specifico.
* Se devi caricare dati da date antecedenti alla data di creazione della suite di rapporti, contatta l'account manager per modificare la data più remota per cui puoi eseguire i rapporti.

**File .FIN**

Quando hai terminato di compilare il file Origine dati, puoi inviarlo FTP in Analytics. Tuttavia, è necessario un file aggiuntivo per l'elaborazione dei dati. You will need to upload an empty text file with the same name of your data file, but with a [!DNL .fin] extension.

For example, if you upload a (tab-delimited) data file called [!DNL myproductdata.txt], you would also need to upload an empty text file called [!DNL myproductdata.fin]. Without the [!DNL .fin] file, data would never be processed.
