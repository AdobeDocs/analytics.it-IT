---
title: Risoluzione dei problemi di Importazione classificazioni
description: Problemi comuni di caricamento quando si utilizza Importazione classificazioni.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 0%

---


# Risoluzione dei problemi di Importazione classificazioni

I problemi più comuni durante il caricamento dei dati di classificazione  Adobe.

## Formato file o estensione non corretti

Le classificazioni richiedono un tipo e un formato di file specifici da caricare correttamente. Se salvato in modo non corretto, genera un errore e non elabora righe. L&#39;errore restituito è spesso *&quot;La prima colonna è obbligatoria per essere la chiave&quot;*, ma può essere un numero qualsiasi di errori. Verificate quanto segue:

* **Caricamento di un foglio di calcolo (.xlsx) invece di un file**.tab o .txt: Importazione classificazioni non sa come gestire i file .xls o .xlsx. Quando si trova nella finestra di dialogo Salva con nome in Excel, impostare il tipo di file Salva come corretto:
   * In Windows, utilizzate il formato file `Text (Tab delimited) (*.txt)`
   * In Mac, usate il formato file `Windows Formatted Text`.
* **Modifica dell’estensione del nome file dopo il salvataggio come cartella di lavoro**: Se si tenta di rinominare direttamente un&#39;estensione di file, viene generata una cartella di lavoro non valida. Utilizzate solo la funzione Salva con nome di Excel o modificate le classificazioni in un editor di testo come Blocco note++.
* **Utilizzo di estensioni** uppercase: Le estensioni maiuscole (come `fileupload.TXT`) non funzionano. Rinominare il file con un’estensione minuscola (`fileupload.txt`).
* **Codifica** caratteri non corrispondente: Accertatevi che la codifica del caricamento delle classificazioni salvato corrisponda alla codifica originale al momento del download del modello. Se caricate un file UTF-16 codificato originariamente in UTF-8, i caricamenti generano risultati imprevisti.  Adobe consiglia di caricare i file con UTF-8 senza indicatori di ordine dei byte.

## Contenuto file non valido

Se il file di caricamento è formattato correttamente, il caricatore tenta di importare il maggior numero possibile di righe valide. Alcuni problemi comuni con i dati di classificazione:

* **Righe già classificate**: Quando si tenta di caricare righe che sono già classificate con lo stesso valore, Importazione restituisce righe che non hanno avuto alcun effetto. Questo risultato è previsto, in quanto le classificazioni non riclassificano un valore chiave con la stessa classificazione. È una notifica invece di un errore. Non è nulla di cui preoccuparsi se non si modificano tutte le righe all&#39;interno di un file di esportazione.  Adobe consiglia di caricare solo le righe modificate.
* **L&#39;intestazione non corrisponde alla variabile caricata**: Se scaricate un modello di classificazione per la dimensione del codice di tracciamento e tentate di caricarlo in una classificazione  eVar, questo non riesce. Utilizzate solo i file di esportazione per le variabili specifiche da cui sono stati esportati.
* **Una chiave o un valore di classificazione contiene il valore 0**: Le classificazioni non possono distinguere il valore 0 da una cella vuota, pertanto non possono classificare tale valore. Consulta [Domande frequenti](../faq.md)sulle classificazioni.
* **Il file di classificazione contiene virgole o caratteri** speciali: Consulta [Domande frequenti](../faq.md)sulle classificazioni.
* **Schede supplementari nel file** caricato: Talvolta, quando si modificano i file di classificazione, è possibile inserire accidentalmente una scheda aggiuntiva. Ogni riga richiede un numero identico di schede da elaborare correttamente. Per verificare la presenza di schede aggiuntive all&#39;interno del file, evidenziate tutto il testo in un editor di testo normale e accertatevi che alla fine non vi siano righe con spazio aggiuntivo.
* **Nel file** sono presenti valori di chiave duplicati: Ogni valore chiave può avere una sola classificazione per colonna. Se tentate di classificare lo stesso valore più volte, Importazione genera un errore.
* **Le sottoclassificazioni esistono e non sono configurate** correttamente: Se esistono delle sottoclassificazioni, verificare quanto segue:
   * Tutti i valori delle sottoclassificazioni hanno un valore di classificazione padre
   * Nessuna due sottocategorie fa riferimento allo stesso valore di classificazione padre

## Risoluzione dei problemi relativi alle importazioni FTP

Di seguito sono illustrate le cause comuni dietro le classificazioni FTP che non elaborano i file caricati:

* **File**.fin mancante: Create un documento di testo vuoto sul desktop e rinominate l’estensione del nome di file da .txt a .fin. Il nome di questo file .fin deve corrispondere al nome del file di classificazione in questione. Ad esempio, se il nome del file FTP è `fileupload.tab`, assegnate al file .fin un nome `fileupload.fin`. Una volta caricato il file .fin, entrambi i file scompaiono.
* **Caricamento del file .fin prima del file** di classificazione: A volte viene creato un file .fin prima che il file di classificazione venga completato durante il caricamento sul sito FTP. L&#39;elaborazione può non riuscire quando i file vengono caricati fuori ordine. Rimuovete entrambi i file, aggiungete prima il file di classificazione, quindi il file .fin dopo il caricamento completo del file di classificazione.
* **Le dimensioni del file sono eccessive**:  Adobe raccomanda di mantenere il più possibile ridotte le dimensioni dei file di classificazione per garantire un&#39;elaborazione rapida.
* **File esistenti già in elaborazione**: Se più file vengono caricati per la stessa variabile e suite di rapporti, il vecchio file smette di elaborare a favore del nuovo. Se caricate le classificazioni utilizzando più file, attendete la conferma che i file esistenti abbiano terminato l&#39;elaborazione prima di caricarne di nuovi.
* **File caricati non inseriti nella directory** principale: I file caricati  sito FTP  Adobe devono essere inseriti nella directory principale. Se i file di importazione delle classificazioni vengono inseriti in sottocartelle, non vengono prelevati o elaborati.

In caso di problemi durante il caricamento di un file di classificazione, contatta  Assistenza clienti di Adobe.
