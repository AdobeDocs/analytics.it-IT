---
description: Il Generatore di segmenti fornisce un’area di lavoro per trascinare e rilasciare Dimension di metriche, segmenti ed eventi per segmentare i visitatori in base alla logica gerarchica dei contenitori, alle regole e agli operatori. Questo strumento di sviluppo integrato consente di creare e salvare segmenti semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite e hit pagina.
title: Generare segmenti
feature: Segmentation
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '1872'
ht-degree: 3%

---

# Generatore di segmenti

Il [!UICONTROL Segment Builder] consente di creare segmenti semplici o complessi che identificano gli attributi e le azioni dei visitatori in visite e hit pagina. Fornisce un’area di lavoro per trascinare e rilasciare dimensioni di metrica, eventi o altri segmenti al fine di segmentare i visitatori in base a logica gerarchica, regole e operatori.

Esistono diversi modi per accedere al Generatore di segmenti:

* **Navigazione superiore di Analytics**: fai clic **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Segments]**.
* **[!UICONTROL Analysis Workspace]**: fai clic **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, apri un progetto e fai clic su **[!UICONTROL + New]** > **[!UICONTROL Create Segment]**.
* **[!UICONTROL Report Builder]**: [Aggiungere o modificare segmenti nel Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html).

## Criteri del generatore {#section_F61C4268A5974C788629399ADE1E6E7C}

Puoi aggiungere definizioni di regole e contenitori per definire i segmenti.

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Title]**: assegna un nome al segmento.
1. **[!UICONTROL Description]**: fornisci una descrizione del segmento.
1. **[!UICONTROL Tags]**: [Assegna tag al segmento](/help/components/segmentation/segmentation-workflow/seg-workflow.md) per creare, fai clic su un elenco di tag esistenti o creane uno nuovo.
1. **[!UICONTROL Definitions]**: qui è dove [generare e configurare i segmenti](/help/components/segmentation/segmentation-workflow/seg-workflow.md), aggiungi regole e nidifica contenitori e sequenze.
1. **[!UICONTROL Show]**: (selettore contenitore superiore). Consente di selezionare il livello superiore [contenitore](/help/components/segmentation/seg-overview.md) ( [!UICONTROL Visitor], [!UICONTROL Visit], [!UICONTROL Hit]). Il contenitore principale predefinito è il contenitore Hit.
1. **[!UICONTROL Options]** icona : (ingranaggio)

   * **[!UICONTROL + Add container]**: consente di aggiungere un nuovo contenitore (sotto il contenitore principale) alla definizione del segmento.
   * **[!UICONTROL Exclude]**: consente di definire il segmento escludendo una o più dimensioni, segmenti o metriche.

1. **[!UICONTROL Dimensions]**: i componenti vengono trascinati e rilasciati dall’elenco Dimension (barra laterale arancione).
1. **[!UICONTROL Operator]**: puoi confrontare e vincolare i valori utilizzando gli operatori selezionati.
1. **[!UICONTROL Value]**: il valore immesso o selezionato per la dimensione, il segmento o la metrica.
1. **[!UICONTROL Attribution Models]**: disponibile solo per le dimensioni, questi modelli determinano i valori di una dimensione da segmentare. I modelli di Dimension sono particolarmente utili nella segmentazione sequenziale.

   * **[!UICONTROL Repeating]** (impostazione predefinita): include le istanze e i valori persistenti per la dimensione.
   * **[!UICONTROL Instance]**: include le istanze della dimensione.
   * **[!UICONTROL Non-repeating instance]**: include istanze univoche (non ripetute) della dimensione. Si tratta del modello applicato in Flusso quando le varianti di ripetizione sono escluse.

   ![](assets/attribution-models.jpg)

   **Esempio: segmento di hit in cui eVar 1 = A**

   | Esempio | A | A | A (persistente) | B | A | C |
   |---|---|---|---|---|---|---|
   | Ripetizione | X | X | X | - | X | - |
   | Istanza | X | X | - | - | X | - |
   | Istanza non ripetuta | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**: assegna il [!UICONTROL AND/OR/THEN] tra contenitori o regole. L’operatore THEN consente di: [definire segmenti sequenziali](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).
