---
description: Selezionando l'icona a forma di ingranaggio accanto a una metrica è possibile specificare il tipo di metrica e il modello di attribuzione.
title: Tipo di metrica e attribuzione
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# Tipo di metrica e attribuzione

Selezionando l&#39;icona a forma di ingranaggio accanto a una metrica è possibile specificare il tipo di metrica e il modello di attribuzione.

* [Tipo di metrica](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [Modello di attribuzione colonna](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [Come funziona l&#39;allocazione lineare (dal 19 luglio 2018)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## Tipo di metrica {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| Tipo di metrica | Definizione |
|---|---|
| Standard | Queste metriche sono le stesse utilizzate per il [!DNL Analytics] reporting standard. Se una formula è costituita da una singola metrica standard, vengono visualizzati dati identici a quelli della corrispondente metrica non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singolo elemento riga. Ad esempio, [Ordini] / [Visite] riceve gli ordini per quell&#39;articolo specifico e lo divide per il numero di visite per quell&#39;articolo specifico. |
| Totale | Utilizzare il totale per il periodo di reporting in ogni voce di riga. Se una formula è costituita da una singola metrica totale, visualizza lo stesso numero totale su ogni elemento riga. Le metriche totali sono utili per creare metriche calcolate confrontate con i dati totali del sito. Ad esempio, [Ordini] / Visite [] totali mostra la proporzione di ordini rispetto a TUTTE le visite al sito, non solo le visite all&#39;elemento riga specifico. |

## Modello di attribuzione colonna {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>Nel luglio 2018, [!DNL Analytics] è stato introdotto [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), che ha modificato il modo in cui vengono valutati i modelli di allocazione nelle metriche calcolate. Come parte di questa modifica, le metriche calcolate che utilizzano un modello di allocazione non predefinito sono state migrate in nuovi modelli di attribuzione migliorati:
>
>* Per un elenco completo dei modelli di attribuzione e delle finestre di lookback non predefiniti supportati, consultate la documentazione di [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html) .
>* I modelli di allocazione &quot;Marketing Channel Last Touch&quot; e &quot;Marketing Channel First Touch&quot; verranno migrati rispettivamente ai nuovi modelli di attribuzione &quot;Last Touch&quot; e &quot;First Touch&quot; (Nota: &quot;Marketing Channels&quot; (Canali di marketing) non verrà dichiarato obsoleto; verranno visualizzati solo i due modelli di allocazione nelle metriche calcolate.
>* Inoltre, correggeremo il modo in cui viene calcolata l&#39;allocazione lineare. Per i clienti che utilizzano metriche calcolate con modelli di allocazione &quot;Lineare&quot;, i report potrebbero subire lievi modifiche per riflettere il nuovo modello di attribuzione corretto. La modifica alle metriche calcolate si rifletterà in Analysis Workspace, Reports &amp; Analytics, Reporting API, Report Builder e Ad Hoc Analysis. Per ulteriori informazioni, vedere **Funzionamento dell&#39;allocazione lineare (dal 19 luglio 2018**, di seguito).
>



## Come funziona l&#39;allocazione lineare (dal 19 luglio 2018)

Nel luglio 2018, Adobe ha modificato il modo in cui viene riportata l&#39;allocazione lineare per le metriche calcolate. Questa modifica interessa Analysis Workspace, Analisi ad hoc, Reporting e analisi, Generatore di report, Activity Map e le API di reporting. La modifica interesserà principalmente le eVar e altre dimensioni con persistenza. Si noti che queste modifiche saranno applicate solo alle metriche calcolate e non avranno alcun impatto sugli altri report che utilizzano l&#39;allocazione lineare (come il report Pagine in Reporting e analisi). Altri rapporti che utilizzano l&#39;allocazione lineare continueranno a utilizzare il metodo esistente di allocazione lineare.

L&#39;esempio seguente illustra come le metriche calcolate con allocazione lineare cambieranno nei report:

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Hit 1 </th> 
   <th colname="col3" class="entry"> Hit 2 </th> 
   <th colname="col4" class="entry"> Hit 3 </th> 
   <th colname="col5" class="entry"> Hit 4 </th> 
   <th colname="col6" class="entry"> Hit 5 </th> 
   <th colname="col7" class="entry"> Hit 6 </th> 
   <th colname="col8" class="entry"> Hit 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dati inviati in </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ultima eVar tocco </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> PROMO B </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>First Touch eVar </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO A </td> 
   <td colname="col6"> PROMO A </td> 
   <td colname="col7"> PROMO A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esempio di proprietà </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

In questo esempio, i valori A, B e C sono stati inviati in una variabile sugli hit 1, 3, 4 e 6 prima che un acquisto di $10 fosse effettuato sull&#39;hit 7. Nella seconda riga, questi valori persistono tra gli hit in base all’ultima visita di tocco. La terza riga illustra una persistenza della visita di primo tocco. Infine, l&#39;ultima riga illustra come i dati verrebbero registrati per una prop che non ha persistenza.

## Funzionamento dell&#39;allocazione lineare prima di luglio 2018

Prima del 19 luglio 2018, l&#39;attribuzione lineare è stata calcolata dopo che si è già verificata la persistenza del primo tocco o dell&#39;ultimo tocco. Ciò significa che per l&#39;ultima eVar touch sopra, i $10 sarebbero distribuiti come segue: A = 10 * (3/6) = $5, B = 10 * (2/6) = $3,33, C = 10 * (1/6) = $1,67.

Per la prima eVar touch sopra, tutti $10 sarebbe dato a A. Per il prop: A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50, e C = 10 * (1/4) = $2,50. Per riepilogare l&#39;allocazione lineare come funzionava in precedenza:

| Valori | Ultima eVar di tocco corrente | Prima eVar touch corrente | Prop corrente |
|---|---|---|---|
| PROMO A | $5.00 | $10.00 | $5.00 |
| PROMO B | $3.33 | $0 | $2.50 |
| PROMO C | $1.67 | $0 | $2.50 |
| Totale | $10.00 | $10.00 | $10.00 |

**Riepilogo del funzionamento dell’allocazione lineare a partire dal 19 luglio 2018**

Dopo il 19 luglio, abbiamo corretto questo comportamento nelle metriche calcolate. Invece di utilizzare i valori persistenti basati sull&#39;ultimo tocco o sul primo tocco, [!DNL Analytics] ora utilizza solo i valori passati (la prima riga della tabella superiore). Di conseguenza, le impostazioni di allocazione delle dimensioni non influiscono più sul modo in cui viene calcolata l&#39;allocazione lineare (vale a dire proprietà e eVar saranno trattate allo stesso modo), e i risultati riflettono ciò che è stato originariamente passato al posto dei valori del primo o dell&#39;ultimo tocco che potrebbero essere persistenti. Quindi, in tutti e tre i casi, A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50, e C = 10 * (1/4) = $2,50.

| Valori | Nuova eVar ultimo tocco | Nuova prima eVar touch | Nuovo prop |
|---|---|---|---|
| PROMO A | $5.00 | $5.00 | $5.00 |
| PROMO B | $2.50 | $2.50 | $2.50 |
| PROMO C | $2.50 | $2.50 | $2.50 |
| Totale | $10.00 | $10.00 | $10.00 |

