---
description: Informazioni sui requisiti per la suite di rapporti prima dell'uso di Origini dati.
subtopic: Data sources
title: Requisiti e limiti di caricamento
topic-fix: Developer and implementation
uuid: d79fca77-fa0e-4171-b978-cdee5c67d9df
exl-id: 97a7cc65-f99a-4227-94f2-6f428ebdfad3
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 91%

---

# Requisiti e limiti di caricamento

Informazioni sui requisiti per la suite di rapporti prima dell&#39;uso di Origini dati.

Nelle sezioni seguenti sono elencati i limiti applicabili a Origini dati e ai dati importati nei reporting e analisi di marketing.

* [Limiti dimensione](/help/import/c-data-sources/datasrc-requirements.md#section_77B06D82CB374FFABD39F7D9A49D8E18)
* [Date](/help/import/c-data-sources/datasrc-requirements.md#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2)
* [Generale](/help/import/c-data-sources/datasrc-requirements.md#section_1CD337F660484ABDB7D8CAE96FF46ACF)
* [Supporto multibyte](/help/import/c-data-sources/datasrc-requirements.md#section_96C8D26B21184C3E839865DB6F23EA22)
* [Caricamento di file Registro web](/help/import/c-data-sources/datasrc-requirements.md#section_DD736FC971FE45C89AB310BEDC1FE707)

## Limiti dimensione {#section_77B06D82CB374FFABD39F7D9A49D8E18}

* Ogni account FTP è limitato a 50 MB di dati totali per tutti i file. L’elaborazione viene messa in pausa se la dimensione supera i 50 MB e non riprende finché il totale non è inferiore a 50 MB.

## Date {#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2}

* Ogni giorno di calendario puoi caricare dati per 90 date uniche. Se superi questo limite, il caricamento non riuscirà con un messaggio di errore che indica che hai superato i giorni univoci massimi.
* È possibile importare solo i dati con date correnti o passate. Non tentare di utilizzare date future nei dati di Origini dati.
* È necessario specificare una data per tutte le righe per abilitare le funzionalità di grafici di rapporti. Se una riga non include una data, Origini dati genera un errore e rifiuta il file. Il formato di data/ora varia in base al tipo di origine di dati:

   * **Origini** dati di elaborazione completa: Utilizza il formato di data ISO 8601 di  `YYYY-MM-DDThh:mm:ss±UTC_offset` (ad esempio,  `2013-09-01T12:00:00-07:00`) o Unix Time Format (il numero di secondi trascorsi dal 1° gennaio 1970).

   * **Origini dati standard e di integrazione**: Utilizza il formato data seguente:  `MM/DD/YYYY/HH/mm/SS` (ad esempio,  `01/01/2013/06/00/00`)

## Generale {#section_1CD337F660484ABDB7D8CAE96FF46ACF}

* Quando carichi un file Origini dati, Origini dati esegue una convalida dei dati base per verificare che il file non contenga errori di formattazione. Se viene rilevato un errore in un file, viene inviata una notifica e-mail e l&#39;elaborazione si interrompe.
* I campi di dati non possono contenere punti e virgole. Origini dati ignora i record che contengono un punto e virgola.
* I dati da Registro web, Traffico e alcuni raggruppamenti Origini dati generici non sono disponibili in Data Warehouse o Discover. Per ulteriori informazioni, consulta [Tipi di dati e categorie](/help/import/c-data-sources/c-datasrc-types/datasrc-categories.md).
* Origini dati non supporta eventi serializzati.

## Supporto multibyte {#section_96C8D26B21184C3E839865DB6F23EA22}

Origini dati supporta la codifica multibyte. Origini dati tenta di rilevare il formato del file Origini dati in entrata e, laddove necessario, lo converte in un formato supportato. Nella tabella seguente sono elencati i formati di caratteri comuni e il relativo stato di supporto.

<table id="table_F9E685D7EEAB49A9ABAD622AE630EC21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato carattere </th> 
   <th colname="col2" class="entry"> Supporto </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> UTF-8 </td> 
   <td colname="col2"> <p>Supportati. La suite di rapporti utilizzata con Origini dati deve avere il supporto caratteri multibyte abilitato. </p> <p>Consulta <a href="https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html"  >Nuova suite di rapporti</a> in Aiuto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-8 con indicatore ordine byte (EF BB BF) </td> 
   <td colname="col2"> <p>Supportati. Questo formato non è standard, anche se molte applicazioni Windows salvano in questo formato. </p> <p>Ad esempio, WordPad salva in questo formato se si sceglie "UTF-8". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ISO-8859-1 (Latin-1 o Windows-1252) </td> 
   <td colname="col2"> Supportati. Microsoft Excel salva in questo formato quando si sceglie un'esportazione con valori delimitati da tabulazioni. La suite di rapporti deve utilizzare ISO-8859-1 locale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Little-endian, con indicatore ordine byte (FF FE) </td> 
   <td colname="col2"> Convertito in ISO-8859-1 o UTF-8, come determinato dalla configurazione della suite di rapporti. Microsoft Excel salva in questo formato quando si sceglie un'esportazione Unicode. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Big-endian, con indicatore ordine byte (EF FF) </td> 
   <td colname="col2"> Convertito in ISO-8859-1 o UTF-8, come determinato dalla configurazione della suite di rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 senza indicatore ordine byte </td> 
   <td colname="col2"> Non supportati. </td> 
  </tr> 
 </tbody> 
</table>

Se invii un file UTF-8 o ISO-8859-1 e la suite di rapporti non è configurata per supportarlo, si verifica una delle situazioni seguenti:

* L&#39;errore viene rilevato durante la conversione, in tal caso ricevi un messaggio come &quot;Trovato carattere errato nel file in posizione 18 durante la conversione da UTF-8 a ISO-8859-1&quot;.
* Il file viene elaborato senza errori, ma nel rapporto saranno visualizzati dati illeggibili.

## Caricamento di file Registro web {#section_DD736FC971FE45C89AB310BEDC1FE707}

* I rapporti più utili per visualizzare i dati Registro web sono i rapporti del traffico, come le visualizzazioni pagina.
* I nomi delle pagine sono visualizzati come URL completo, inclusa la stringa di query.
* Ogni richiesta di file è visualizzata come visualizzazione pagina separata, che include i fogli di stile e i file di immagine.
* Se aggiungi informazioni all&#39;URL, i file potrebbero essere registrati come pagine separate. Ad esempio, Adobe registra i seguenti URL come due pagine separate:

`/jokes/misc/snail_joke.html?userid=12345`

`/jokes/misc/snail_joke.html?userid=98765`
