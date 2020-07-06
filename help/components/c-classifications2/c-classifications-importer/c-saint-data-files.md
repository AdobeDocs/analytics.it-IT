---
description: Importazione consente di caricare in massa i dati delle classificazioni nei rapporti di analisi in un file. L’importazione richiede un formato di file specifico per il caricamento dei dati.
subtopic: Classifications
title: File di dati di classificazione
topic: Admin tools
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1733'
ht-degree: 1%

---


# File di dati di classificazione

Importazione consente di caricare in massa i dati delle classificazioni nei rapporti di analisi in un file. L’importazione richiede un formato di file specifico per il caricamento dei dati.

Per facilitare la creazione di file di dati validi, è possibile scaricare un file modello che fornisce una struttura di file in cui è possibile incollare i dati delle classificazioni. Per ulteriori informazioni, consulta [Scaricare il modello](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md)di classificazione.

Per ulteriori informazioni sui limiti dei caratteri nelle classificazioni, vedere Struttura [](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) generale dei file.

Per informazioni sul caricamento di dati utilizzando classificazioni numeriche 2, vedere Classificazioni [](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md) numeriche2.

## Struttura generale dei file

Esempio di file di dati:

![](assets/completed-saint-file.png)

Un file di dati deve rispettare le seguenti regole di struttura:

* Le classificazioni non possono avere un valore pari a 0 (zero).
* Adobe consiglia di limitare il numero di colonne di importazione ed esportazione a 30.
* I file caricati devono utilizzare UTF-8 senza codifica caratteri BOM.
* All&#39;interno di una cella è possibile incorporare caratteri speciali, ad esempio tabulazioni, newline e virgolette, a condizione che sia specificato il formato di file v2.1 e che la cella sia correttamente [preceduta](/help/components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md)da una sequenza di escape. I caratteri speciali includono:

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   La virgola non è un carattere speciale.

