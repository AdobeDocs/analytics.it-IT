---
description: L’importazione consente di caricare in massa i dati delle classificazioni nei rapporti di Analytics in un file. L’importazione richiede un formato di file specifico per il caricamento dei dati.
subtopic: Classifications
title: File di dati di classificazione
feature: Strumenti di amministrazione
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1724'
ht-degree: 100%

---


# File di dati di classificazione

L’importazione consente di caricare in massa i dati delle classificazioni nei rapporti di Analytics in un file. L’importazione richiede un formato di file specifico per il caricamento dei dati.

Per facilitare la creazione di file di dati validi, puoi scaricare un file modello che ti fornisce una struttura in cui incollare i dati delle classificazioni. Per ulteriori informazioni, consulta [Scaricare il modello delle classificazioni](/help/components/classifications/importer/c-download-saint-data.md).

Per ulteriori informazioni sui limiti dei caratteri nelle classificazioni, consulta [Struttura generale dei file](/help/components/classifications/importer/c-saint-data-files.md).

## Struttura generale dei file

L’illustrazione seguente è un esempio di file di dati:

![](assets/completed-saint-file.png)

Un file di dati deve rispettare le seguenti regole di struttura:

* Le classificazioni non possono avere un valore pari a 0 (zero).
* Adobe consiglia di limitare a 30 il numero di colonne di importazione ed esportazione.
* I file caricati devono utilizzare la codifica dei caratteri UTF-8 senza BOM.
* È possibile incorporare caratteri speciali come tab, caratteri di nuova riga e virgolette all’interno di una cella a condizione che sia specificato il formato di file v2.1 e che la cella sia correttamente [preceduta da caratteri di escape](/help/components/classifications/importer/t-classifications-escape-data.md). I caratteri speciali includono:

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   La virgola non è un carattere speciale.

