---
description: nulle
seo-description: nulle
seo-title: Avvisi
solution: Analytics
subtopic: Avvisi
title: Avvisi
topic: Reports & Analytics
uuid: e 1333 a 9 b-eba 0-45 b 7-b 7 e 6-46 e 06190 db 64
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Avvisi

## Alerts {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

Il nuovo sistema di avvisi globale di Adobe Analytics, Avvisi intelligenti, consente di creare e gestire gli avvisi , , anche con l'ausilio di anteprime e regole. È possibile

* Creare avvisi basati su anomalie (soglie del 90%, 95% o 99%; modifica della percentuale; superiore/inferiore).
* Visualizzare in anteprima la frequenza di attivazione degli avvisi.
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente.
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso.

You can access this new Alerts system from **[!UICONTROL More]** &gt; **[!UICONTROL Alerts]** in any report in Reports &amp; Analytics.

For more information, go to the Analysis Workspace documentation on [Intelligent Alerts](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/intellligent_alerts.html).

## Add an Alert {#task_51187E8BF19544DDA9EF2057E6F11D35}

Procedura che descrive come aggiungere un avviso in Adobe Analytics.

<!-- 

t_add_an_alert.xml

 -->

Navigate to the new Alert Builder in the **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** menu. Tuttavia, potete comunque accedervi dall'interno dei rapporti in Reporting e analisi:

1. In Reporting e analisi, apri il rapporto in cui vuoi impostare un avviso.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.
1. This will take you to the [new Alert Builder](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-builder.html).

## View or Edit Existing Alerts {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

Contesto attività

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Alerts]**. This takes you to the new [Alert Manager](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-manager.html).

## Legacy Alerts Migration {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

Diverse funzioni per gli avvisi esistenti di Analytics non saranno inclusi nella nuova funzione di Gestione avvisi, che verrà rilasciata (come parte di Analysis Workspace) in autunno 2016. Nella tabella seguente sono elencate le funzioni di avviso obsolete e alcune funzioni di avviso che verranno trasferite alla nuova Gestione avvisi in un modulo diverso.

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzionalità Avvisi precedenti </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Obsoleto o migrato? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Totali (Tutti gli elementi) </p> </td> 
   <td colname="col2"> <p>Crea avvisi su tutti gli elementi di un rapporto dimensione. </p> </td> 
   <td colname="col3"> <p>In alcuni casi, se crei un avviso su tutti gli elementi di un rapporto dimensione o se imposti l'avviso solo su una metrica aggregata (non applicata a una dimensione), si verifica lo stesso risultato. Ad esempio, supponiamo tu crei un avviso mensile Tutti gli elementi nella metrica «Revenue» (Entrate). Otterrete lo stesso risultato semplicemente per eseguire il rapporto sulle entrate e impostare un avviso mensile. </p> <p>In questa situazione, l'avviso Legacy (Tutti gli elementi) non sarà più disponibile e sarà migrato a quella seconda e più semplice. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Primi 1000 elementi </p> <p> </p> </td> 
   <td colname="col2"> <p>Crea avvisi per i primi 1000 elementi in un rapporto. </p> </td> 
   <td colname="col3"> <p>Non sono più disponibili nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi visitatori univoci basati sul tempo (giornalieri, settimanali, mensili ecc.) Visitatori univoci) </p> <p> </p> </td> 
   <td colname="col2"> <p>Crea avvisi per rapporti visitatori unici, giornalieri, settimanali e mensili. </p> </td> 
   <td colname="col3"> <p>Nella nuova Gestione avvisi, alcuni avvisi Visitatore unici basati sul tempo non saranno più supportati. Ad esempio, se in precedenza era possibile impostare un avviso settimanale per Visitatori giornalieri univoci, sarà possibile impostare ogni giorno, settimanale, ecc. avviso sulla metrica Visitatori unici. Analysis Workspace supporta una metrica Visitatori unici, ma non Giornaliera/Settimanale/Mensile/ecc. Metriche Visitatori univoci.) </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cerca </p> </td> 
   <td colname="col2"> <p>Crea avvisi per un rapporto di dimensioni con una ricerca applicata. Applicabile solo a «Totali» («Tutti gli elementi») o «Elementi principali 1000». </p> <p> </p> </td> 
   <td colname="col3"> <p>Non sono più disponibili nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Report specifici di Reporting e analisi </p> </td> 
   <td colname="col2"> <p>Creazione di avvisi per diversi rapporti esistenti in Reporting e analisi e non corrispondenti a un report Analysis Workspace, ad esempio 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">Lunghezza percorso </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">Bot </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">Timezone </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">Domini di livello principale </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>Non sono più disponibili nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi con uno slot ASI come suite di rapporti </p> </td> 
   <td colname="col2"> <p>You can no longer <a href="https://marketing.adobe.com/resources/help/en_US/reference/ASI_slots_admin.html" format="https" scope="external"> create or edit ASI slots </a> and they are not available for use in Analysis Workspace. Pertanto, non sono supportati dai nuovi avvisi. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi utilizzando le metriche di partecipazione </p> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_participation.html" format="https" scope="external"> Le metriche di partecipazione </a> sono disponibili in Reporting e analisi, ma non sono attualmente disponibili nel nuovo sistema di avvisi in Analysis Workspace. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi mensili per suite di rapporti personalizzate </p> </td> 
   <td colname="col2"> <p>This only affects customers with alerts set up for report suites that have <a href="https://marketing.adobe.com/resources/help/en_US/arb/custom_calendar.html" format="https" scope="external"> custom month start dates </a> (National Retail Federation/NRF and Custom Calendar types). </p> <p>Non influisce sugli avvisi sulle suite di rapporti gregoriane o modificate del calendario gregoriano. In precedenza questi avvisi venivano inviati nel primo giorno del mese Gregoriano (ad es. 1 gennaio, 1 febbraio, ecc.). Questo non funzionerà con la nuova funzione Rilevamento anomalie degli avvisi, che considera i dati dei mesi precedenti in account per rilevare le anomalie. In futuro, verrà aggiunto il supporto per il sistema di pianificazione per i calendari personalizzati, in modo che sia gli avvisi sia i progetti pianificati possano essere inviati il primo giorno del mese del calendario personalizzato, anziché il primo giorno del mese gregoriano. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non ancora disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi che non sono eseguiti dal 2015 settembre. </p> </td> 
   <td colname="col2"> <p>Gli avvisi non sono stati eseguiti a partire dal 2015 settembre, tra cui: </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">In Gestione avvisi hai fatto clic su "Disable" (Disattiva). </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">L'avviso è in esecuzione in errori e non viene mai completato correttamente. </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> Questi avvisi non verranno migrati nel nuovo sistema. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avvisi contrassegnati come «disabilitati» </td> 
   <td colname="col2"> Al momento non è possibile disattivare/riabilitare gli avvisi nella nuova interfaccia utente, anche se si prevede di aggiungere questa funzionalità. <p> </p> </td> 
   <td colname="col3"> Questi avvisi non verranno migrati nel nuovo sistema. </td> 
  </tr> 
 </tbody> 
</table>