1. **[!UICONTROL Metric]**: (barra laterale verde) metrica trascinata e rilasciata dall’elenco Metriche.
1. **[!UICONTROL Comparison]** operatore: è possibile confrontare e vincolare i valori utilizzando gli operatori selezionati.
1. **[!UICONTROL Value]**: il valore immesso o selezionato per la dimensione, il segmento o la metrica.
1. **[!UICONTROL X]**: (Elimina) consente di eliminare questa parte della definizione del segmento.
1. **[!UICONTROL Experience Cloud publishing]**: pubblicando un segmento di Adobe Analytics nell’Experience Cloud puoi utilizzare il segmento per l’attività di marketing in [!DNL Audience Manager] e in altri canali di attivazione. [Ulteriori informazioni...](/help/components/segmentation/segmentation-workflow/seg-publish.md)
1. **[!UICONTROL Audience library]**: i servizi di pubblico di Adobe gestiscono come tradurre i dati sui visitatori in segmentazione del pubblico. La creazione e la gestione dei tipi di pubblico sono simili alla creazione e all’utilizzo dei segmenti e in più permettono di condividere i segmenti di pubblico nell’Experience Cloud. [Ulteriori informazioni...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=it)
1. **[!UICONTROL Search]**: esegue la ricerca nell’elenco di dimensioni, segmenti o metriche.
1. **[!UICONTROL Dimensions]**: (Elenco) Fai clic sull’intestazione per espanderla.
1. **[!UICONTROL Metrics]**: fai clic sull’intestazione per espandere.
1. **[!UICONTROL Segments]**: fai clic sull’intestazione per espandere.
1. **[!UICONTROL Report suite selector]**: consente di selezionare la suite di rapporti in cui verrà salvato il segmento. Puoi comunque utilizzare il segmento in tutte le suite di rapporti.
1. **[!UICONTROL Segment Preview]**: consente di visualizzare in anteprima le metriche chiave per verificare se hai un segmento valido e quanto è ampio il segmento. Rappresenta il raggruppamento del set di dati previsto per vedere se si applica questo segmento. Mostra 3 cerchi concentrici e un elenco per mostrare il numero e la percentuale di corrispondenze per [!UICONTROL Hits], [!UICONTROL Visits], e [!UICONTROL Visitors] per un segmento eseguito su un set di dati. Questo grafico viene aggiornato subito dopo la creazione o la modifica della definizione del segmento.
1. **[!UICONTROL Product Compatibility]**: fornisce un elenco dei prodotti Adobe Analytics (Analysis Workspace, Data Warehouse) con cui è compatibile il segmento creato. La maggior parte dei segmenti è compatibile con tutti i prodotti. Tuttavia, non tutti gli operatori e le dimensioni sono compatibili con tutti i prodotti Analytics, in particolare [Data Warehouse](/help/components/segmentation/seg-reference/seg-compatibility.md). Questo grafico viene aggiornato subito dopo aver apportato modifiche alla definizione del segmento.
1. **[!UICONTROL Save]** o **[!UICONTROL Cancel]**: salva o annulla il segmento. Dopo aver fatto clic su **[!UICONTROL Save]**, ti indirizzano al Gestore segmenti per gestire il segmento.


## Generare segmenti {#build-segments}

1. È sufficiente trascinare un evento di Dimension, segmento o metrica dal riquadro di sinistra al [!UICONTROL Definitions] campo.

   ![](assets/drag_n_drop_dimension.png)

   Il livello superiore predefinito [!UICONTROL Hit] Il contenitore viene visualizzato dopo aver trascinato un elemento in [!UICONTROL Definitions]. Puoi cambiare il tipo di contenitore in Visita o Visitatore da **[!UICONTROL Show]** menu a discesa.

1. Imposta il [operatore](/help/components/segmentation/seg-reference/seg-operators.md) dal menu a discesa.
1. Immettere o selezionare un valore per l&#39;elemento selezionato.
1. Se necessario, aggiungi altri contenitori utilizzando **[!UICONTROL And]**, **[!UICONTROL Or]**, o **[!UICONTROL Then]** regole.
1. Dopo aver inserito i contenitori e aver impostato le regole, vedi i risultati del segmento nel grafico di convalida in alto a destra. La convalida indica la percentuale e il numero assoluto di visualizzazioni di pagina, visite e visitatori univoci che corrispondono al segmento creato.
1. Sotto **[!UICONTROL Tags]**, [tag](/help/components/segmentation/segmentation-workflow/seg-tag.md) il contenitore selezionando un tag esistente o creandone uno nuovo.
1. Clic **[!UICONTROL Save]** per salvare il segmento.

