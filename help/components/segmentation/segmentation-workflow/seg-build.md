---
description: Il Generatore di segmenti fornisce un’area di lavoro per trascinare e rilasciare Dimension di metriche, segmenti ed eventi per segmentare i visitatori in base alla logica gerarchica dei contenitori, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di creare e salvare segmenti semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite e hit di pagina.
title: Generare segmenti
feature: Segmenti
uuid: c01393df-ccdd-431c-83a6-3c2700bd4999
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1929'
ht-degree: 5%

---

# Generatore di segmenti

Il [!UICONTROL Segment Builder] ti consente di creare segmenti semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite e hit di pagina. Fornisce un’area di lavoro per trascinare e rilasciare dimensioni metriche, eventi o altri segmenti al fine di segmentare i visitatori in base alla logica gerarchica, alle regole e agli operatori.

Esistono diversi modi per accedere al Generatore di segmenti:

* **Navigazione** superiore di Analytics: Fai clic su  **[!UICONTROL Analytics]** >  **[!UICONTROL Components]** >  **[!UICONTROL Segments]**.
* **[!UICONTROL Analysis Workspace]**: Fai clic su  **[!UICONTROL Analytics]** >  **[!UICONTROL Workspace]**, apri un progetto e fai clic su  **[!UICONTROL + New]** >  **[!UICONTROL Create Segment]**.
* **[!UICONTROL Reports & Analytics]**: Fai clic su  **[!UICONTROL Analytics]** >  **[!UICONTROL Reports]**, apri un rapporto esistente e fai clic sull’icona Segmenti   ![](assets/segment_icon.png) nella navigazione a sinistra, quindi fai clic su  **[!UICONTROL Add]**.
* **[!UICONTROL Report Builder]**:  [Aggiungi o modifica segmenti nel Report Builder](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/data-requests/segmentation.html).

## Criteri di generazione {#section_F61C4268A5974C788629399ADE1E6E7C}

Puoi aggiungere definizioni di regole e contenitori per definire i segmenti.

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Title]**: Denomina il segmento.
1. **[!UICONTROL Description]**: Fornisci una descrizione del segmento.
1. **[!UICONTROL Tags]**:  [Assegna tag al ](/help/components/segmentation/segmentation-workflow/seg-workflow.md) segmento che stai creando selezionando da un elenco di tag esistenti o creando un nuovo tag.
1. **[!UICONTROL Definitions]**: In questa area puoi  [creare e configurare segmenti](/help/components/segmentation/segmentation-workflow/seg-workflow.md), aggiungere regole e nidificare e sequenziare contenitori.
1. **[!UICONTROL Show]**: (Selettore contenitore superiore). Consente di selezionare il contenitore principale [a1/> ( [!UICONTROL Visitor], [!UICONTROL Visit], [!UICONTROL Hit]). ](/help/components/segmentation/seg-overview.md) Il contenitore principale predefinito è il contenitore Hit.
1. **[!UICONTROL Options]**: Icona (ingranaggio)

   * **[!UICONTROL + Add container]**: Consente di aggiungere un nuovo contenitore (sotto il contenitore principale) alla definizione del segmento.
   * **[!UICONTROL Exclude]**: Consente di definire il segmento escludendo una o più dimensioni, segmenti o metriche.

1. **[!UICONTROL Dimensions]**: I componenti vengono trascinati e rilasciati dall’elenco Dimension (barra laterale arancione).
1. **[!UICONTROL Operator]**: Puoi confrontare e vincolare i valori utilizzando gli operatori selezionati.
1. **[!UICONTROL Value]**: Il valore immesso o selezionato per la dimensione o il segmento o la metrica.
1. **[!UICONTROL Attribution Models]**: Disponibile solo per le dimensioni, questi modelli determinano i valori di una dimensione per cui eseguire il segmento. I modelli di Dimension sono particolarmente utili nella segmentazione sequenziale.

   * **[!UICONTROL Repeating]** (predefinito): Include istanze e valori persistenti per la dimensione.
   * **[!UICONTROL Instance]**: Include le istanze per la dimensione.
   * **[!UICONTROL Non-repeating instance]**: Include istanze univoche (non ripetute) per la dimensione. Questo è il modello applicato in Flusso quando le istanze ripetute sono escluse.

   ![](assets/attribution-models.jpg)

   **Esempio: Segmento Hit in cui eVar1 = A**

   | Esempio | A | A | A (persistente) | B | A | C |
   |---|---|---|---|---|---|---|
   | Ripetuto | X | X | X | - | X | - |
   | Istanza | X | X | - | - | X | - |
   | Istanza non ripetuta | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**: Assegna gli  [!UICONTROL AND/OR/THEN] operatori tra contenitori o regole. L’operatore THEN ti consente di [definire segmenti sequenziali](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).