* Le classificazioni non possono contenere un accento circonflesso (^) poiché questo carattere è utilizzato per indicare una sottocategoria.
* Prestare attenzione quando si utilizza un trattino. Ad esempio, se utilizzate un trattino (-) in un termine Social, Social riconosce il trattino come [!DNL Not] operatore (il segno meno). Ad esempio, se specificate *`fragrance-free`* come termine con l&#39;importazione, Social riconosce il termine come *`minus`* gratuito e raccoglie i post che ne parlano *`fragrance`*, ma non *`free`*.
* I limiti dei caratteri vengono applicati per classificare i dati del rapporto. Ad esempio, se caricate un file di testo delle classificazioni per i prodotti ( *`s.products`*) con nomi di prodotto superiori a 100 caratteri (byte), i prodotti non verranno visualizzati nei rapporti. I codici di tracciamento e tutte le variabili di conversione personalizzate (eVar) consentono 255 byte.
* File di dati delimitati da tabulazioni (create il file modello utilizzando un’applicazione per fogli di calcolo o un editor di testo).
* Un’estensione [!DNL .tab] o [!DNL .txt] file.
* Un simbolo cancelletto (#) identifica la riga come commento utente. Adobe ignora qualsiasi riga che inizia con #.
* Un segno a due libbre seguito da SC (## SC) identifica la riga come commento intestazione pre-elaborazione utilizzato dai report. Non eliminare queste righe.
* Le esportazioni di classificazione possono avere chiavi duplicate a causa di caratteri di nuova riga nella chiave. In un&#39;esportazione FTP o browser, questo può essere risolto attivando la citazione per l&#39;account FTP. Le virgolette racchiudono ciascuna chiave con caratteri di nuova riga.
* La cella C1 nella prima riga del file di importazione contiene un identificatore di versione che determina in che modo le classificazioni gestiscono l&#39;uso delle virgolette per tutto il resto del file.

   * v2.0 ignora le virgolette e presuppone che siano tutte parte delle chiavi e dei valori specificati. Ad esempio, considerare questo valore: &quot;Questo è &quot;&quot;un valore&quot;&quot;&quot;. v2.0 interpreterebbe letteralmente questo come: &quot;Questo è &quot;&quot;un valore&quot;&quot;&quot;.
   * v2.1 indica alle classificazioni di presumere che le virgolette facciano parte della formattazione del file utilizzata nei file Excel. Quindi v2.1 formatta l&#39;esempio precedente in modo che: Questo è &quot;un valore&quot;.
   * I problemi possono sorgere quando v2.1 è specificato nel file, ma ciò che è effettivamente desiderato è v2.0 - vale a dire, quando le virgolette sono utilizzate in modi che è illegale in Excel formattazione. Ad esempio, se disponete di un valore: Vestito S/l &quot;VP NO REPS&quot; con sovrapposizione. Con v2.1, si tratta di una formattazione errata (il valore deve essere racchiuso tra virgolette di apertura e chiusura e le virgolette che fanno parte del valore effettivo devono essere precedute da virgolette) e le classificazioni non funzioneranno oltre questo punto.
   * Effettuate una delle seguenti operazioni: modificate il formato di file in v2.0 modificando l&#39;intestazione (cella C1) nei file caricati, OPPURE implementate correttamente le virgolette Excel in tutti i file.

* La prima riga (senza commenti) del file di dati contiene le intestazioni di colonna utilizzate per identificare i dati di classificazione in quella colonna. Importazione richiede un formato specifico per le intestazioni di colonna. Per ulteriori informazioni, vedere Formato [intestazione](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)colonna.
* Immediatamente dopo la riga di intestazione in un file di dati sono riportate le righe di dati. Ogni riga di dati deve contenere un campo dati per ogni intestazione di colonna.
* Il file di dati supporta i seguenti codici di controllo, utilizzati da Adobe per fornire struttura al file, e importare correttamente i dati di classificazione:

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CODICE DI CONTROLLO </th> 
   <th colname="col2" class="entry"> DESCRIPTION </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;Nuovo grafico a linee&gt; </p> </td> 
   <td colname="col2"> <p>Un nuovo carattere di riga è l'unico delimitatore supportato tra righe/record di dati nel file di dati. In genere, è necessario inserire questi caratteri solo quando si scrive un programma per generare automaticamente i file di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>Richiede che Adobe generi automaticamente un ID univoco per questo elemento. </p> <p>Nel contesto della campagna, questo valore di controllo indica ad Adobe di assegnare un identificatore a ciascun elemento creativo. Vedere <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > Chiave </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Indica che la colonna di dati rappresenta l'intervallo di date associato all'elemento. Vedere <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > Data </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campo vuoto </p> </td> 
   <td colname="col2"> <p>Rappresenta un valore NULL per il campo corrente. Utilizzate questa opzione se una particolare colonna di dati non si applica al record corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER modificatori </p> </td> 
   <td colname="col2"> <p>Indica che la colonna di dati rappresenta un campo <span class="wintitle"> PER Modificatore </span> . Vedere <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > Per Intestazioni Modificatore </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Problemi comuni di caricamento](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)


## Formato intestazione colonna

>[!NOTE]
>
>Adobe consiglia di limitare il numero di colonne di importazione ed esportazione a 30.

I file di classificazione supportano le seguenti intestazioni di colonna:

### Chiave

Ogni valore deve essere univoco per l&#39;intero sistema. Il valore in questo campo corrisponde a un valore assegnato alla [!DNL Analytics] [!DNL JavaScript] variabile nel beacon del sito Web. I dati in questa colonna possono includere ~codice di tracciamento automatico~ o qualsiasi altro codice di tracciamento univoco.

### Intestazione colonna classificazione

Ad esempio, reporting e analisi includono automaticamente due classificazioni per [!UICONTROL Campaign] le variabili: [!UICONTROL Campaigns] e [!UICONTROL Creative Elements]. Per aggiungere dati alla [!UICONTROL Campaigns] classificazione, l&#39;intestazione della colonna nel file di dati della classificazione sarà [!UICONTROL Campaigns].

>[!NOTE]
>
>I valori nell&#39;intestazione della [!UICONTROL Classifications] colonna devono corrispondere esattamente alla convenzione di denominazione della classificazione, altrimenti l&#39;importazione non riesce. Ad esempio, se l&#39;amministratore cambia [!UICONTROL Campaigns] in [!UICONTROL Internal Campaign Names] nella [!UICONTROL Campaign Set-up Manager], l&#39;intestazione della colonna del file deve cambiare per corrispondere.

Inoltre, il file di dati supporta le seguenti convenzioni di intestazione aggiuntive per identificare sottocategorie e altre colonne di dati specializzate:

### Intestazione sottocategoria

Ad esempio, [!UICONTROL Campaigns^Owner] è un&#39;intestazione di colonna per la colonna contenente [!UICONTROL Campaign Owner] dei valori. Analogamente, [!UICONTROL Creative Elements^Size] è un&#39;intestazione di colonna per la colonna contenente la [!UICONTROL Size] sottoclassificazione della [!UICONTROL Creative Elements] classificazione.

### Intestazioni delle metriche di classificazione

Ad esempio, [!UICONTROL Campaigns^~Cost] si riferisce alla [!UICONTROL Cost] metrica nella [!UICONTROL Campaigns] classificazione.

### Intestazione del modificatore PER

*`Per Modifier`* Le intestazioni sono indicate aggiungendo *`~per`* all&#39;intestazione della metrica di classificazione. Ad esempio, se l’ *`Metric`* intestazione è *`Campaigns^~Cost`*, l’intestazione del modificatore PER è *`Campaigns^~Cost~per`*. Adobe supporta le seguenti *`PER Modifier`* parole chiave:

Questi caratteri hanno un significato speciale in un file di dati. Laddove possibile, evitare di usare queste parole nei nomi e nei dati degli attributi.

**RISOLTO:** Valore fisso. Non eseguite alcuna operazione di ridimensionamento.

**GIORNO:** Moltiplica il valore per il numero di giorni nel rapporto.

**ORDINE:** Moltiplica il valore per il numero di ordini per l&#39;elemento della riga nel rapporto.

**CHECKOUT:** Moltiplicare il valore per il numero di pagamenti per l&#39;elemento della riga nel rapporto.

**UNITÀ:** Moltiplica il valore per il numero di unità per l&#39;elemento della riga nel report.

**ENTRATE:** Moltiplica il valore per l&#39;importo delle entrate per l&#39;articolo della linea nel rapporto.

**SCADD:** Moltiplicare il valore per il numero di volte in cui l&#39; [!UICONTROL Shopping Cart Add] evento è stato chiamato per elemento del rapporto.

**SCREMOVE:** Moltiplicare il valore per il numero di volte in cui l&#39; [!UICONTROL Shopping Cart Remove] evento è stato chiamato per elemento del rapporto.

**ISTANZA:** Moltiplica il valore per il numero di istanze per l&#39;elemento della riga nel rapporto.

**FATE CLIC SU:** Moltiplica il valore per il numero di clic per l&#39;elemento della riga nel report.

**EVENTO:** Moltiplicare il valore per il numero di volte in cui si è verificato l&#39;evento personalizzato specificato per elemento riga del rapporto.

**Esempio:** Se Campaign A cost $10.000, la [!UICONTROL Campaigns^~Cost] colonna contiene un valore di 10000 e la colonna [!UICONTROL Campaigns^~~Costper] contiene [!UICONTROL FIXED]. Quando visualizzi il costo per la campagna A nei rapporti, vedrai $10.000 come costo fisso per la campagna A per l&#39;intervallo di date.

**Esempio:** Se la campagna B costa circa $ 2 per clic, la [!UICONTROL Campaigns^~Cost] colonna contiene 2 e la colonna **[!UICONTROL Campaigns^~~Costper]** contiene [!UICONTROL CLICK]. Quando nei rapporti viene visualizzato il costo per la campagna B, Adobe calcola al volo (2 * [numero di clic]) l&#39;intervallo di date del rapporto. Questo consente di calcolare il costo totale in base al numero di clic eseguiti con Campaign B.

### Data

Le date delle campagne sono in genere intervalli (date di inizio e di fine) associati a singole campagne. Le date devono essere visualizzate in formato AAAA/MM/GG. Ad esempio, 2013/06/15-2013/06/30.

Per ulteriori informazioni, vedere Classificazioni [](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html)conversione.

>[!NOTE]
>
>Nella versione di manutenzione del 10 maggio 2018 [!DNL Analytics] , Adobe ha iniziato a limitare le funzionalità delle classificazioni numeriche e abilitate per le date. Questi tipi di classificazione sono stati rimossi dalle interfacce Admin (Amministratore) e Classification Importer (Importazione classificazione). Non è possibile aggiungere nuove classificazioni numeriche e abilitate per le date. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti.

## Utilizzo di date in combinazione con [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL Classifications] può essere utilizzato per assegnare intervalli di date alle campagne o ad altre conversioni [!UICONTROL classifications]che consentono una misurazione più accurata delle campagne. Dopo aver specificato l&#39;intervallo di date di un valore, qualsiasi valore corrispondente che si verifica al di fuori dell&#39;intervallo di date non sarà classificato. Questo è utile per la misurazione della campagna che desidera utilizzare le date esatte in cui una campagna è stata live, e non tutti gli hit che corrispondono alla campagna stessa. Per classificare con successo un valore con un intervallo di date, è necessario soddisfare quanto segue:

* È [!UICONTROL classification] necessario basare l&#39;elemento su una variabile di conversione.
* L&#39; [!UICONTROL classification] utente utilizzato deve essere impostato come Data-Enabled o Numeric 2.
* L&#39;intervallo di date interessato deve contenere una data iniziale e (facoltativamente) una data finale.

Per classificare le campagne in base all&#39;intervallo di date:

1. Accedete a [!DNL Analytics] e andate ad Admin > Classifications (Classificazioni).
1. Fare clic sulla **[!UICONTROL Browser Export]** scheda, verificare che le impostazioni della classificazione abilitata per la data siano corrette, quindi fare clic su Esporta file.
1. Aprite questo file in Microsoft Excel o in un altro editor di fogli di calcolo che vi è familiare.
1. Una delle colonne termina con

   ^~periodo~corrispondente alla colonna in cui immettere l&#39;intervallo di date.
1. In questa colonna, immettere l&#39;intervallo di date di ciascun valore nel formato seguente:

   `YYYY/MM/DD - YYYY/MM/DD` (Progetto > scarica CSV). Verificate quanto segue:

   * Lasciare spazi su entrambi i lati del trattino.
   * Usate un trattino (-) per separare gli intervalli, non un trattino o un trattino lungo.
   * Se il mese o il giorno è una cifra singola, è presente uno zero iniziale.
   * Esiste un intervallo di date iniziale; l&#39;intervallo di date di fine è facoltativo.

1. Salvate il file e caricatelo [!DNL Analytics] da Admin | Classificazioni | Importa file.

>[!NOTE]
>
>Un valore chiave specifico non può avere più di un intervallo di date.

## Classificazioni per la risoluzione dei problemi

* [Problemi](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)comuni di caricamento: Articolo della Knowledge Base che descrive i problemi derivanti da formati di file e contenuti di file non corretti.

