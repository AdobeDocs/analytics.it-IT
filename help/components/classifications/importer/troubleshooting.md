---
title: Risoluzione di problemi dell’importazione di classificazioni
description: Problemi di caricamento comuni quando si utilizza l’importazione classificazioni.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 86%

---


# Risoluzione di problemi dell’importazione di classificazioni

I problemi più comuni durante il caricamento dei dati di classificazione in Adobe.

## Formato file o estensione non corretti

Le classificazioni richiedono un tipo e un formato di file specifici affinché il caricamento vada a buon fine. Se vengono salvate in modo scorretto, si genera un errore e le righe non vengono elaborate. L’errore restituito è spesso *“La prima colonna deve essere occupata dalla chiave”*, ma possono verificarsi anche errori diversi. Verifica quanto segue:

* **Caricamento di un foglio di calcolo (.xlsx) invece di un file**.tab o .txt: Potete visualizzare il messaggio di errore *&quot;La prima colonna deve essere la chiave&quot;* quando caricate i file di classificazione in un formato non corretto. Importazione classificazioni non sa come gestire i file .xls o .xlsx. Imposta il tipo di file corretto nella finestra di dialogo “Salva con nome” in Excel:
   * In Windows, utilizza il formato file `Text (Tab delimited) (*.txt)`
   * In Mac, utilizza il formato file `Windows Formatted Text`.
* **Modifica dell’estensione del nome file dopo averlo salvato come cartella di lavoro**: se provi a rinominare direttamente un’estensione di file, viene generata una cartella di lavoro non valida. Utilizza solo la funzione Salva con nome di Excel o modifica le classificazioni in un editor di testo come Notepad++.
* **Utilizzo di estensioni in maiuscolo**: le estensioni in maiuscolo (come `fileupload.TXT`) non funzionano. Rinomina il file con un’estensione in minuscolo (`fileupload.txt`).
* **Codifica caratteri non corrispondente**: accertati che la codifica del caricamento delle classificazioni salvate corrisponda alla codifica originale al momento del download del modello. Se carichi un file UTF-16 codificato originariamente in UTF-8, i caricamenti genereranno risultati imprevisti. Adobe consiglia di caricare i file utilizzando UTF-8 senza indicatori per l’ordine dei byte.

## Contenuto del file non valido

Se il file di caricamento è formattato correttamente, il caricatore tenta di importare il maggior numero possibile di righe valide. Alcuni problemi comuni relativi ai dati di classificazione:

* **Righe già classificate**: quando tenti di caricare righe già classificate con lo stesso valore, l’importazione restituisce righe che non hanno avuto alcun effetto. Questo risultato è previsto, in quanto le classificazioni non riclassificano un valore chiave con la stessa classificazione. È una notifica più che un errore. Non preoccuparti se non modifichi tutte le righe all’interno di un file di esportazione. Adobe consiglia di caricare solo le righe modificate.
* **L’intestazione non corrisponde alla variabile caricata**: se scarichi un modello di classificazione per la dimensione del codice di tracciamento e provi a caricarlo in una classificazione eVar, questo non riesce. Utilizza solo i file di esportazione per le variabili specifiche da cui sono stati esportati.
* **Una chiave o un valore di classificazione contiene il valore 0**: le classificazioni non sono in grado di distinguere il valore 0 da una cella vuota, pertanto non possono classificare tale valore. Consulta [Domande frequenti sulle classificazioni](../faq.md).
* **Il file di classificazione contiene virgole o caratteri speciali**: consulta [Domande frequenti sulle classificazioni](../faq.md).
* **Schede supplementari nel file caricato**: talvolta, quando si modificano i file di classificazione, può capitare di inserire accidentalmente una scheda in più. Ogni riga richiede un numero identico di schede per essere elaborata correttamente. Per verificare la presenza di schede supplementari all’interno del file, evidenzia tutto il testo in un editor di testo normale e accertati che non vi siano righe con spazio aggiuntivo alla fine.
* **Nel file sono presenti valori chiave duplicati**: ogni valore chiave può avere una sola classificazione per colonna. Se provi a classificare lo stesso valore più volte, l’importazione genera un errore.
* **Sono presenti sottoclassificazioni non configurate correttamente**. Se sono presenti sottoclassificazioni, verifica che:
   * Tutti i valori delle sottoclassificazioni abbiano un valore di classificazione padre
   * Due sottoclassificazioni non facciano riferimento allo stesso valore di classificazione padre
* **Colonna non corrispondente**: È possibile visualizzare il messaggio di errore *&quot;La chiave in linea contiene troppe colonne&quot;* se è presente un numero non valido di colonne in una riga specifica. Ad esempio, nel caricamento della classificazione sono presenti 3 colonne e la variabile dispone solo di una classificazione singola. Convalidate il file di caricamento per essere certi che il numero di colonne non sia maggiore del numero di classificazioni configurate per tale variabile.

## Risoluzione dei problemi relativi alle importazioni FTP

Di seguito sono illustrate le cause comuni per cui le classificazioni FTP non elaborano i file caricati:

* **File .fin mancante**: crea un documento di testo vuoto sul desktop e rinomina l’estensione del nome file da .txt a .fin. Il nome del file .fin deve corrispondere al nome del file di classificazione in questione. Ad esempio, se il nome del file FTP è `fileupload.tab`, rinomina il file .fin `fileupload.fin`. Una volta caricato il file .fin, entrambi i file scompaiono.
* **Caricamento del file .fin prima del file di classificazione**: a volte viene creato un file .fin prima che sia avvenuto il caricamento del file di classificazione sul sito FTP. L’elaborazione può non riuscire quando i file vengono caricati nell’ordine scorretto. Rimuovi entrambi i file, aggiungi prima il file di classificazione e poi, una volta completato il caricamento, aggiungi il file .fin.
* **Le dimensioni del file sono eccessive**: Adobe raccomanda di mantenere le dimensioni dei file di classificazione ridotte il più possibile per garantire la rapidità dell’elaborazione.
* **File esistenti già in elaborazione**: se più file vengono caricati per la stessa variabile e suite di rapporti, il file vecchio non viene più elaborato per dare precedenza al nuovo. Se carichi le classificazioni utilizzando più file, attendi la conferma che i file esistenti abbiano terminato l’elaborazione prima di caricarne di nuovi.
* **File caricati non inseriti nella directory radice**: i file caricati sul sito FTP Adobe devono essere inseriti nella directory radice. I file di importazione delle classificazioni, se inseriti in sottocartelle, non vengono prelevati o elaborati.

In caso di problemi durante il caricamento di un file di classificazione, contatta l’Assistenza clienti di Adobe.