1. **[!UICONTROL Metric]**: (Barra laterale verde) Metrica trascinata dall’elenco Metriche.
1. **[!UICONTROL Comparison]** operatore: Puoi confrontare e vincolare i valori utilizzando gli operatori selezionati.
1. **[!UICONTROL Value]**: Il valore immesso o selezionato per la dimensione o il segmento o la metrica.
1. **[!UICONTROL X]**: (Elimina) Consente di eliminare questa parte della definizione del segmento.
1. **[!UICONTROL Experience Cloud publishing]**: La pubblicazione di un segmento Adobe Analytics nell’Experience Cloud consente di utilizzare il segmento per l’attività di marketing in  [!DNL Audience Manager] e in altri canali di attivazione. [Ulteriori informazioni...](/help/components/segmentation/segmentation-workflow/seg-publish.md)
1. **[!UICONTROL Audience library]**: I servizi di pubblico di Adobe gestiscono la trasformazione dei dati dei visitatori in segmentazione del pubblico. La creazione e la gestione dei tipi di pubblico sono simili alla creazione e all&#39;uso dei segmenti, e in più permettono di condividere i segmenti di pubblico in Experience Cloud. [Ulteriori informazioni...](https://docs.adobe.com/content/help/it-IT/core-services/interface/audiences/audience-library.html)
1. **[!UICONTROL Search]**: Cerca nell’elenco di dimensioni, segmenti o metriche.
1. **[!UICONTROL Dimensions]**: (Elenco) Fai clic sull’intestazione da espandere.
1. **[!UICONTROL Metrics]**: Fai clic sull’intestazione da espandere.
1. **[!UICONTROL Segments]**: Fai clic sull’intestazione da espandere.
1. **[!UICONTROL Report suite selector]**: Consente di selezionare la suite di rapporti in cui verrà salvato il segmento. Puoi ancora utilizzare il segmento in tutte le suite di rapporti.
1. **[!UICONTROL Segment Preview]**: Ti consente di visualizzare in anteprima le metriche chiave per verificare se hai un segmento valido e la sua ampiezza. Rappresenta il raggruppamento del set di dati che si prevede di vedere se si applica questo segmento. Mostra 3 cerchi concentrici e un elenco per mostrare il numero e la percentuale di corrispondenze per [!UICONTROL Hits], [!UICONTROL Visits] e [!UICONTROL Visitors] per un segmento eseguito rispetto a un set di dati. Questo grafico viene aggiornato immediatamente dopo aver creato o apportato modifiche alla definizione del segmento.
1. **[!UICONTROL Product Compatibility]**: Fornisce un elenco dei prodotti Adobe Analytics (Analysis Workspace,  [!UICONTROL Reports & Analytics], Data Warehouse) con cui è compatibile il segmento creato. La maggior parte dei segmenti è compatibile con tutti i prodotti. Tuttavia, non tutti gli operatori e le dimensioni sono compatibili con tutti i prodotti Analytics, in particolare [Data Warehouse](/help/components/segmentation/seg-reference/seg-compatibility.md). Questo grafico viene aggiornato immediatamente dopo aver apportato modifiche alla definizione del segmento.
1. **[!UICONTROL Save]** o  **[!UICONTROL Cancel]**: Salva o annulla il segmento. Dopo aver fatto clic su **[!UICONTROL Save]**, accedi al Gestore segmenti dove puoi gestire il segmento.

I segmenti con intervalli di date incorporati continuano a funzionare diversamente in Analysis Workspace rispetto a [!UICONTROL Reports & Analytics]: In Workspace, un segmento con un intervallo di date integrato sostituisce l’intervallo di date del pannello. Al contrario, [!UICONTROL Reports & Analytics] offre l’intersezione dell’intervallo di date del rapporto e dell’intervallo di date integrato del segmento.

## Generare segmenti {#build-segments}

1. Trascina semplicemente un Dimension, un segmento o un evento metrica dal riquadro a sinistra al campo [!UICONTROL Definitions] .

   ![](assets/drag_n_drop_dimension.png)

   Il contenitore predefinito di livello superiore [!UICONTROL Hit] viene visualizzato dopo aver trascinato un elemento in [!UICONTROL Definitions]. Puoi modificare il tipo di contenitore in Visita o Visitatore dal menu a discesa **[!UICONTROL Show]** .

