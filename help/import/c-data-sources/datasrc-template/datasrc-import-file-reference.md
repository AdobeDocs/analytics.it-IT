---
description: Informazioni sul modello .txt Origine dati.
subtopic: Data sources
title: Riferimento file di importazione
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 7966b156-04bf-4d39-a720-ab47a665d1e2
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 64%

---

# Riferimento file di importazione

Informazioni sul modello .txt Origine dati.

Utilizza la procedura guidata Origini dati per generare un modello di importazione. Il file di importazione Origini dati include i dati seguenti:

* Un simbolo cancelletto (#) identifica la riga come commento.
* Puoi aggiungere altri commenti al file, in base alle necessità.
* Un commento che elenca il titolo del file modello.
* Un commento che elenca i nomi delle metriche esterne e delle dimensioni dati specificati nel [!UICONTROL Data Source Activation Wizard].

Le intestazioni colonna vengono utilizzate per identificare i dati in ogni colonna del file Origine dati. Esistono tre tipi di intestazioni colonna:

**Data**: (Obbligatorio) un timestamp per ogni riga di dati nel file, nel formato `m/d/yyyy`.

**Variabili**: nomi delle variabili di reporting mappate alle dimensioni dati dell’origine dati.

**Eventi**: nomi degli eventi mappati alle metriche dell’origine dati.

Usa il modello Origine dati per creare un file Origini dati che contiene i dati da caricare. Quando crei un file Origini dati, ricorda quanto segue:

* Di fatto, ogni riga nel file Origini dati contiene un record di dati, in cui ogni record è costituito da una serie di campi separati da tabulazioni. Le intestazioni colonna nel modello Origine dati definiscono l&#39;ordine dei campi. Ad esempio:

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

* Se carichi più file di dati, Origini dati li carica in ordine alfabetico. I file da elaborare in ordine cronologico devono essere denominati in modo che l&#39;ordine alfabetico corrisponda all&#39;ordine cronologico. Ad esempio:

   ```
   log_2009-01-01_13:00.txt
   log_2009-01-01_13:15.txt
   log_2009-01-01_13:30.txt
   ```

* Per velocizzare l&#39;elaborazione del file Origini dati, Adobe consiglia di aggregare dati di eventi (metriche) in una sola riga per data.

   Ad esempio, se il file Origini dati mappa dati ad impression all&#39;Evento 6, crea una singola riga di dati che include il numero totale di ad impression per ogni giorno, invece di creare una riga di dati separata per ogni ad impression che si verifica in un giorno specifico.
* Se devi caricare dati da date precedenti alla data di creazione della suite di rapporti, contatta il team dell’account Adobe per modificare la data meno recente per la quale puoi eseguire i rapporti.

**File .FIN**

Una volta completato il file Origine dati, puoi inviarlo ad Analytics tramite FTP. Tuttavia, è necessario un file aggiuntivo per l&#39;elaborazione dei dati. Dovrai caricare un file di testo vuoto con lo stesso nome del file di dati, ma con [!DNL .fin] estensione.

Ad esempio, se carichi un file di dati (delimitato da tabulazioni) denominato [!DNL myproductdata.txt], sarà inoltre necessario caricare un file di testo vuoto denominato [!DNL myproductdata.fin]. Senza [!DNL .fin] file, i dati non verranno mai elaborati.
