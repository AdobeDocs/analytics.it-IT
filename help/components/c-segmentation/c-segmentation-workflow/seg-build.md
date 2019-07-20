---
description: Il Generatore di segmenti fornisce un quadro per trascinare dimensioni metriche, segmenti ed eventi per segmentare i visitatori in base a logica gerarchica, regole e operatori. Questo strumento di sviluppo integrato consente di creare e salvare segmenti semplici o complessi che identificano gli attributi dei visitatori e le azioni tra visite e hit di pagina.
seo-description: Il Generatore di segmenti fornisce un quadro per trascinare dimensioni metriche, segmenti ed eventi per segmentare i visitatori in base a logica gerarchica, regole e operatori. Questo strumento di sviluppo integrato consente di creare e salvare segmenti semplici o complessi che identificano gli attributi dei visitatori e le azioni tra visite e hit di pagina.
seo-title: Creare segmenti
solution: Analytics
title: Creare segmenti
topic: Segmenti
uuid: c 01393 df-ccdd -431 c -83 a 6-3 c 2700 bd 4999
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Generatore di segmenti

Il Generatore di segmenti fornisce un quadro per trascinare dimensioni metriche, segmenti ed eventi per segmentare i visitatori in base a logica gerarchica, regole e operatori. Questo strumento di sviluppo integrato consente di creare e salvare segmenti semplici o complessi che identificano gli attributi dei visitatori e le azioni tra visite e hit di pagina.

The [!UICONTROL Segment Builder] provides a canvas to drag and drop Metric Dimensions, Segments, and Events to segment visitors based on container hierarchy logic, rules, and operators. Questo strumento di sviluppo integrato consente di creare e salvare segmenti semplici o complessi che identificano gli attributi dei visitatori e le azioni tra visite e hit di pagina.

>[!IMPORTANT]
>
>Abbiamo introdotto modelli di attribuzione della dimensione nella release di giugno 2019. Consultate la sezione # 6 in Funzioni interfaccia Web di seguito.

Esistono diversi modi per accedere al Generatore di segmenti:

