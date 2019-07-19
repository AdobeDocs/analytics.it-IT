---
description: Adobe Analytics offre diverse metriche e dimensioni dedicate al tempo. Scopri cosa sono e come vengono calcolati.
seo-description: Adobe Analytics offre diverse metriche e dimensioni dedicate al tempo. Scopri cosa sono e come vengono calcolati.
seo-title: Durata
solution: Analytics
title: Durata
topic: Metrics (Metriche)
uuid: a 9 f 63 da 3-7 e 79-49 c 3-9 b 0 b -6 dcd 2 ae 6 aadc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Durata

Adobe Analytics offre diverse metriche e dimensioni dedicate al tempo. Scopri cosa sono e come vengono calcolati.

* [Metriche dedicate](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_4F54D70300944748A62088F5870E4B6C)
* [Tempo trascorso nelle dimensioni](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_D51606544CB046FC902E2E317318892C)
* [Calcolo del tempo trascorso](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_90A3882638974969A4B8B674FFDB7624)
* [Domande frequenti sul tempo trascorso](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_51C2735BACAB42CCBA1DD3CBF238E2F7)
* [Esempi di calcolo](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_3D63D6A601F34E42AD5366435CB610D5)

## Time Spent Metrics {#section_4F54D70300944748A62088F5870E4B6C}

In questa tabella sono elencate le diverse metriche Tempo trascorso, la relativa definizione e dove è possibile utilizzarli in Adobe Analytics.

<table id="table_7095406DF1614F3CAD5E437B919598D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Definizione </th> 
   <th colname="col3" class="entry"> Disponibile in </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Secondi totali trascorsi </p> </td> 
   <td colname="col2"> <p>Rappresenta la quantità totale di visitatori che interagiscono con un elemento dimensione specifico. </p> <p>Include l'istanza di un valore e persistenza in tutti gli hit successivi. Nel caso dei prop, anche il tempo trascorso viene conteggiato negli eventi di collegamento successivi. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> <p>Generatore di report (denominatò tempo totale trascorso ') </p> <p>Data Warehouse </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso per visita (secondi) </p> </td> 
   <td colname="col2"> <p><i>Secondi totali trascorsi/(boun@-@ bounances)</i> </p> <p>Rappresenta la quantità media di visitatori che interagiscono con un elemento dimensione specifico durante ogni visita. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso per visitatore (secondi) </p> </td> 
   <td colname="col2"> <p><i>Secondi totali trascorsi/(visitatore univoco - visitatori univoci)</i> </p> <p>Rappresenta la quantità media di visitatori che interagiscono con un elemento dimensione specifico per tutta la durata del visitatore (lunghezza del cookie). </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo medio trascorso sul sito (secondi) </p> </td> 
   <td colname="col2"> <p>Rappresenta la quantità totale di visitatori che interagiscono con un elemento dimensione specifico, per sequenza con un elemento della dimensione. Non è solo limitato alle medie «del sito», come suggerito dal nome. Consulta La sezione Tempo trascorso per ulteriori informazioni sulle sequenze. </p> <p>Nota: Questa metrica sarà molto probabilmente diversa da Tempo trascorso per visita a livello di elemento dimensione a causa delle differenze nel denominatore nel calcolo. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi (mostrato in minuti) </p> <p>Generatore di report (mostrato in minuti) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo medio trascorso sulla pagina </p> </td> 
   <td colname="col2"> <p><b>Metrica obsoleta. </b> </p> <p>Consigliamo di utilizzare la dicitura «Tempo medio trascorso sul sito» se è necessario un tempo medio per un elemento dimensione. </p> </td> 
   <td colname="col3"> <p>Generatore di report (quando una dimensione si trova nella richiesta) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Totale lunghezza sessione </p> <p>(Noto anche come: Durata sessione precedente) </p> </td> 
   <td colname="col2"> <p>Solo SDK per app mobile. Determinato al successivo avvio dell'app, per la sessione precedente. Calcolato in secondi, questa metrica non viene conteggiata quando l'app è in background, solo quando utilizzata. Questa è una metrica a livello di sessione. </p> <p>Ad esempio: Installazione dell'app ABC e avvio e utilizzo per 2 minuti, quindi chiudi l'app. Nessun dato viene inviato in questa sessione. Al successivo avvio, la lunghezza totale sessione verrà inviata con un valore pari a 120. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> <p>Generatore di report </p> <p>Interfaccia utente di Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durata sessione media (mobile) </p> </td> 
   <td colname="col2"> <p>Totale lunghezza sessione/(Avvii - Primi avvii) </p> <p>Solo SDK per app mobile. Questa è una metrica a livello di sessione. </p> </td> 
   <td colname="col3"> <p>Generatore di report </p> <p>Interfaccia utente di Mobile Services </p> </td> 
  </tr> 
 </tbody> 