1. Imposta l&#39; [operatore](/help/components/segmentation/seg-reference/seg-operators.md) dal menu a discesa.
1. Immettere o selezionare un valore per l&#39;elemento selezionato.
1. Se necessario, aggiungi altri contenitori utilizzando le regole **[!UICONTROL And]**, **[!UICONTROL Or]** o **[!UICONTROL Then]**.
1. Dopo aver posizionato i contenitori e impostato le regole, vedi i risultati del segmento nel grafico di convalida in alto a destra. La convalida indica la percentuale e il numero assoluto di visualizzazioni di pagina, visite e visitatori unici che corrispondono al segmento creato.
1. Sotto **[!UICONTROL Tags]**, [tag](/help/components/segmentation/segmentation-workflow/seg-tag.md) il contenitore selezionando un tag esistente o creandone uno nuovo.
1. Fai clic su **[!UICONTROL Save]** per salvare il segmento.

Ora puoi passare al [Gestore segmenti](/help/components/segmentation/segmentation-workflow/seg-manage.md), dove puoi assegnare tag, condividere e gestire il segmento in più modi.

## Aggiungi contenitori {#section_1C38F15703B44474B0718CEF06639EFD}

È possibile [creare un framework di contenitori](/help/components/segmentation/seg-overview.md) e quindi inserire regole logiche e operatori tra loro.

1. Fai clic su **[!UICONTROL Options > Add Container]**.

   ![](assets/add_container.png)

   Viene aperto un nuovo contenitore [!UICONTROL Hit] senza l’identificazione di un [!UICONTROL Hit] (Visualizzazione pagina).

   ![](assets/new_container.png)

1. Modifica il tipo di contenitore in base alle esigenze.
1. Trascina un Dimension, un segmento o un evento dal riquadro a sinistra al contenitore .
1. Continua ad aggiungere nuovi contenitori dal pulsante di livello principale **[!UICONTROL Options]** > **[!UICONTROL Add container]** nella parte superiore della definizione oppure aggiungi contenitori dall’interno di un contenitore alla logica di nidificazione.

   **O**

   Seleziona una o più regole e fai clic su **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. In questo modo la selezione viene trasformata in un contenitore separato.

## Usa intervalli di date {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Puoi creare segmenti che contengono intervalli di date dinamici per rispondere a domande su campagne o eventi in corso.

Ad esempio, puoi creare facilmente un segmento che include &quot;tutti coloro che hanno effettuato un acquisto negli ultimi 60 giorni&quot;.

Crea un contenitore Visita e al suo interno aggiungi l’ intervallo di tempo [!UICONTROL Last 60 days] e la metrica [!UICONTROL Orders is greater than or equal to 1] con un operatore AND:

![](assets/date-ranges.png)

## Stack di segmenti {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

L’impilamento dei segmenti funziona combinando i criteri in ciascun segmento utilizzando un operatore &quot;e&quot; e quindi applicando i criteri combinati. Questa operazione può essere eseguita in un progetto Workspace direttamente o nel generatore di segmenti.

Ad esempio, impilare un segmento &quot;utenti di telefonia mobile&quot; e un segmento &quot;geografia statunitense&quot; restituirebbe dati solo agli utenti di telefonia mobile negli Stati Uniti.

Considera questi segmenti come blocchi predefiniti o moduli che puoi includere in una libreria di segmenti, affinché gli utenti possano utilizzarli come ritengono opportuno. In questo modo, puoi ridurre drasticamente il numero di segmenti necessari. Ad esempio, supponiamo di avere 40 segmenti:

* 20 per gli utenti di telefoni cellulari in diversi paesi (US_mobile, Germany_mobile, France_mobile, Brazil_mobile, ecc.)
* 20 per gli utenti di tablet in diversi paesi (US_tablet, Germany_tablet, France_tablet, Brazil_tablet, ecc.)

Utilizzando lo stacking dei segmenti, puoi ridurre il conteggio dei segmenti a 22 e sovrapporlo in base alle esigenze. È necessario creare questi segmenti:

* un segmento per gli utenti di dispositivi mobili
* un segmento per gli utenti di tablet
* 20 segmenti per diverse aree geografiche

>[!NOTE]
>
>Quando si sovrappongono due segmenti, per impostazione predefinita sono collegati da un’istruzione AND. Non è possibile modificare questo valore in un&#39;istruzione OR.