* Le classificazioni non possono contenere un accento circonflesso (^) poiché questo carattere è utilizzato per indicare una sottoclassificazione.
* Presta attenzione quando utilizzi i trattini. Ad esempio, se utilizzi un trattino (-) in un termine Social, Social riconosce il trattino come operatore [!DNL Not] (il segno meno). Ad esempio, se specifichi *`fragrance-free`* come termine con l’importazione, Social riconosce il termine come fragrance *`minus`* free e raccoglie i post che menzionano *`fragrance`* ma non *`free`*.
* I limiti di caratteri vengono applicati per classificare i dati dei rapporti. Ad esempio, se carichi un file di testo delle classificazioni per i prodotti (*`s.products`*) con nomi di prodotto che superano i 100 caratteri (byte), i prodotti non verranno visualizzati nei rapporti. I codici di tracciamento e tutte le variabili di conversione personalizzate (eVar) consentono 255 byte.
* File di dati delimitati da tabulazioni (crea il file modello utilizzando un’applicazione per fogli di calcolo o un editor di testo).
* Un’estensione file [!DNL .tab] o [!DNL .txt].
* Il cancelletto (#) identifica la riga come un commento degli utenti. Adobe ignora le righe che iniziano con #.
* Un doppio cancelletto seguito da SC (## SC) identifica la riga come un commento intestazione pre-elaborazione utilizzato nel reporting. Non eliminare queste righe.
* Le esportazioni delle classificazioni possono avere chiavi duplicate a causa di caratteri di nuova riga nella chiave. In un’esportazione FTP o browser, questo può essere risolto attivando le virgolette per l’account FTP. In questo modo ciascuna chiave con caratteri di nuova riga verrà inserita tra virgolette.
* La cella C1 nella prima riga del file di importazione contiene un identificatore di versione che determina il modo in cui le classificazioni gestiscono l’uso delle virgolette per la parte restante del file.

   * v2.0 ignora le virgolette e presuppone che siano parte delle chiavi e dei valori specificati. Ad esempio, considera questo valore: “Questo è ““un valore”””. v2.0 lo interpreterebbe letteralmente: “Questo è ““un valore”””.
   * v2.1 indica alle classificazioni di presumere che le virgolette siano parte della formattazione del file utilizzata nei file Excel. Quindi v2.1 formatta l’esempio precedente in questo modo: Questo è “un valore”.
   * Possono sorgere problemi quando v2.1 è specificato nel file, ma si desidera v2.0, ovvero quando le virgolette sono utilizzate in modi che non sono concessi nella formattazione Excel. Ad esempio, se disponi di un valore: “VP NO REPS” S/l Dress w/ Overlay. Con v2.1 questa viene considerata una formattazione errata (il valore deve essere racchiuso tra virgolette di apertura e chiusura e le virgolette che fanno parte del valore effettivo devono essere precedute da virgolette) e le classificazioni non funzioneranno oltre questo punto.
   * Effettua una delle seguenti operazioni: modifica il formato del file in v2.0 modificando l’intestazione (cella C1) nei file caricati, OPPURE implementa correttamente le virgolette Excel in tutti i file.

* La prima riga (senza commenti) del file di dati contiene le intestazioni di colonna utilizzate per identificare i dati di classificazione nella colonna. L’importazione richiede un formato specifico per le intestazioni di colonna. Per ulteriori informazioni, consulta [Formato delle intestazioni di colonna](/help/components/classifications/importer/c-saint-data-files.md).
* Dopo la riga di intestazione in un file di dati sono riportate le righe di dati. Ognuna di esse deve contenere un campo dati per ogni intestazione di colonna.
* Il file di dati supporta i seguenti codici di controllo utilizzati da Adobe per conferire struttura al file e importare correttamente i dati di classificazione:

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CODICE DI CONTROLLO </th> 
   <th colname="col2" class="entry"> DESCRIZIONE </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;Nuova riga&gt; </p> </td> 
   <td colname="col2"> <p>Il carattere di nuova riga è l’unico delimitatore tra righe/record di dati supportato nel file di dati. In genere, è necessario inserire questi caratteri solo quando si scrive un programma per generare automaticamente i file di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>Richiede che Adobe generi automaticamente un ID univoco per questo elemento. </p> <p>Nel contesto delle campagne, questo valore di controllo indica ad Adobe di assegnare un identificatore a ogni elemento creativo. Consulta <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Chiave</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~periodo~ </p> </td> 
   <td colname="col2"> <p>Indica che la colonna di dati rappresenta l’intervallo di date associato all’elemento. Consulta <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campo vuoto </p> </td> 
   <td colname="col2"> <p>Rappresenta un valore NULL per il campo corrente. Utilizzalo se una particolare colonna di dati non si applica al record corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificatori PER </p> </td> 
   <td colname="col2"> <p>Indica che la colonna di dati rappresenta un campo <span class="wintitle">modificatore PER</span>. Consulta <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Intestazioni dei modificatori PER</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Problemi comuni relativi al caricamento](https://helpx.adobe.com/it/analytics/kb/common-saint-upload-issues.html)


## Formato dell’intestazione di colonna

>[!NOTE]
>
>Adobe consiglia di limitare a 30 il numero di colonne di importazione ed esportazione.

I file di classificazione supportano le seguenti intestazioni di colonna:

### Chiave

Ogni valore deve essere univoco in tutto il sistema. Il valore in questo campo corrisponde a un valore assegnato alla variabile [!DNL Analytics] nel beacon [!DNL JavaScript] del sito web. I dati in questa colonna possono includere un codice di tracciamento ~autogen~ o qualsiasi altro codice di tracciamento univoco.

### Intestazione della colonna di classificazione

Ad esempio, Reports and Analytics include automaticamente due classificazioni per le variabili [!UICONTROL Campaign]: [!UICONTROL Campaigns] e [!UICONTROL Creative Elements]. Per aggiungere dati alla classificazione [!UICONTROL Campaigns], l’intestazione di colonna nel file di dati di classificazione sarà [!UICONTROL Campaigns].

>[!NOTE]
>
>I valori nell’intestazione della colonna [!UICONTROL Classifications] devono corrispondere esattamente alla convenzione di denominazione della classificazione, altrimenti l’importazione non riesce. Ad esempio, se l’amministratore modifica [!UICONTROL Campaigns] in [!UICONTROL Internal Campaign Names] nel [!UICONTROL Campaign Set-up Manager], l’intestazione della colonna del file dev’essere modificata di conseguenza.

Inoltre, il file di dati supporta le seguenti convenzioni di intestazione aggiuntive per identificare sottoclassificazioni e altre colonne di dati specializzate:

### Intestazione delle sottoclassificazioni

Ad esempio, [!UICONTROL Campaigns^Owner] è un’intestazione di colonna per la colonna contenente i valori [!UICONTROL Campaign Owner]. Allo stesso modo, [!UICONTROL Creative Elements^Size] è un’intestazione di colonna per la colonna contenente la sottoclassificazione [!UICONTROL Size] della classificazione [!UICONTROL Creative Elements].

### Intestazioni delle metriche di classificazione

Ad esempio, [!UICONTROL Campaigns^~Cost] si riferisce alla metrica [!UICONTROL Cost] nella classificazione [!UICONTROL Campaigns].

### Intestazione del modificatore PER

Le intestazioni del *`Per Modifier`* sono identificate tramite l’aggiunta di *`~per`* all’intestazione della metrica di classificazione. Ad esempio, se l’intestazione *`Metric`* è *`Campaigns^~Cost`*, l’intestazione del modificatore PER è *`Campaigns^~Cost~per`*. Adobe supporta le seguenti parole chiave per i *`PER Modifier`*:

Questi caratteri hanno un significato particolare in un file di dati. Laddove possibile, evita di usare queste parole nei nomi e nei dati degli attributi.

**FISSO:** valore fisso. Non eseguire operazioni di ridimensionamento.

**GIORNO:** moltiplica il valore per il numero di giorni nel rapporto.

**ORDINE:** moltiplica il valore per il numero di ordini per la riga nel rapporto.

**CHECKOUT:** moltiplica il valore per il numero di checkout per la riga nel rapporto.

**UNITÀ:** moltiplica il valore per il numero di unità per la riga nel rapporto.

**ENTRATE:** moltiplica il valore per l’importo delle entrate per la riga nel rapporto.

**SCADD:** moltiplica il valore per il numero di volte in cui l’evento [!UICONTROL Shopping Cart Add] è stato chiamato per riga del rapporto.

**SCREMOVE:** moltiplica il valore per il numero di volte in cui l’evento [!UICONTROL Shopping Cart Remove] è stato chiamato per riga del rapporto.

**ISTANZA:** moltiplica il valore per il numero di istanze per la riga nel rapporto.

**CLIC:** moltiplica il valore per il numero di clic per la riga nel report.

**EVENTO:** moltiplica il valore per il numero di volte in cui si è verificato l’evento personalizzato specificato per riga del rapporto.

**Esempio:** se la campagna A costa $ 10.000, la colonna [!UICONTROL Campaigns^~Cost] contiene il valore 10000 e la colonna [!UICONTROL Campaigns^~Cost~per] contiene [!UICONTROL FIXED]. Quando visualizzi il costo per la campagna A nei rapporti, vedrai $ 10.000 come costo fisso per la campagna A per l’intervallo di date.

**Esempio:** se la campagna B costa circa $ 2 per clic, la colonna [!UICONTROL Campaigns^~Cost] contiene il valore 2 e la colonna **[!UICONTROL Campaigns^~Cost~per]** contiene [!UICONTROL CLICK]. Quando nei rapporti viene visualizzato il costo per la campagna B, Adobe calcola in tempo reale (2 * [numero di clic]) per l’intervallo di date del rapporto. Questo consente di calcolare il costo totale in base al numero di clic eseguiti con la campagna B.

### Data

Le date delle campagne sono in genere intervalli (date di inizio e di fine) associati a singole campagne. Le date sono visualizzate in formato AAAA/MM/GG. Ad esempio, 2013/06/15-2013/06/30.

Per ulteriori informazioni, consulta [Classificazioni di conversione](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html).

>[!NOTE]
>
>Nella versione di manutenzione di [!DNL Analytics] del 10 maggio 2018, Adobe ha iniziato a limitare le funzionalità delle classificazioni numeriche e con data abilitata. Le classificazioni di questo tipo sono state rimosse dalle interfacce Admin e Importazione delle classificazioni. Non è possibile aggiungere nuove classificazioni numeriche e con data abilitata. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti.

## Utilizzo delle date in combinazione con le [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

Le [!UICONTROL Classifications], possono essere utilizzate per assegnare intervalli di date alle campagne o ad altre [!UICONTROL classifications] di conversione che consentono una misurazione più accurata delle campagne. Dopo aver specificato l’intervallo di date di un valore, qualsiasi valore corrispondente che si verifica al di fuori dell’intervallo di date non sarà classificato. Ciò consente di misurare le campagne utilizzando le date esatte in cui una campagna è stata attiva e non tutti gli hit che corrispondono alla campagna stessa. Per classificare un valore con un intervallo di date, è necessario soddisfare le condizioni seguenti:

* La [!UICONTROL classification] deve essere basata su una variabile di conversione.
* La [!UICONTROL classification] utilizzata deve essere impostata come numerica 2 o con data abilitata.
* L’intervallo di date interessato deve contenere una data di inizio e (facoltativamente) una data di fine.

Per classificare le campagne in base all’intervallo di date:

1. Accedi a [!DNL Analytics] e vai su Amministratore > Classificazioni.
1. Fai clic sulla scheda **[!UICONTROL Browser Export]**, verifica che le impostazioni della classificazione con data abilitata siano corrette e fai clic su Esporta file.
1. Apri il file in Microsoft Excel o nell’editor di fogli di calcolo che preferisci.
1. Una delle colonne termina con

   ^~periodo~, questa è la colonna in cui inserire l’intervallo di date.
1. In questa colonna, inserisci l’intervallo di date di ciascun valore nel formato seguente:

   `YYYY/MM/DD - YYYY/MM/DD`. Assicurati di effettuare le seguenti operazioni:

   * Lascia uno spazio prima e dopo il trattino.
   * Utilizza un trattino (-) per separare gli intervalli, non un trattino breve o un trattino lungo.
   * Se il mese o il giorno sono composti da una sola cifra, assicurati che sia presente uno zero iniziale.
   * Assicurati che sia presente un intervallo di date di inizio, l’intervallo di date di fine è facoltativo.

1. Salva il file e caricalo su [!DNL Analytics] da Amministratore | Classificazioni | Importa file.

>[!NOTE]
>
>Un valore chiave specifico non può avere più di un intervallo di date.

## Risoluzione di problemi relativi alle classificazioni

* [Problemi comuni relativi al caricamento](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html): articolo della knowledge base che descrive i problemi derivanti da formati e contenuti di file non corretti.