</table>

## Time Spent Dimensions {#section_D51606544CB046FC902E2E317318892C}

In questa tabella sono elencate le varie dimensioni dedicate al tempo, la definizione e dove in Adobe Analytics puoi utilizzarli.

<table id="table_BF1B7B8620714105BFB5C1AC37ABE02C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensione </th> 
   <th colname="col2" class="entry"> Definizione </th> 
   <th colname="col3" class="entry"> Disponibile in </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso per visita - granulari </p> </td> 
   <td colname="col2"> <p>Il tempo totale trascorso durante la visita al secondo, e applicato a ogni hit che era parte della visita. Questa dimensione a livello di visita. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso per visita - marcato </p> </td> 
   <td colname="col2"> <p>La dimensione granulare è suddivisa in 9 intervalli diversi. Questa è una dimensione a livello di visita. Gli intervalli includono: </p> 
    <ul id="ul_BC909A2D22ED4D48A3F7CE6A666F26E5"> 
     <li id="li_0FB28A1F0D894B7C95724A8C6BD5B00B">Meno di 1 minuto </li> 
     <li id="li_10223656420A475AAB3443981D49D10E">1-5 minuti </li> 
     <li id="li_0DEE723B81C64EAFB5BD1125D48D3AD2">5-10 minuti </li> 
     <li id="li_B736AC970E0049EB8844480702F345A6">10-30 minuti </li> 
     <li id="li_21B8ECC3EE66497E8D870A004351B04B">30-60 minuti </li> 
     <li id="li_79FB658128FD4F97AAE1A803F1687BD1">1-2 ore </li> 
     <li id="li_CCC0746FEB954BECB9E670ECCDBF30F3">2-5 ore </li> 
     <li id="li_BD7AFC524C814F9FAE423A4E301661D4">5-10 ore </li> 
     <li id="li_C9B5F1A83F99437A98A61756EE286687">10-15 ore </li> 
     <li id="li_8CC5A279D5804C5EA34C1B3589EF07BA">15 ore </li> 
    </ul> <p>Nota: Visite più lunghe possono verificarsi 12 ore quando gli hit vengono ricevuti in base all'ordine. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> <p>Generatore di report </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso sulla pagina </p> </td> 
   <td colname="col2"> <p>Il tempo totale trascorso su ogni hit, troncato al secondo. Si tratta di una dimensione a livello di hit e include sia visualizzazioni di pagina che eventi di collegamento. Non è solo limitato alla dimensione «pagina», come suggerito dal nome. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso sulla pagina </p> </td> 
   <td colname="col2"> <p>La dimensione granulare è suddivisa in 10 intervalli diversi; Tuttavia, la dimensione con bande conteggia solo le visualizzazioni di pagina (ed esclude gli eventi di collegamento). Questa dimensione è a livello di hit. Gli intervalli includono: </p> 
    <ul id="ul_D5F067A2520646A99AA261F9A4625C03"> 
     <li id="li_82307DE66EC548F0AD79DB1505A21F0D">meno di 15 secondi </li> 
     <li id="li_585965B82C4D43B6870978A5CE63B5B6">Da 15 a 29 secondi </li> 
     <li id="li_5C20DC78E126472A838818EBA1D954D0">Da 30 a 59 secondi </li> 
     <li id="li_2579C0B9279340ABA3AD4A527D758239">Da 1 a 3 minuti </li> 
     <li id="li_E0FD800E948049A48DB4329A3E7A2478">Da 3 a 5 minuti </li> 
     <li id="li_D9DBBFE6004F42BD80BB4F9268DF7DA7">Da 5 a 10 minuti </li> 
     <li id="li_20F146799679456E8D6434D79EE12C31">Da 10 a 15 minuti </li> 
     <li id="li_A38951A553A14AE7A0F23A904EEE35DE">Da 15 a 20 minuti </li> 
     <li id="li_D44D773A344E47BFAA771302A49D8BD4">Da 20 a 30 minuti </li> 
     <li id="li_8766683DB29147CD8470D2317F750E97">oltre 30 minuti </li> 
    </ul> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> </td> 
  </tr> 
 </tbody> 
</table>

## How Time Spent is Calculated {#section_90A3882638974969A4B8B674FFDB7624}