Ora sei portato al [Gestore segmenti](/help/components/segmentation/segmentation-workflow/seg-manage.md), dove puoi assegnare tag, condividere e gestire il segmento in diversi modi.

## Aggiungere contenitori {#section_1C38F15703B44474B0718CEF06639EFD}

È possibile [creare un framework di contenitori](/help/components/segmentation/seg-overview.md) e quindi posiziona regole logiche e operatori tra.

1. Fai clic su **[!UICONTROL Options > Add Container]** (Usa modello di attribuzione non predefinito).

   ![](assets/add_container.png)

   Una nuova [!UICONTROL Hit] il contenitore si apre senza un [!UICONTROL Hit] (Visualizzazione pagina) identificata.

   ![](assets/new_container.png)

1. Modifica il tipo di contenitore in base alle esigenze.
1. Trascina un Dimension, un segmento o un evento dal riquadro di sinistra al contenitore.
1. Continua ad aggiungere nuovi contenitori dal livello superiore **[!UICONTROL Options]** > **[!UICONTROL Add container]** nella parte superiore della definizione, oppure aggiungi contenitori da un contenitore alla logica di nidificazione.

   **OPPURE**

   Seleziona una o più regole, quindi fai clic su **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. In questo modo la selezione diventa un contenitore separato.

## Utilizzare intervalli di date {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Puoi creare segmenti che contengono intervalli di date continui per rispondere a domande su campagne o eventi in corso.

Ad esempio, puoi facilmente creare un segmento che include &quot;tutti coloro che hanno effettuato un acquisto negli ultimi 60 giorni&quot;.

Crei un contenitore Visita e al suo interno aggiungi [!UICONTROL Last 60 days] l’intervallo di tempo e la metrica [!UICONTROL Orders is greater than or equal to 1], con un operatore AND:

![](assets/date-ranges.png)