* **Navigazione in alto in Analytics:** Fate clic **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Segments]**.
* **[!UICONTROL Analysis Workspace]:** Fate clic **[!UICONTROL Analytics]** &gt; **[!UICONTROL Workspace]**, aprite un progetto e fate clic **[!UICONTROL + New]** su &gt; **[!UICONTROL Create Segment]**.
* **[!UICONTROL Reports & Analytics]:** Fai clic **[!UICONTROL Analytics]** su &gt; **[!UICONTROL Reports]**, apri un rapporto esistente e fai clic sull'icona Segmenti ![](assets/segment_icon.png) nella barra di navigazione a sinistra, quindi fai clic **[!UICONTROL Add]** su.
* **[!UICONTROL Ad Hoc Analysis]:**[Creare segmenti in Analisi ad hoc](../../../components/c-segmentation/c-segmentation-workflow/seg-build.md#section_E440630183D64999BA2369D1B8048AA6).
* **[!UICONTROL Report Builder]:**[Aggiungi o modifica segmenti in Generatore di report](https://marketing.adobe.com/resources/help/en_US/arb/segmentation.html).

## Segment Builder user interface {#concept_643F2DF74C544796B58F4656ABC5F726}

The [!UICONTROL Segment Builder] lets you build simple or complex segments that identify visitor attributes and actions across visits and page hits. Fornisce un quadro per trascinare dimensioni metriche, eventi o altri segmenti per segmentare i visitatori in base a logica gerarchica, regole e operatori.

## Web UI Features {#section_F61C4268A5974C788629399ADE1E6E7C}

The [!UICONTROL Segment Builder] lets you build and edit segments in the web UI (or in a [Java UI in Ad Hoc Analysis](../../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#section_E440630183D64999BA2369D1B8048AA6)). Puoi aggiungere definizioni di regole e contenitori per perfezionare i segmenti, sovrapporre segmenti e nidificarli per perfezionarli. Puoi inoltre verificare il numero di visualizzazioni di pagina, visite e visitatori unici derivanti dalla definizione del segmento corrente. Quindi salva il segmento per esigenze future.

Accedi al Generatore di segmenti:

* Displaying an existing report and clicking the Segments icon  ![](assets/segment_icon.png) in the left navigation. In the segment rail that displays, click **[!UICONTROL Add]**.

* From within the Segment Manager, clicking **[!UICONTROL + Add]**.
* Fai clic su un titolo segmento esistente in Gestione segmenti per modificare il segmento in Segment Builder (Generatore segmenti).

![](assets/segment_builder_ui.png)

1. **[!UICONTROL Title:]** Consente di denominare o rinominare il segmento.
1. **[!UICONTROL Description:]** Fornisce una descrizione del segmento. Se desiderate condividere il segmento, dovete fornire una descrizione.
1. **[!UICONTROL Tags:]**[Assegnate un tag al segmento](../../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_CD892CEB326C4986A1B67487052DBA50) che state creando scegliendo da un elenco di tag esistenti o creando un nuovo tag.
1. **[!UICONTROL Definitions:]** Puoi [creare e configurare segmenti](../../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_BD4C17B01C5B4E378D0C14C852D055D4), aggiungere regole e nidificare i contenitori. Consente di fornire una descrizione del nuovo segmento selezionando il contenitore e trascinando e trasmettendo dimensioni, segmenti o metriche nella definizione.
1. **[!UICONTROL Show:]** (Selettore contenitore superiore). Lets you select the top-level [container](../../../components/c-segmentation/seg-overview.md#concept_A38E7000056547399E346559D85E2551) ( [!UICONTROL Visitor], [!UICONTROL Visit], [!UICONTROL Hit]). Il contenitore di livello principale predefinito è il contenitore Hit.
1. **[!UICONTROL Options:]** icona (ingranaggio)

   * **[!UICONTROL + Add container:]** Consente di aggiungere un nuovo contenitore (sotto il contenitore di livello principale) alla definizione del segmento.
   * **[!UICONTROL + Add container from selection:]** Consente di creare un nuovo contenitore dall'elemento/elemento selezionato (multipla) nel campo Definizioni.
   * **[!UICONTROL Exclude:]** Consente di definire il segmento escludendo una o più dimensioni, segmenti o metriche.
   **[!UICONTROL Attribution Models:]** Per segmentazione delle dimensioni. I modelli di dimensione sono particolarmente utili nella segmentazione sequenziale, ad esempio in quelli che supportano visualizzazioni Flusso:
   * **[!UICONTROL Repeating]** ((predefinito)): Include istanze e valori persistenti per la dimensione.
   * **[!UICONTROL Instance]**: Include le istanze della dimensione.
   * **[!UICONTROL Non-repeating instance]**: Include istanze univoche (non ripetute) per la dimensione.
   ![](assets/attribution-models.jpg)

1. **[!UICONTROL Dimensions:]** La dimensione viene trascinata e rilasciata dall'elenco Dimensioni (barra laterale arancione).
1. **[!UICONTROL Comparison:]** Potete confrontare e vincolare i valori utilizzando operatori selezionati.
1. **[!UICONTROL Value:]** Il valore immesso o selezionato per la dimensione o il segmento o la metrica.
1. **[!UICONTROL And/Or/Then]**: Assegna gli [!UICONTROL AND/OR/THEN] operatori tra contenitori o regole. The THEN operator lets you [define sequential segments](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_83AEC78CD25F442EBEE364856A889560).
1. **[!UICONTROL Metric]**: (Barra laterale verde) Metrica trascinata e rilasciata dall'elenco Metriche.
1. **[!UICONTROL Comparison]** operatore: Potete confrontare e vincolare i valori utilizzando operatori selezionati.
1. **[!UICONTROL Value]**: Il valore immesso o selezionato per la dimensione o il segmento o la metrica.
1. **[!UICONTROL X]**: (Elimina) Consente di eliminare questa parte della definizione del segmento.
1. **[!UICONTROL Save]** oppure **[!UICONTROL Cancel]**: Salva o annulla il segmento. After clicking **[!UICONTROL Save]**, you are taken to the Segment Manager where you can manage the segment.
1. **[!UICONTROL Search:]** Cerca l'elenco di dimensioni, segmenti o metriche.
1. **[!UICONTROL Dimensions:]** (Elenco) Fate clic sull'intestazione per espandere.
1. **[!UICONTROL Metrics:]** Fare clic sull'intestazione per espandersi.
1. **[!UICONTROL Segments:]** Fare clic sull'intestazione per espandersi.
1. **[!UICONTROL Report suite selector:]** Consente di selezionare la suite di rapporti in cui verrà salvato questo segmento. Puoi comunque utilizzare il segmento in tutte le suite di rapporti.
1. **[!UICONTROL Segment Preview:]** Consente di visualizzare l'anteprima delle metriche chiave per verificare se si dispone di un segmento valido e di quanto è largo il segmento. Rappresenta la suddivisione del set di dati che si prevede di visualizzare se si applica questo segmento. Shows 3 concentric circles and a list to show the number and percentage of matches for [!UICONTROL Hits], [!UICONTROL Visits], and [!UICONTROL Visitors] for a segment run against a data set. Il grafico viene aggiornato immediatamente dopo aver creato o modificato la definizione del segmento.
1. **[!UICONTROL Product Compatibility:]** Fornisce un elenco dei prodotti Adobe Analytics (Analysis Workspace, [!UICONTROL Reports & Analytics]Ad Hoc Analysis, Data Warehouse) con il quale il segmento creato è compatibile. La maggior parte dei segmenti sono compatibili con tutti i prodotti. However, not all operators and dimensions are compatible with all Analytics products, especially [Data Warehouse](../../../components/c-segmentation/seg-reference/seg-compatibility.md#concept_7A2CC00352274A75ACD4949CA3C144D4). Il grafico viene aggiornato immediatamente dopo aver apportato modifiche alla definizione del segmento.

   Segments with embedded date ranges continue to operate differently in Analysis Workspace versus [!UICONTROL Reports & Analytics]: In Workspace, a segment with an embedded date range overrides the panel date range. By contrast, [!UICONTROL Reports & Analytics] gives you the intersection of the report date range and the segment's embedded date range.

**[!UICONTROL Publish to Experience Cloud (for `<report suite name>`)]**: (Non visualizzato sullo schermo) Questa opzione viene visualizzata solo se la suite di rapporti in cui stai salvando il segmento è [abilitata per Experience Cloud](../../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_1E9FC92437D748C392546542B6511D01). By publishing a segment to the Experience Cloud, you can use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], and [!DNL Audience Manager]. Sono necessari titolo e descrizione del segmento.

>[!NOTE]
>
>In Analytics puoi modificare o eliminare un segmento pubblicato. Se il segmento è in uso, quando modifichi un segmento compare un messaggio di avviso. Non puoi eliminare un segmento modificato che risulta in uso in Adobe [!DNL Target].

![](assets/segment_publish_to_mac_copy.png)

>[!IMPORTANT]
>
>Devi limitare il numero di tipi di pubblico condivisi da Analytics a 20 per evitare ulteriori ritardi di elaborazione. Il pubblico condiviso con Experience Cloud da Analytics non può superare i 20 milioni di membri unici. Inoltre, a causa della cache, sono necessarie 12 ore prima che l'eliminazione delle suite di rapporti di Analytics possa essere visibile in Experience Cloud.

>[!IMPORTANT]
>
>Once a visitor qualifies for the audience shared from Analytics, there is a 24 - 48 hour delay before that information is actionable in [!DNL Target], [!DNL Advertising Cloud], and [!DNL Campaign].

## Build segments {#section_050E3343533E45C3923242398E0E0213}

1. Simply drag a Dimension, Segment, or Metric Event from the left pane to the [!UICONTROL Definitions] field.

   ![](assets/drag_n_drop_dimension.png)

   The default top-level [!UICONTROL Hit] container is shown after dragging an element to [!UICONTROL Definitions]. You can change the container type to Visit or Visitor from the **[!UICONTROL Show]** drop-down menu.

1. Set the [operator](../../../components/c-segmentation/seg-reference/seg-operators.md) from the drop-down menu.
1. Inserite o selezionate un valore per l'elemento selezionato.
1. Add additional containers if needed, using **[!UICONTROL And]**, **[!UICONTROL Or]**, or **[!UICONTROL Then]** rules.
1. Dopo aver inserito i contenitori e impostato le regole, vedi i risultati del segmento nel grafico di convalida in alto a destra. La convalida indica la percentuale e il numero assoluto di visualizzazioni di pagina, visite e visitatori univoci che corrispondono al segmento creato.
1. Under **[!UICONTROL Tags]**, [tag](../../../components/c-segmentation/c-segmentation-workflow/seg-tag.md#concept_CD892CEB326C4986A1B67487052DBA50) the container by selecting an existing tag or creating a new one.
1. Click **[!UICONTROL Save]** to save the segment.

You are now taken to the [Segment Manager](../../../components/c-segmentation/c-segmentation-workflow/seg-manage.md#concept_7A2E019317864065B7C641DC3315928F), where you can tag, share, and manage your segment in multiple ways.

## Build and nest containers {#section_1C38F15703B44474B0718CEF06639EFD}

[Potete creare un framework di contenitori](../../../components/c-segmentation/seg-overview.md#concept_82653C7E29FE49F5A4B5E5E93B0A6399) , quindi inserire regole logiche e operatori tra.

1. Fai clic su **[!UICONTROL Options > Add Container]**.

   ![](assets/add_container.png)

   A new [!UICONTROL Hit] container opens without a [!UICONTROL Hit] (Page View) identified.

   ![](assets/new_container.png)

1. Modificare il tipo di contenitore in base alle esigenze.
1. Trascina una dimensione, un segmento o un evento dal riquadro a sinistra al contenitore.
1. Continue to add new containers from the top-level **[!UICONTROL Options]** &gt; **[!UICONTROL Add container]** button at the top of the definition, or add containers from within a container to nest logic.

   **OR**

   Select one or more rules and then click **[!UICONTROL Options]** &gt; **[!UICONTROL Add container from selection]**. In questo modo la selezione viene convertita in un contenitore separato.

## Use date ranges in segments {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Puoi creare segmenti che contengono intervalli di date dinamici per rispondere alle domande sulle campagne o gli eventi in corso.

Ad esempio, puoi creare facilmente un segmento che include «tutti gli utenti che hanno fatto un acquisto negli ultimi 60 giorni».

You create a Visit container and within it, add the [!UICONTROL Last 60 days] time range and the metric [!UICONTROL Orders is greater than or equal to 1], with an AND operator:

![](assets/date-ranges.png)

## Stack segments {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

L'impilamento dei segmenti funziona combinando i criteri in ogni segmento utilizzando un operatore "and" e quindi applicando i criteri combinati.

Ad esempio, se si sovrappone un segmento «user phone users» e un segmento «geografia US» si restituiscono dati solo per gli utenti di telefoni cellulari negli Stati Uniti.

Considera questi segmenti come blocchi costitutivi o moduli che puoi includere in una libreria segmenti, affinché gli utenti possano utilizzarli come per l'adattamento. In tal modo, puoi ridurre notevolmente il numero di segmenti necessari. Ad esempio, supponiamo di disporre di 40 segmenti:

* 20 per gli utenti del cellulare in diversi paesi (US_ mobile, Germania_ mobile, France_ mobile, Brasile_ mobile, ecc.)
* 20 per gli utenti tablet in diversi paesi (USA_ tablet, Germania_ tablet, France_ tablet, ecc.)

Con l'impilamento dei segmenti, puoi ridurre il conteggio dei segmenti a 22 e impilarli in base alle esigenze. Devi creare questi segmenti:

* un segmento per gli utenti mobili
* un segmento per gli utenti tablet
* 20 segmenti per le diverse aree geografiche

>[!NOTE]
>
>Quando si sovrappongono due segmenti, questi vengono collegati per impostazione predefinita da un'istruzione AND. Non può essere modificato in un'istruzione OR.

1. Andate al Generatore di segmenti.
1. Fornite un titolo e una descrizione per il segmento.

   Risultato 1. Click **[!UICONTROL Show Segments]** to bring up the list of segments in the left navigation.

   Risultato 1. Trascina e rilascia i segmenti da impilare nell'area di lavoro di definizione del segmento. Ecco un esempio di segmento che sovrappone i segmenti esistenti «Visits from Tablet» e «US Geo»:

   ![](assets/seg_stack2.png)

1. Salva il segmento.

   Risultato passaggio

## Use segment templates {#concept_5098446CC78D441E93B8E4D1D1EA6558}

I modelli rappresentano i precedenti segmenti preconfigurati e di suite.

In the Segment Manager, click **[!UICONTROL Add]**, which takes you to the Segment Builder. Now click the Segments icon  ![](assets/segment_icon.png)

per visualizzare la barra laterale. I modelli dei segmenti vengono visualizzati nella parte inferiore dell'elenco dei segmenti. Distinguono da un'icona della cartella a sinistra del nome del modello:

![](assets/seg_template.png)

Potete trascinarli nell'area di lavoro Definizioni e utilizzarli così come sono stati definiti o modificati.

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome modello </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abbandonato carrello </td> 
   <td colname="col2">Visualizzare i dati per i visitatori che hanno aggiunto elementi al loro carrelli, ma non ordinavano nulla. Nella definizione segmento, il contenitore è Visita. La regola per questo segmento sequenziale è <p> Aggiunte carrello non sono null </p> <p>Then </p> <p>Ordini è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite prima visita </td> 
   <td colname="col2">Visualizzare i dati per i visitatori che hanno visitato un massimo di uno [1] tempo. Nella definizione segmento, il contenitore è Visita. La regola è <p>Numero visita è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acquirenti non acquirenti </td> 
   <td colname="col2">Visualizzare i dati per i visitatori che non hanno partecipato a un evento di ordine. Nella definizione segmento, il contenitore è Visitatore. Questo segmento utilizza la logica Exclude. La regola è <p>Ordini non è null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visita non singola (non rimbalzi) </td> 
   <td colname="col2">Visualizzare i dati per i visitatori che hanno visitato più di una volta. Nella definizione segmento, il contenitore è Visitatore. Questo segmento utilizza la logica Exclude. La regola è <p>Single Access non è null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricerca pagata </td> 
   <td colname="col2">Visualizzare i dati dai visitatori provenienti da una ricerca a pagamento. Nella definizione segmento, il contenitore è Visita. La regola è <p>Paid Search è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acquirenti </td> 
   <td colname="col2">Visualizzare i dati per i visitatori che hanno partecipato a un evento di ordine. Nella definizione segmento, il contenitore è Visitatore. La regola è <p>Ordini non è null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite di ritorno </td> 
   <td colname="col2">Visualizzare i dati dei visitatori che hanno visitato almeno una volta. Nella definizione segmento, il contenitore è Visita. La regola è <p>Numero visita è maggiore di 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite a pagina singola </td> 
   <td colname="col2"> Visualizzare i dati delle visite in cui viene visualizzato un solo valore di pagina, anche se durante quella visita è possibile inviare più visualizzazioni di pagina. Le visite a una singola pagina con eventi di collegamento uscita sono incluse nel segmento. Nella definizione segmento, il contenitore è Visita. La regola è <p>Le visite singole sono pari a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prodotto visualizzato non aggiunto al carrello </td> 
   <td colname="col2">Visualizzare i dati per i visitatori che hanno visualizzato prodotti ma che non hanno aggiunto aggiunte al carrello. Nella definizione segmento, il contenitore è Visita. La regola per questo segmento sequenziale è <p>Visualizzazioni prodotto non è null </p> <p>Then </p> <p> Le aggiunte del carrello sono pari a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da Campaign </td> 
   <td colname="col2">Visualizzare i dati dei visitatori richiamati dalle campagne. Nella definizione segmento, il contenitore è Visita. La regola è <p>Il codice di tracciamento non è null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da dispositivi mobili </td> 
   <td colname="col2">Visualizzare i dati dai visitatori che utilizzano i dispositivi mobili. Nella definizione segmento, il contenitore è Visita. La regola è <p>Il dispositivo mobile non è null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da ricerca naturale </td> 
   <td colname="col2">Visualizzare i dati dai visitatori che non provengono da una ricerca a pagamento. Nella definizione segmento, il contenitore è Visita. La regola è <p>Paid Search è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da dispositivo non mobile </td> 
   <td colname="col2">Visualizzare i dati dai visitatori che non utilizzano dispositivi mobili. Nella definizione segmento, il contenitore è Visita. Questo segmento utilizza la logica Exclude. La regola è <p>Tipo dispositivo mobile è uguale al cellulare </p> <p>Oppure </p> <p>Tipo dispositivo mobile è Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai telefoni </td> 
   <td colname="col2">Visualizzare i dati dai visitatori che utilizzano i telefoni. Nella definizione segmento, il contenitore è Visita. La regola è <p>Tipo dispositivo è uguale al cellulare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da motori di ricerca </td> 
   <td colname="col2">Visualizzare i dati dei visitatori che fanno riferimento a motori di ricerca. Nella definizione segmento, il contenitore è Visita. La regola è <p>Il tipo di referente è uguale a Motori di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da social sites </td> 
   <td colname="col2">Visualizzare i dati dei visitatori che fanno riferimento a siti social. Nella definizione segmento, il contenitore è Visita. La regola è <p>Il tipo di referente è uguale alle reti social network. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da tablet </td> 
   <td colname="col2">Visualizzare i dati dai visitatori che utilizzano i tablet. Nella definizione segmento, il contenitore è Visita. La regola è <p>Tipo dispositivo è Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite con cookie ID visitatore </td> 
   <td colname="col2">Visualizzare i dati dei visitatori sul sito, dove è richiesto un cookie permanente. Nella definizione segmento, il contenitore è Visita. La regola è <p>Cookie persistente è uguale a 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Example: Campaign visitors segment {#concept_61AC6115097B4EB3AEFE8CE98F38315D}

Mostra un esempio del segmento utilizzato di frequente.

Molti clienti desiderano vedere le metriche dai visitatori che hanno risposto a campagne specifiche. La creazione di segmenti di visitatori della campagna rappresenta un modo semplice per ottenere questi dati.

La creazione di questo segmento in Segment Builder (Generatore di segmenti) significa che da un contenitore Visita di livello principale viene trascinato in una dimensione campagna, in questo caso Nome campagna:

![](assets/seg_campaign_visitor.png)

(Facoltativo) Puoi anche applicare un tag Campagne a questo segmento, se desideri filtrare facilmente tutti i segmenti relativi alla campagna.