Adobe Analytics uses explicit values (including link events and video views) to calculate [!UICONTROL Time Spent].

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. Additionally, for similar reasons, [!UICONTROL Bounce Visits] (i.e. [!UICONTROL Visits] with a single hit) will not have a [!UICONTROL Time Spent]associated.

The **numerator** in all time spent calculations is "Total seconds spent".

**Il denominatore** non è disponibile come metrica separata in Analytics. Per le metriche di livello hit, il denominatore è sequenze. Una sequenza è un set consecutivo di hit in cui una determinata variabile contiene lo stesso valore (impostato, affiancato o persistente). «Estensione avanti» si riferisce alla persistenza dei prop tra le visualizzazioni di pagina (ad es. negli eventi di collegamento successivi), allo scopo di calcolare il tempo trascorso.

* For example, in the case of [!UICONTROL Page Name] or other dimensions at the hit level, the denominator is essentially [!UICONTROL Instances] or [!UICONTROL Page Views], but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence).

* [!UICONTROL Bounce] e [!UICONTROL Exit] gli hit vengono rimossi anche dal denominatore perché il tempo trascorso non può essere noto.

## FAQs about Time Spent {#section_51C2735BACAB42CCBA1DD3CBF238E2F7}

<table id="table_D8BA825412B6420390CA78D77A5E57C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tutte le metriche Tempo trascorso saranno applicate a qualsiasi dimensione? </p> </td> 
   <td colname="col2"> <p>Queste metriche Tempo trascorso possono essere applicate a qualsiasi dimensione: </p> 
    <ul id="ul_FC9513D0184B4A74BA1F4CCEA8BC1940"> 
     <li id="li_669156CC549040E08AB4977AF4B8AECB">Secondi totali trascorsi </li> 
     <li id="li_3CCD7E7D127448689228E98A5EE854CB">Tempo trascorso per visita (secondi) </li> 
     <li id="li_1F61C157EC414C7F8702BC3F365AA2D7">Tempo trascorso per visitatore (secondi) </li> 
     <li id="li_A3EF959A9BAB4872915F1A5C1A86D48E">Tempo medio trascorso sul sito (secondi) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quale tempo è più adatto nelle suddivisioni con altre dimensioni? </p> </td> 
   <td colname="col2"> <p>La dimensione «Tempo trascorso sulla pagina - granulare» è una dimensione a livello di hit. Suddividendo questa sezione per un'altra dimensione ti spiegherà i secondi in cui un hit è durato anche la dimensione di suddivisione. </p> <p>Nell'esempio di seguito, il termine di ricerca «classifica» è associato a tempi di hit di 54 secondi, 59 secondi, ecc., indicando che i visitatori stanno spesa il contenuto di lettura del tempo restituito per quel termine di ricerca. </p> <p><img placement="break" align="center"  src="assets/time-spent1.png" id="image_99FB62DCADDA4F8887B14333E65FF8FA" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual è la metrica appropriata rispetto alla dimensione di «Tempo trascorso sulla pagina - granulare»? </p> </td> 
   <td colname="col2"> <p>Qualsiasi metrica. La dimensione mostra il tempo trascorso sull'hit esatto in cui si è verificato l'evento. Più tempo trascorso significa che un visitatore resta più lungo su una pagina (hit) in cui si è verificato l'evento. </p> <p><img placement="break" align="center"  src="assets/time-spent2.png" id="image_A741C1BA52254124B5C28D030FE20EFF" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> How does <span class="wintitle"> Average Time Spent on Site </span> differ from <span class="wintitle"> Time Spent per Visit </span>? </td> 
   <td colname="col2"> <p>La differenza è il denominatore della metrica: </p> 
    <ul id="ul_E9D7B4D3EDCC4691B2C724E0FE5480D2"> 
     <li id="li_CA34D84A3164473A8737D258425CA468"> <span class="wintitle"> Tempo medio trascorso sul sito </span> utilizza le sequenze che includono un elemento di dimensione. </li> 
     <li id="li_2F2639480BE24927919732D00364EECA"> <span class="wintitle"> Il tempo trascorso per visita </span> utilizza il conteggio visite </li> 
    </ul> <p>Di conseguenza, queste metriche possono produrre risultati simili a livello di visita, ma saranno diversi a livello di hit. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Calculation Examples {#section_3D63D6A601F34E42AD5366435CB610D5}

Supponiamo che il seguente set di chiamate server sia per un singolo visitatore all'interno di una singola visita:

<table id="table_63CBB5097E5A46659877E2CA3C94D81C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Visita hit # </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Visita tempo trascorso (sec)</b> </td> 
   <td colname="col2"> 0 </td> 
   <td colname="col3"> 30 </td> 
   <td colname="col4"> 80 </td> 
   <td colname="col5"> 180 </td> 
   <td colname="col6"> 190 </td> 
   <td colname="col7"> 230 </td> 
   <td colname="col8"> 290 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondi trascorsi</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> 100 </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tipo di hit</b> </td> 
   <td colname="col2"> Pagina </td> 
   <td colname="col3"> Collegamento </td> 
   <td colname="col4"> Pagina </td> 
   <td colname="col5"> Pagina </td> 
   <td colname="col6"> Pagina </td> 
   <td colname="col7"> Pagina </td> 
   <td colname="col8"> Pagina </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nome pagina</b> </td> 
   <td colname="col2"> Home </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> Prodotto </td> 
   <td colname="col5"> Home </td> 
   <td colname="col6"> Home <p>(ricarica) </p> </td> 
   <td colname="col7"> Carrello </td> 
   <td colname="col8"> Conferma ordine </td> 
  </tr> 
 </tbody> 
</table>

### Esempio evar

<table id="table_6D0CF0C53DC145D3A53C06EC3012BCC0">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Visita hit # </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>eVar1</b> </td> 
   <td colname="col2"> Rosso <p>(set) </p> </td> 
   <td colname="col3"> Rosso <p>(persistente) </p> </td> 
   <td colname="col4"> (scaduto) </td> 
   <td colname="col5"> Blu <p>(set) </p> </td> 
   <td colname="col6"> Blu <p>(set) </p> </td> 
   <td colname="col7"> Blu <p>(persistente) </p> </td> 
   <td colname="col8"> Rosso <p>(set) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondi evar</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> - </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
 </tbody> 
</table>

### Esempio prop

<table id="table_1CB4D24A6CAA479C8E59A7C77FFB8226">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Visita hit # </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>prop1</b> </td> 
   <td colname="col2"> Una  <p>(set) </p> </td> 
   <td colname="col3"> Una  <p>(affiancamento) </p> </td> 
   <td colname="col4"> (non impostato) </td> 
   <td colname="col5"> B <p>set) </p> </td> 
   <td colname="col6"> B <p>(set) </p> </td> 
   <td colname="col7"> Una  <p>(set) </p> </td> 
   <td colname="col8"> C <p>(set) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>prop 1 secondi trascorsi</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> - </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
 </tbody> 
