---
description: Scopri la prima esperienza cliente per implementare l’implementazione di Adobe Analytics.
keywords: Introduzione
seo-description: Scopri la prima esperienza cliente per implementare l’implementazione di Adobe Analytics.
seo-title: Modalità di implementazione semplificata
solution: Analytics
subtopic: Analysis Workspace
title: Modalità di implementazione semplificata
topic: Reports and Analytics
uuid: 6fad2c1f-476c-4985-90df-7c222e751dc
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Modalità di implementazione semplificata

Scopri la prima esperienza cliente per implementare l’implementazione di Adobe Analytics.

<!-- 

<p>https://activation.adobedtm.com/index.php?redirected=1 </p>

 -->

I nuovi utenti possono creare rapidamente la tua prima suite di [!DNL Analytics] rapporti (repository dei dati) utilizzando questa modalità di configurazione *`Getting Started with Adobe Analytics`* . Quindi, puoi distribuire [!DNL Analytics] il codice utilizzando [!DNL Dynamic Tag Management].

[!DNL Dynamic Tag Management] consente di gestire l’implementazione di Adobe Analytics senza dover apportare ogni volta modifiche al sito. Se stai implementando un app Mobile, puoi ottenere la SDK di cui hai bisogno per iniziare a raccogliere dati importanti dalle tue app.

Questa procedura ti consente di:

* Creare rapidamente la tua prima [suite per report](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html).
* Distribuisci [!DNL Analytics] e il servizio [](https://marketing.adobe.com/resources/help/en_US/mcvid/)identità.

* Eseguire report sui dati di base a livello di pagina.

> [!NOTE] Prima di iniziare, verifica che Analytics sia [attivato in Adobe Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html) (il processo di provisioning della soluzione). Se hai ricevuto un'email che ti invita a effettuare l'accesso in Analytics nella Dashboard di Enterprise, significa che hai completato questo prerequisito.

**Per eseguire la modalità di implementazione semplificata**

1. Effettuate l'accesso a [!DNL Adobe Experience Cloud] ( [experience.adobe.com](https://experiencecloud.adobe.com)).

   Quando accedi ad [!DNL Analytics], il sistema determina se disponi di una suite per report. In caso contrario viene visualizzata la [!UICONTROL Getting Started with Adobe Analytics] pagina.

   ![](assets/analytics-implementation-rs-wizard.png)

   In alternativa, puoi eseguire questa configurazione in [!DNL Analytics] facendo clic su **[!UICONTROL Help]** &gt; **[!UICONTROL Welcome to Adobe Analytics]**.

1. Specifica le seguenti informazioni di base sulla tua attività:

   <table id="table_1741878A1B284CB78D297D531DC703D6"> 
     <thead> 
      <tr> 
       <th colname="col1" class="entry"> Elemento </th> 
       <th colname="col2" class="entry"> Descrizione </th> 
      </tr> 
     </thead>
     <tbody> 
      <tr> 
       <td colname="col1"> <p>Tipo proprietà </p> </td> 
       <td colname="col2"> <p>La tua implementazione è per il web, il mobile o entrambi? </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Industrie </p> </td> 
       <td colname="col2"> <p>Specifica qual è il settore di attività della tua azienda (prodotti, servizi al cliente, brand awareness, pubblicità). </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Livello dati </p> </td> 
       <td colname="col2"> <p>(consigliato) un array di JavaScript utilizzato per archiviare informazioni. Se esegui una configurazione automatica tramite Gestione tag dinamica, utilizzerai un livello dati. </p> <p>For a blog on data layers, see <a href="https://blogs.adobe.com/digitalmarketing/analytics/data-layers-buzzword-best-practice/"> Data Layer: From Buzzword to Best Practice</a>. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Repository dei dati (Suite per report) </p> </td> 
       <td colname="col2"> <p> Una <a href="https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html">suite per report</a> è un insieme di dati discreti che corrispondono solitamente a una singola proprietà (sito o app) o marchio. Ogni suite per report è dotata del proprio insieme di report e metriche. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Fuso orario </p> </td> 
       <td colname="col2"> <p>Il fuso orario in cui ci si trova (rilevato automaticamente). </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Visite stimate alle pagine </p> </td> 
       <td colname="col2"> <p>Il numero di visite stimato che le pagine del tuo sito ricevono quotidianamente. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Valuta di base </p> </td> 
       <td colname="col2"> <p>La valuta con la quale lavori. </p> </td> 
      </tr> 
     </tbody> 
    </table>

1. Fai clic su **[!UICONTROL Next]**.

   Il sistema crea una suite per report.

1. To begin deployment, click **[!UICONTROL Next]**, then click one of the following options:

   <table id="table_71C7F7B9677346CD8D5130519D32464B"> 
     <thead> 
      <tr> 
       <th colname="col1" class="entry"> Elemento </th> 
       <th colname="col2" class="entry"> Descrizione </th> 
      </tr> 
     </thead>
     <tbody> 
      <tr> 
       <td colname="col1"> <p>Distribuisci </p> </td> 
       <td colname="col2"> <p> Lancia <span class="keyword">Gestione tag dinamica</span>, a cui puoi accedere per distribuire Analytics. This process automatically implements the <span class="filepath"> AppMeasurement.js</span> file and the Identity Service (<span class="filepath"> VisitorAPI.js</span>). </p> <p> <p>Importante: In una nuova scheda del browser, viene visualizzata una pagina della guida che illustra la distribuzione di <span class="keyword"> Adobe Analytics</span> tramite Gestione tag dinamica. </p> </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Scarica </p> </td> 
       <td colname="col2"> <p> Scarica il file di installazione denominato <span class="filepath">INSTALL-ME &lt;report suite name&gt;.js</span>. Questa opzione è dedicata agli utenti più esperti che conoscono l'<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html">implementazione JavaScript</a>. </p> <p> <p>Importante: scaricare il codice non equivale a distribuire <span class="keyword">Analytics</span>. Questa è una distribuzione manuale che esegui sulle pagine del tuo sito o attraverso i servizi di consulenza Adobe. </p> </p> </td> 
      </tr> 
     </tbody> 
    </table>

1. Esegui un report.

   Dopo aver distribuito lo strumento Analytics, puoi eseguire un report in Reporting e analisi per confermare che i dati affluiscono al tuo sito. (consulta Accedi e [naviga](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/analytics-navigation.html) per acquisire familiarità con l'interfaccia di Analytics.

   For example, a **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Real-Time]** lets you see immediate data.

   >[!NOTE]
   >
   >The [!UICONTROL Real-Time] report requires some configuration prior to running. Consulta [Configure Real-Time Report](https://marketing.adobe.com/resources/help/en_US/reference/t_realtime_admin.html) (Configura un report in tempo reale).

**Esempio di report in tempo reale**

![](assets/real-time-report.png)