Ecco un video sull’utilizzo degli intervalli di date continui nei segmenti:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Sovrapponi segmenti {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

L’impilamento dei segmenti funziona combinando i criteri in ciascun segmento utilizzando un operatore &quot;e&quot; e quindi applicando i criteri combinati. Questa operazione può essere eseguita direttamente in un progetto Workspace o nel generatore di segmenti.

Ad esempio, impilando un segmento &quot;utenti di telefonia mobile&quot; e un segmento &quot;geografia USA&quot; si restituiscono dati solo per gli utenti di telefonia mobile negli Stati Uniti.

Considera questi segmenti come blocchi predefiniti o moduli che puoi includere in una libreria di segmenti e che gli utenti potranno utilizzare come ritengono più opportuno. In questo modo, puoi ridurre drasticamente il numero di segmenti necessari. Ad esempio, supponiamo che tu abbia 40 segmenti:

* 20 per gli utenti di telefoni cellulari in diversi paesi (US_mobile, Germany_mobile, France_mobile, Brazil_mobile, ecc.)
* 20 per utenti di tablet in diversi paesi (US_tablet, Germany_tablet, France_tablet, Brazil_tablet, ecc.)

Utilizzando lo stacking dei segmenti, puoi ridurre il numero di segmenti a 22 e sovrapporli in base alle esigenze. Dovrai creare i seguenti segmenti:

* un segmento per gli utenti di dispositivi mobili
* un segmento per gli utenti di tablet
* 20 segmenti per le diverse aree geografiche

>[!NOTE]
>
>Quando si sovrappongono due segmenti, per impostazione predefinita questi sono collegati da un’istruzione AND. Non può essere modificata in un&#39;istruzione OR.

1. Passa al Generatore di segmenti.
1. Fornisci un titolo e una descrizione per il segmento.

   Risultato passaggio 1. Clic **[!UICONTROL Show Segments]** per visualizzare l’elenco dei segmenti nel menu di navigazione a sinistra.

   Risultato passaggio 1. Trascina i segmenti da sovrapporre nell’area di lavoro di definizione dei segmenti. Di seguito è riportato un esempio di segmento che sovrappone i segmenti esistenti &quot;Visite da tablet&quot; e &quot;US Geo&quot;:

   ![](assets/seg_stack2.png)

1. Salva il segmento.

   Risultato passaggio

## Modelli di segmento {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Sono forniti modelli di segmenti per casi di utilizzo di segmentazione comuni, ad esempio &quot;Prime visite&quot; o &quot;Visite da dispositivi mobili&quot;. Sono disponibili nei progetti Workspace e nel generatore di segmenti come blocchi predefiniti per i nuovi segmenti.

I modelli sono identificati dal logo &quot;A&quot; dell&#39;Adobe. Di seguito è riportato un esempio di modelli:

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome modello </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abbandona carrello </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno aggiunto elementi ai loro carrelli ma non hanno ordinato nulla. Nella definizione del segmento, il contenitore è Visita. La regola per questo segmento sequenziale è <p> Aggiunte carrello non è nullo </p> <p>Then </p> <p>Ordini è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prime visite </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visitato un massimo di una [1] volte. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Il numero di visite è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non acquirenti </td> 
   <td colname="col2">Visualizza i dati per i visitatori che non hanno partecipato a un evento di ordine. Nella definizione del segmento, il contenitore è Visitatore. Questo segmento utilizza la logica Exclude. La regola è <p>Ordini non nulli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visita non a pagina singola (non rimbalzate) </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visitato più di una volta. Nella definizione del segmento, il contenitore è Visitatore. Questo segmento utilizza la logica Exclude. La regola è <p>L'accesso singolo non è nullo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricerca a pagamento </td> 
   <td colname="col2">Visualizzare i dati dei visitatori provenienti da una ricerca a pagamento. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Ricerca a pagamento è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acquirenti </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno partecipato a un evento di ordine. Nella definizione del segmento, il contenitore è Visitatore. La regola è <p>Ordini non nulli. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite di ritorno </td> 
   <td colname="col2">Visualizza i dati dei visitatori che hanno visitato almeno una volta. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Il numero di visite è maggiore di 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite a pagina singola </td> 
   <td colname="col2"> Visualizzare i dati delle visite in cui viene visualizzato il valore di una singola pagina, anche se durante tale visita è possibile inviare più visualizzazioni di pagina. Le visite a pagina singola con eventi di collegamento di uscita sono incluse nel segmento. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Visite a pagina singola è uguale a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Il prodotto visualizzato non è stato aggiunto al carrello </td> 
   <td colname="col2">Visualizza i dati per i visitatori che hanno visualizzato i prodotti ma senza aggiunte al carrello. Nella definizione del segmento, il contenitore è Visita. La regola per questo segmento sequenziale è <p>Visualizzazioni prodotto non nulle </p> <p>Then </p> <p> Aggiunte al carrello è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da Campaign </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento le campagne. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Il codice di tracciamento non è nullo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da dispositivi mobili </td> 
   <td colname="col2">Visualizza i dati dei visitatori tramite dispositivi mobili. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Il dispositivo mobile non è nullo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da ricerca naturale </td> 
   <td colname="col2">Visualizzare i dati dei visitatori che non provengono da una ricerca a pagamento. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Ricerca a pagamento è uguale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da dispositivi non mobili </td> 
   <td colname="col2">Visualizza i dati dei visitatori che non utilizzano dispositivi mobili. Nella definizione del segmento, il contenitore è Visita. Questo segmento utilizza la logica Exclude. La regola è <p>Tipo di dispositivo mobile è uguale a Telefono cellulare </p> <p>Oppure </p> <p>Tipo di dispositivo mobile è uguale a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai telefoni </td> 
   <td colname="col2">Visualizza i dati dei visitatori tramite telefono. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Tipo di dispositivo è uguale a Telefono cellulare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai motori di ricerca </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento i motori di ricerca. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Tipo referrer è uguale a Motori di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite dai siti social </td> 
   <td colname="col2">Visualizza i dati dei visitatori a cui fanno riferimento i siti di social networking. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Tipo di referrer è uguale a Social network. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite da tablet </td> 
   <td colname="col2">Visualizza i dati dei visitatori utilizzando le tavolette. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Tipo di dispositivo è uguale a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite con il cookie ID visitatore </td> 
   <td colname="col2">Visualizza i dati dai visitatori al tuo sito, dove è richiesto un cookie persistente. Nella definizione del segmento, il contenitore è Visita. La regola è <p>Il cookie persistente è uguale a 1. </p> </td> 
  </tr> 
 </tbody> 
</table>