</table>

In base alla tabella sopra, le metriche Tempo trascorso vengono calcolate come indicato di seguito:

| prop1 | Secondi totali trascorsi | Tempo trascorso per visita | Tempo trascorso per visitatore | Conteggio delle sequenze | Tempo medio trascorso sul sito |
|---|---|---|---|---|---|
| Una  | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Tempo non attribuito | 100 | - | - | - | - |

| eVar1 | Secondi totali trascorsi | Tempo trascorso per visita | Tempo trascorso per visitatore | Conteggio delle sequenze | Tempo medio trascorso sul sito |
|---|---|---|---|---|---|
| Rosso | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Blu | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Tempo non attribuito | 100 | - | - | - | - |

Per le dimensioni del tempo trascorso, nei rapporti associati vengono visualizzate le righe seguenti:

* Tempo trascorso per visita (granulare): 290
* Tempo trascorso sulla pagina (granulare): 10, 30, 40, 50, 60, 100

Alcune note aggiuntive a supporto dell'esempio:

* Tutti i calcoli relativi al tempo sono basati sul tempo trascorso della visita che inizia da zero al primo hit della visita.
* «Secondi trascorso» è la differenza tra la marca temporale dell'hit corrente e la marca temporale dell'hit successivo. Di conseguenza, l'ultimo hit della visita (e gli bounce) non sono stati spesi.
* Una «sequenza» è un set di hit consecutivi in cui una determinata variabile contiene lo stesso valore (impostato, affiancato o persistente). Ad esempio, prop 1 «A» ha due sequenze: hit 1 e 2 e hit 6. I valori nell'ultimo hit della visita non avviano una nuova sequenza perché l'ultimo hit non è trascorso. Il tempo medio trascorso sul sito utilizza le sequenze nel denominatore.

   * Solo ai fini del tempo trascorso, i prop sono «spread avanti» dagli hit di pagina agli hit successivi dei collegamenti come mostrato sopra per prop 1 sull'hit 2. Questo consente il valore impostato per prop 1 sull'hit 1 ("A") per accumulare il tempo trascorso sull'hit 2.
   * Le evar accumulano il tempo trascorso su qualsiasi hit in cui la evar viene impostata o persistente. La persistenza evar è definita dalle impostazioni evar in Analytics Admin.
