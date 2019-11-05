---
description: Adobe Analytics offre diverse metriche e dimensioni Time Spent. Scopri cosa sono e come vengono calcolati.
seo-description: Adobe Analytics offre diverse metriche e dimensioni Time Spent. Scopri cosa sono e come vengono calcolati.
seo-title: Durata
solution: Analytics
title: Durata
topic: Metriche
uuid: a9f63da3-7e79-49c3-9b0b-6dcd2ae6aadc
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Durata

Adobe Analytics offre diverse metriche e dimensioni Time Spent. Scopri cosa sono e come vengono calcolati.

* [Metriche tempo trascorso](/help/components/c-variables/c-metrics/metrics-time-spent.md#section_4F54D70300944748A62088F5870E4B6C)
* [Dimensioni tempo trascorso](/help/components/c-variables/c-metrics/metrics-time-spent.md#section_D51606544CB046FC902E2E317318892C)
* [Modalità di calcolo del tempo trascorso](/help/components/c-variables/c-metrics/metrics-time-spent.md#section_90A3882638974969A4B8B674FFDB7624)
* [Domande frequenti sul tempo trascorso](/help/components/c-variables/c-metrics/metrics-time-spent.md#section_51C2735BACAB42CCBA1DD3CBF238E2F7)
* [Esempi di calcolo](/help/components/c-variables/c-metrics/metrics-time-spent.md#section_3D63D6A601F34E42AD5366435CB610D5)

## Time Spent Metrics {#section_4F54D70300944748A62088F5870E4B6C}

Questa tabella elenca le varie metriche Time Spent, la loro definizione e dove è possibile utilizzarle in Adobe Analytics.

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
   <td colname="col1"> <p>Totale secondi trascorsi </p> </td> 
   <td colname="col2"> <p>Rappresenta il tempo totale di interazione dei visitatori con un elemento dimensione specifico. </p> <p>Include l’istanza di un valore e la persistenza tra tutti gli hit successivi. Nel caso delle proprietà, il tempo trascorso viene conteggiato anche tra gli eventi di collegamento successivi. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> <p>Generatore di report (denominato 'tempo totale trascorso') </p> <p>Data Warehouse </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso per visita (secondi) </p> </td> 
   <td colname="col2"> <p><i>Totale secondi trascorsi / (visit-bounces)</i> </p> <p>Rappresenta il tempo medio di interazione dei visitatori con un elemento dimensione specifico durante ogni visita. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso per visitatore (secondi) </p> </td> 
   <td colname="col2"> <p><i>Totale secondi trascorsi / (visitatore univoco - visitatori univoci rimbalzati)</i> </p> <p>Rappresenta il tempo medio di interazione dei visitatori con un elemento dimensione specifico per tutta la durata del visitatore (lunghezza del cookie). </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo medio trascorso sul sito (secondi) </p> </td> 
   <td colname="col2"> <p>Rappresenta il tempo totale di interazione dei visitatori con un elemento dimensione specifico, per sequenza con un elemento dimensione. Non è limitato alle medie del "sito" come suggerisce il nome. Per ulteriori informazioni sulle sequenze, consulta la sezione Calcolo del tempo trascorso. </p> <p>Nota:  Questa metrica sarà molto probabilmente diversa da Tempo trascorso per visita a livello di elemento dimensione a causa delle differenze nel denominatore nel calcolo. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi (visualizzati in minuti) </p> <p>Generatore di report (visualizzato in minuti) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo medio trascorso sulla pagina </p> </td> 
   <td colname="col2"> <p><b>Metrica obsoleta. </b> </p> <p>È consigliabile utilizzare 'Tempo medio trascorso sul sito' se è necessario il tempo medio per un elemento dimensione. </p> </td> 
   <td colname="col3"> <p>Generatore di report (quando una dimensione è nella richiesta) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durata totale sessione </p> <p>(noto anche come: Durata sessione precedente) </p> </td> 
   <td colname="col2"> <p>Solo SDK per app mobili. Determinato al successivo avvio dell’app per la sessione precedente. Calcolata in secondi, questa metrica non conta quando l'app è in background, solo quando è in uso. Si tratta di una metrica a livello di sessione. </p> <p>Ad esempio: Installate l'app ABC e avviate l'app per 2 minuti, quindi chiudete l'app. Nessun dato inviato al momento della sessione. Al successivo avvio, Lunghezza totale sessione verrà inviata con un valore pari a 120. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> <p>Report Builder </p> <p>Interfaccia di Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durata media della sessione (mobile) </p> </td> 
   <td colname="col2"> <p>Durata totale sessione / (avvii - Primi avvii) </p> <p>Solo SDK per app mobili. Si tratta di una metrica a livello di sessione. </p> </td> 
   <td colname="col3"> <p>Report Builder </p> <p>Interfaccia di Mobile Services </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dimensioni tempo trascorso {#section_D51606544CB046FC902E2E317318892C}

In questa tabella sono elencate le varie dimensioni Time Spent, la loro definizione e dove è possibile utilizzarle in Adobe Analytics.

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
   <td colname="col1"> <p>Tempo trascorso per visita - granulare </p> </td> 
   <td colname="col2"> <p>Il tempo totale trascorso durante la visita troncato al secondo più vicino e applicato a ogni hit che faceva parte della visita. Questa è una dimensione a livello di visita. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso per visita - allungato </p> </td> 
   <td colname="col2"> <p>La dimensione granulare si è divisa in 9 intervalli diversi. Questa è una dimensione a livello di visita. Gli intervalli includono: </p> 
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
     <li id="li_8CC5A279D5804C5EA34C1B3589EF07BA">15+ ore </li> 
    </ul> <p>Nota:  Le visite possono durare più di 12 ore quando gli hit vengono ricevuti in modo non ordinato. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> <p>Report Builder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso sulla pagina - granulare </p> </td> 
   <td colname="col2"> <p>Il tempo totale trascorso su ogni hit, troncato al secondo più vicino. Si tratta di una dimensione a livello di hit e include sia le visualizzazioni di pagina che gli eventi di collegamento. Non è limitato alla dimensione "pagina", come suggerisce il nome. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo trascorso sulla pagina - a blocchi </p> </td> 
   <td colname="col2"> <p>La dimensione granulare si è incassata in 10 intervalli diversi; tuttavia, la dimensione esterna conteggia solo le visualizzazioni di pagina (ed esclude gli eventi di collegamento). Si tratta di una dimensione a livello di hit. Gli intervalli includono: </p> 
    <ul id="ul_D5F067A2520646A99AA261F9A4625C03"> 
     <li id="li_82307DE66EC548F0AD79DB1505A21F0D">inferiore a 15 secondi </li> 
     <li id="li_585965B82C4D43B6870978A5CE63B5B6">15-29 secondi </li> 
     <li id="li_5C20DC78E126472A838818EBA1D954D0">30-59 secondi </li> 
     <li id="li_2579C0B9279340ABA3AD4A527D758239">Da 1 a 3 minuti </li> 
     <li id="li_E0FD800E948049A48DB4329A3E7A2478">Da 3 a 5 minuti </li> 
     <li id="li_D9DBBFE6004F42BD80BB4F9268DF7DA7">Da 5 a 10 minuti </li> 
     <li id="li_20F146799679456E8D6434D79EE12C31">da 10 a 15 minuti </li> 
     <li id="li_A38951A553A14AE7A0F23A904EEE35DE">Da 15 a 20 minuti </li> 
     <li id="li_D44D773A344E47BFAA771302A49D8BD4">20-30 minuti </li> 
     <li id="li_8766683DB29147CD8470D2317F750E97">più di 30 minuti </li> 
    </ul> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modalità di calcolo del tempo trascorso {#section_90A3882638974969A4B8B674FFDB7624}

Adobe Analytics usa valori espliciti (inclusi eventi di collegamento e visualizzazioni video) per il calcolo [!UICONTROL Time Spent].

> [!NOTE] Senza eventi di collegamento come [!UICONTROL Video Views] o [!UICONTROL Exit Links], non è possibile conoscere il tempo trascorso sull'ultimo hit di una visita. Inoltre, per motivi simili, [!UICONTROL Bounce Visits] (ad es. [!UICONTROL Visits] con un singolo hit) non sarà [!UICONTROL Time Spent]associato.

Il **numeratore** in tutti i calcoli del tempo trascorso è "Totale secondi trascorsi".

Il **denominatore** non è disponibile come metrica separata in Analytics. Per le metriche sul tempo trascorso a livello di hit, il denominatore è sequenze. Una sequenza è un insieme consecutivo di hit in cui una determinata variabile contiene lo stesso valore (sia che venga impostata, estesa in avanti o persistente). Per "diffusione in avanti" si intende la persistenza di prop tra le visualizzazioni di pagina (ossia tra eventi di collegamento successivi), al fine di calcolare il tempo trascorso.

* Ad esempio, nel caso di [!UICONTROL Page Name] o di altre dimensioni a livello di hit, il denominatore è essenzialmente [!UICONTROL Instances] o [!UICONTROL Page Views], ma con ricariche e valori non impostati (ad esempio, eventi di collegamento) conteggiati come singola interazione (una sequenza).

* [!UICONTROL Bounce] e [!UICONTROL Exit] gli hit vengono rimossi anche dal denominatore perché il tempo trascorso non è noto.

## Domande frequenti sul tempo trascorso {#section_51C2735BACAB42CCBA1DD3CBF238E2F7}

<table id="table_D8BA825412B6420390CA78D77A5E57C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>È possibile applicare tutte le metriche Time Spent a qualsiasi dimensione? </p> </td> 
   <td colname="col2"> <p>Queste metriche Time Spent possono essere applicate a qualsiasi dimensione: </p> 
    <ul id="ul_FC9513D0184B4A74BA1F4CCEA8BC1940"> 
     <li id="li_669156CC549040E08AB4977AF4B8AECB">Totale secondi trascorsi </li> 
     <li id="li_3CCD7E7D127448689228E98A5EE854CB">Tempo trascorso per visita (secondi) </li> 
     <li id="li_1F61C157EC414C7F8702BC3F365AA2D7">Tempo trascorso per visitatore (secondi) </li> 
     <li id="li_A3EF959A9BAB4872915F1A5C1A86D48E">Tempo medio trascorso sul sito (secondi) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual è la dimensione del tempo trascorso più utilizzata nelle suddivisioni con altre dimensioni? </p> </td> 
   <td colname="col2"> <p>La dimensione "Tempo trascorso sulla pagina - granulare" è una dimensione a livello di hit. Suddividendo questa dimensione per un’altra dimensione, potrai vedere i secondi in cui è durato un hit in cui era presente anche la dimensione di suddivisione. </p> <p>Nell’esempio di seguito, il termine di ricerca "classifieds" è associato a un hit time di 54 secondi, 59 secondi ecc., ad esempio per indicare che i visitatori passano del tempo a leggere il contenuto restituito per quel termine di ricerca. </p> <p><img placement="break" align="center"  src="assets/time-spent1.png" id="image_99FB62DCADDA4F8887B14333E65FF8FA" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quale metrica è appropriata rispetto alla dimensione "Time Spent on Page - granular"? </p> </td> 
   <td colname="col2"> <p>Qualsiasi metrica. La dimensione mostra il tempo trascorso sull’hit esatto in cui si è verificato l’evento. Un tempo maggiore impiegato indica che un visitatore è rimasto più a lungo in una pagina (hit) in cui si è verificato l’evento. </p> <p><img placement="break" align="center"  src="assets/time-spent2.png" id="image_A741C1BA52254124B5C28D030FE20EFF" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> In che <span class="wintitle"> modo il tempo medio trascorso sul sito </span> è diverso dal <span class="wintitle"> tempo trascorso per visita </span>? </td> 
   <td colname="col2"> <p>La differenza è il denominatore della metrica: </p> 
    <ul id="ul_E9D7B4D3EDCC4691B2C724E0FE5480D2"> 
     <li id="li_CA34D84A3164473A8737D258425CA468"> <span class="wintitle"> Tempo medio trascorso sul sito </span> utilizza le sequenze che includono un elemento dimensione. </li> 
     <li id="li_2F2639480BE24927919732D00364EECA"> <span class="wintitle"> Il tempo trascorso per visita </span> utilizza il conteggio delle visite </li> 
    </ul> <p>Di conseguenza, queste metriche possono produrre risultati simili a livello di visita, ma saranno diverse a livello di hit. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Esempi di calcolo {#section_3D63D6A601F34E42AD5366435CB610D5}

Supponiamo che il seguente set di chiamate server riguardi un singolo visitatore all’interno di una singola visita:

<table id="table_63CBB5097E5A46659877E2CA3C94D81C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Visita l'hit # </th> 
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
   <td colname="col1"> <b>Tempo trascorso visita (sec)</b> </td> 
   <td colname="col2"> 0 </td> 
   <td colname="col3"> 30 </td> 
   <td colname="col4"> 80 </td> 
   <td colname="col5"> 180 </td> 
   <td colname="col6"> 190 </td> 
   <td colname="col7"> 230 </td> 
   <td colname="col8"> 290 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Secondi passati</b> </td> 
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
   <td colname="col6"> Home <p>(ricaricare) </p> </td> 
   <td colname="col7"> Carrello </td> 
   <td colname="col8"> Conferma ordine </td> 
  </tr> 
 </tbody> 
</table>

### Esempio eVar

<table id="table_6D0CF0C53DC145D3A53C06EC3012BCC0">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Visita l'hit # </th> 
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
   <td colname="col1"> <b>secondi eVar spesi</b> </td> 
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

### Esempio Prop

<table id="table_1CB4D24A6CAA479C8E59A7C77FFB8226">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Visita l'hit # </th> 
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
   <td colname="col3"> Una  <p>(differenziale in avanti) </p> </td> 
   <td colname="col4"> (non impostato) </td> 
   <td colname="col5"> B <p>set) </p> </td> 
   <td colname="col6"> B <p>(set) </p> </td> 
   <td colname="col7"> Una  <p>(set) </p> </td> 
   <td colname="col8"> C <p>(set) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>prop1 secondi trascorsi</b> </td> 
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

In base alla tabella precedente, le metriche Time Spent sono calcolate come segue:

| prop1 | Totale secondi trascorsi | Tempo trascorso per visita | Tempo trascorso per visitatore | Conteggio delle sequenze | Tempo medio trascorso sul sito |
|---|---|---|---|---|---|
| Una  | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Tempo non attribuito | 100 | - | - | - | - |

| eVar1 | Totale secondi trascorsi | Tempo trascorso per visita | Tempo trascorso per visitatore | Conteggio delle sequenze | Tempo medio trascorso sul sito |
|---|---|---|---|---|---|
| Rosso | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Blu | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Tempo non attribuito | 100 | - | - | - | - |

Per le dimensioni Time Spent, nei report associati verranno visualizzate le righe seguenti:

* Tempo trascorso per visita (granulare): 290
* Tempo trascorso sulla pagina (granulare): 10, 30, 40, 50, 60, 100

Alcune note aggiuntive a sostegno dell’esempio:

* Tutti i calcoli relativi al tempo trascorso si basano sul tempo trascorso della visita che inizia a zero al primo hit della visita.
* "Secondi trascorsi" è la differenza tra il timestamp dell’hit corrente e il timestamp dell’hit successivo. Di conseguenza, l’ultimo hit della visita (e rimbalzi) non ha tempo trascorso.
* Una "sequenza" è un insieme consecutivo di hit in cui una determinata variabile contiene lo stesso valore (sia che venga impostata, estesa in avanti o persistente). Ad esempio, prop1 "A" ha due sequenze: hit 1 e 2 e hit 6. I valori sull’ultimo hit della visita non avviano una nuova sequenza perché l’ultimo hit non ha tempo trascorso. Il tempo medio trascorso sul sito utilizza le sequenze nel denominatore.

   * Solo ai fini del tempo trascorso, le proprietà vengono "distribuite in avanti" dagli hit di pagina agli hit di collegamento successivi, come mostrato sopra per prop1 nell’hit 2. Questo consente al valore impostato per prop1 sull'hit 1 ("A") di accumulare il tempo trascorso sull'hit 2.
   * Le eVar accumulano il tempo trascorso su qualsiasi hit in cui l'eVar è impostata o persistente. La persistenza eVar è definita dalle impostazioni eVar in Analytics Admin.
