---
description: Utilizzare gli avvisi in Reporting e analisi.
subtopic: Alerts
title: Avvisi
topic: Reports and Analytics
uuid: e1333a9b-eba0-45b7-b7e6-46e06190db64
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 13%

---


# Avvisi

## Avvisi {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

Il nuovo sistema di avvisi globale di Adobe Analytics, Avvisi intelligenti, consente di creare e gestire gli avvisi , , anche con l&#39;ausilio di anteprime e regole. È possibile

* Creare avvisi basati su anomalie (soglie del 90%, 95% o 99%; modifica della percentuale; superiore/inferiore).
* Visualizzare in anteprima la frequenza di attivazione degli avvisi.
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente.
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso.

Puoi accedere a questo nuovo sistema di avvisi da **[!UICONTROL More]** > **[!UICONTROL Alerts]** in qualsiasi rapporto in Reporting e analisi.

Per ulteriori informazioni, consulta la documentazione di Analysis Workspace in [Avvisi intelligenti](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html).

## Aggiungere un avviso {#task_51187E8BF19544DDA9EF2057E6F11D35}

Passaggi che descrivono come aggiungere un avviso in Adobe Analytics.

<!-- 

t_add_an_alert.xml

 -->

Passa al nuovo Generatore di avvisi nel menu **[!UICONTROL Analytics]** > **[!UICONTROL Components]** . Tuttavia, è comunque possibile accedervi dall’interno di reporting e analisi:

1. In Reports &amp; Analytics, apri il rapporto in cui desideri impostare un avviso.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Add Alert]**.
1. Verrà visualizzato il [nuovo Generatore di avvisi](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/alert-builder.html).

## Visualizza o modifica avvisi esistenti {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

Contesto attività

1. Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Alerts]**. Viene visualizzata la nuova [Gestione avvisi](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/alert-manager.html).

## Migrazione avvisi legacy {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

Diverse funzioni per gli avvisi esistenti di Analytics non saranno inclusi nella nuova funzione di Gestione avvisi, che verrà rilasciata (come parte di Analysis Workspace) in autunno 2016. Nella tabella seguente sono elencate le funzioni non più disponibile per gli avvisi e alcune delle funzioni relative agli avvisi che verranno trasferite alla nuova Gestione avvisi in forma diversa.

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzione Avvisi precedenti </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Obsoleta o migrata? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Totali (tutti gli elementi) </p> </td> 
   <td colname="col2"> <p>Creare avvisi su tutti gli elementi di un rapporto sulle dimensioni. </p> </td> 
   <td colname="col3"> <p>In alcuni casi, se crei un avviso su tutti gli elementi di un rapporto di dimensione o se imposti l’avviso solo sulla metrica aggregata da sola (non applicata a una dimensione), si verifica lo stesso risultato. Ad esempio, supponiamo che tu crei un avviso mensile Tutti gli elementi sulla metrica "Entrate". Ottieni lo stesso risultato semplicemente eseguendo il rapporto Ricavi e impostando un avviso mensile su di esso. </p> <p>In questa situazione, l’avviso Totals (Tutti gli elementi) legacy non sarà più disponibile e verrà migrato a quest’ultima versione, più semplice. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Primi 1000 elementi </p> <p> </p> </td> 
   <td colname="col2"> <p>Creare avvisi per i 1000 elementi principali di un rapporto. </p> </td> 
   <td colname="col3"> <p>Non più disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi di visitatori univoci basati sul tempo (giornalieri, settimanali, mensili, ecc. ) </p> <p> </p> </td> 
   <td colname="col2"> <p>Creare avvisi per rapporti sui visitatori univoci su base oraria, giornaliera, settimanale e mensile. </p> </td> 
   <td colname="col3"> <p>Nella nuova Gestione avvisi, alcuni avvisi univoci per visitatori basati su tempo non saranno più supportati. Ad esempio, se in precedenza era possibile impostare un avviso settimanale per Visitatori giornalieri unici, sarà possibile impostare un numero giornaliero, settimanale, ecc. avvisi sulla metrica Visitatori unici in corso. (Analysis Workspace supporta una metrica Visitatori univoci, ma non giornaliera/settimanale/mensile/ecc.) Metriche Visitatori univoci.) </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cerca </p> </td> 
   <td colname="col2"> <p>Creare avvisi per un rapporto sulle dimensioni con una ricerca applicata. Si applica solo a "Totali" ("Tutti gli elementi") o "Primi 1000 elementi". </p> <p> </p> </td> 
   <td colname="col3"> <p>Non più disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Rapporti specifici per Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p>Creare avvisi per diversi rapporti esistenti in Reports &amp; Analytics e non corrispondenti a un rapporto di Analysis Workspace, ad esempio 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">Lunghezza percorso </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">Bot </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">Timezoni </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">Domini di livello principali </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>Non più disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi con uno slot ASI come suite di rapporti </p> </td> 
   <td colname="col2"> <p>Non è più possibile creare o modificare gli slot ASI e non sono disponibili per l’utilizzo in Analysis Workspace. Pertanto, i nuovi avvisi non sono supportati. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi mediante metriche di partecipazione </p> </td> 
   <td colname="col2"> <p> <a href="https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-participation.html"  > Le metriche di partecipazione  </a> sono disponibili in Reports &amp; Analytics, ma al momento non sono disponibili nel nuovo sistema di avvisi in Analysis Workspace. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi mensili per suite di rapporti calendario personalizzate </p> </td> 
   <td colname="col2"> <p>Ciò riguarda solo i clienti con avvisi configurati per suite di rapporti con <a href="https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/data-requests/date-ranges/custom-calendar.html"  > date di inizio mese personalizzate </a> (tipi National Retail Federation/NRF e Custom Calendar). </p> <p>Non influisce sugli avvisi relativi alle suite di rapporti gregoriane o gregoriane modificate. Precedentemente questi avvisi erano stati inviati il primo giorno del mese gregoriano (ad esempio il 1° gennaio, il 1° febbraio ecc.). Questo non funziona con la nuova funzione di rilevamento delle anomalie degli avvisi, che tiene conto dei dati dei mesi precedenti durante il rilevamento delle anomalie. In futuro, aggiungeremo il supporto al sistema di programmazione per i calendari personalizzati in modo che sia gli Avvisi che i Progetti pianificati possano essere pianificati per l’invio il primo giorno del mese di calendario personalizzato invece che il primo giorno del mese gregoriano. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non ancora disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi che non vengono eseguiti da settembre 2015. </p> </td> 
   <td colname="col2"> <p>Ci sono diversi motivi per cui gli avvisi non sarebbero stati eseguiti dal settembre 2015, tra cui: </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">Fai clic su "Disabilita" nell'avviso nella Gestione avvisi. </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">L'avviso viene eseguito in caso di errori e non viene mai completato correttamente. </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> Questi avvisi non verranno trasferiti al nuovo sistema. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avvisi contrassegnati come "disabilitati" </td> 
   <td colname="col2"> Attualmente non è possibile disabilitare/riattivare gli avvisi nella nuova interfaccia utente, anche se si prevede di aggiungere questa funzionalità. <p> </p> </td> 
   <td colname="col3"> Questi avvisi non verranno trasferiti al nuovo sistema. </td> 
  </tr> 
 </tbody> 
</table>