1. Passa al Generatore di segmenti.
1. Specifica un titolo e una descrizione per il segmento.

   Passaggio 1: Fai clic su **[!UICONTROL Show Segments]** per visualizzare l’elenco dei segmenti nel menu di navigazione a sinistra.

   Passaggio 1: Trascina i segmenti che vuoi impilare nell’area di lavoro della definizione del segmento. Ecco un esempio di un segmento che sovrappone i segmenti esistenti &quot;Visite da tablet&quot; e &quot;Geo US&quot;:

   ![](assets/seg_stack2.png)

1. Salva il segmento.

   Risultato del passaggio

## Modelli di segmento {#concept_5098446CC78D441E93B8E4D1D1EA6558}

I modelli di segmenti sono forniti per casi d’uso comuni di segmentazione, ad esempio &quot;Prime visite&quot; o &quot;Viste da dispositivi mobili&quot;. Sono disponibili nei progetti Workspace e nel generatore di segmenti come blocchi predefiniti per i nuovi segmenti.

I modelli sono contraddistinti dal logo &quot;A&quot; dell’Adobe. Di seguito è riportato un esempio di modelli:

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome modello </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Carrello abbandonato </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno aggiunto elementi ai loro carrelli ma non hanno ordinato nulla. Nella definizione del segmento, il contenitore è Visita. La regola per questo segmento sequenziale è <p> Aggiunte carrello non è nullo </p> <p>Then </p> <p>Ordini è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prime visite </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visitato un massimo di 1 [1] volte. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Numero visita è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non acquirenti </td> 
   <td colname="col2">Visualizza i dati per i visitatori che non hanno partecipato a un evento dell’ordine. Nella definizione del segmento, il contenitore è Visitatore. Questo segmento utilizza la logica di esclusione. La regola è <p>Ordini non nulli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visita non a pagina singola (senza rimbalzi) </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visitato più di una volta. Nella definizione del segmento, il contenitore è Visitatore. Questo segmento utilizza la logica di esclusione. La regola è <p>Accesso singolo non nullo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricerca a pagamento </td> 
   <td colname="col2">Visualizza i dati dei visitatori provenienti da una ricerca a pagamento. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Ricerca a pagamento è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acquirenti </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno partecipato a un evento dell’ordine. Nella definizione del segmento, il contenitore è Visitatore. La regola è <p>Ordini non nulli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite di ritorno </td> 
   <td colname="col2">Visualizza i dati dei visitatori che hanno visitato almeno una volta. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Numero visita maggiore di 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite a pagina singola </td> 
   <td colname="col2"> Visualizza i dati delle visite in cui viene visualizzato un singolo valore di pagina, anche se durante tale visita è possibile inviare più visualizzazioni di pagina. Le visite a pagina singola con eventi di collegamento in uscita sono incluse nel segmento. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Visite a pagina singola è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prodotto visualizzato non aggiunto al carrello </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visualizzato prodotti ma non hanno aggiunto carrello. Nella definizione del segmento, il contenitore è Visita. La regola per questo segmento sequenziale è <p>Visualizzazioni prodotto non nulle </p> <p>Then </p> <p> Aggiunte carrello è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da Campaign </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento le campagne. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Il codice di tracciamento non è null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da dispositivi mobili </td> 
   <td colname="col2">Visualizzare i dati dei visitatori che utilizzano dispositivi mobili. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Dispositivo mobile non nullo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da ricerca naturale </td> 
   <td colname="col2">Visualizza i dati dei visitatori non provenienti da una ricerca a pagamento. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Ricerca a pagamento è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da dispositivi non mobili </td> 
   <td colname="col2">Visualizza i dati dei visitatori che non utilizzano dispositivi mobili. Nella definizione del segmento, il contenitore è Visita. Questo segmento utilizza la logica di esclusione. La regola è <p>Tipo di dispositivo mobile uguale a Telefono cellulare </p> <p>Oppure </p> <p>Tipo di dispositivo mobile è uguale a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da telefoni </td> 
   <td colname="col2">Visualizza i dati dei visitatori che utilizzano i telefoni. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Tipo di dispositivo è uguale a Telefono cellulare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai motori di ricerca </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento i motori di ricerca. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Tipo referente è uguale a Motori di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai siti social </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento i siti social. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Tipo referente è uguale a Social Networks. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da Tablet </td> 
   <td colname="col2">Visualizza i dati dei visitatori utilizzando i tablet. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Tipo di dispositivo è uguale a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite con il cookie ID visitatore </td> 
   <td colname="col2">Visualizza i dati dei visitatori del tuo sito, dove è richiesto un cookie permanente. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Cookie persistente uguale a 1. </p> </td> 
  </tr> 
 </tbody> 
</table>
