---
description: nulle
solution: Analytics
subtopic: Alerts
title: Avvisi
topic: Reports and analytics
uuid: e1333a9b-eba0-45b7-b7e6-46e06190db64
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Avvisi

## Avvisi {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

Il nuovo sistema di avvisi globale di Adobe Analytics, Avvisi intelligenti, consente di creare e gestire gli avvisi , , anche con l'ausilio di anteprime e regole. È possibile

* Creare avvisi basati su anomalie (soglie del 90%, 95% o 99%; modifica della percentuale; superiore/inferiore).
* Visualizzare in anteprima la frequenza di attivazione degli avvisi.
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente.
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso.

Puoi accedere a questo nuovo sistema di avvisi da **[!UICONTROL More]** &gt; **[!UICONTROL Alerts]** in qualsiasi rapporto in Reporting e analisi.

Per ulteriori informazioni, consulta la documentazione di Analysis Workspace su Avvisi [](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/intellligent_alerts.html)intelligenti.

## Aggiunta di un avviso {#task_51187E8BF19544DDA9EF2057E6F11D35}

Passaggi che descrivono come aggiungere un avviso in Adobe Analytics.

<!-- 

t_add_an_alert.xml

 -->

Passa al nuovo Generatore di avvisi nel menu **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** . Tuttavia, puoi comunque accedervi dall'interno dei report in Reporting e analisi:

1. In Reporting e analisi, apri il rapporto in cui vuoi impostare un avviso.
1. Fai clic su **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.
1. Viene visualizzato il [nuovo Generatore](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-builder.html)di avvisi.

## Visualizzare o modificare avvisi esistenti {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

Contesto attività

1. Vai a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Alerts]**. Viene aperta la nuova [Gestione](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-manager.html)avvisi.

## Migrazione avvisi legacy {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

Diverse funzioni per gli avvisi esistenti di Analytics non saranno inclusi nella nuova funzione di Gestione avvisi, che verrà rilasciata (come parte di Analysis Workspace) in autunno 2016. Nella tabella seguente sono elencate le funzioni di avviso obsolete e alcune delle funzioni di avviso che verranno trasferite alla nuova Gestione avvisi in un modulo diverso.

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzione Avvisi legacy </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Obsoleto o migrato? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Totali (tutti gli elementi) </p> </td> 
   <td colname="col2"> <p>Creare avvisi su tutti gli elementi di un rapporto dimensione. </p> </td> 
   <td colname="col3"> <p>In alcuni casi, se si crea un avviso su tutti gli elementi di un rapporto dimensione o se si imposta l'avviso solo sulla metrica aggregata di per sé (non applicata a una dimensione), si verifica lo stesso risultato. Ad esempio, crei un avviso mensile Tutti gli articoli sulla metrica "Entrate". Si otterrebbe lo stesso risultato semplicemente eseguendo il report Revenue (Entrate) e configurando un avviso mensile su esso. </p> <p>In questa situazione, l'avviso Totals (Tutti gli elementi) legacy non sarà più disponibile e verrà migrato a quest'ultima versione, più semplice. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Primi 1000 elementi </p> <p> </p> </td> 
   <td colname="col2"> <p>Creare avvisi per i primi 1000 elementi di un report. </p> </td> 
   <td colname="col3"> <p>Non più disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi univoci dei visitatori basati su tempo (giornalieri, settimanali, mensili, ecc.) Visitatori unici) </p> <p> </p> </td> 
   <td colname="col2"> <p>Creare avvisi per rapporti sui visitatori univoci su base oraria, giornaliera, settimanale e mensile. </p> </td> 
   <td colname="col3"> <p>Nella nuova Gestione avvisi, alcuni avvisi per visitatori univoci basati su tempo non saranno più supportati. Ad esempio, se in precedenza era possibile impostare un avviso settimanale per Visitatori giornalieri univoci, sarà possibile impostare un avviso giornaliero, settimanale e così via. avvisi relativi alla metrica Visitatori unici in corso. Analysis Workspace supporta una metrica Visitatori unici, ma non giornaliera/settimanale/mensile/ecc. Metriche univoche dei visitatori. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cerca </p> </td> 
   <td colname="col2"> <p>Creazione di avvisi per un rapporto dimensione con una ricerca applicata. Si applica solo a "Totali" ("Tutti gli elementi") o "Primi 1000 elementi". </p> <p> </p> </td> 
   <td colname="col3"> <p>Non più disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Report specifici per Reporting e analisi </p> </td> 
   <td colname="col2"> <p>Creare avvisi per diversi rapporti esistenti in Reporting e analisi e non corrispondenti a un rapporto di Analysis Workspace, ad esempio 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">Lunghezza percorso </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">Bot </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">Timezones </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">Domini di livello principali </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>Non più disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi con uno slot ASI come suite di rapporti </p> </td> 
   <td colname="col2"> <p>Non è più possibile <a href="https://marketing.adobe.com/resources/help/en_US/reference/ASI_slots_admin.html"  > creare o modificare gli slot ASI </a> e non sono disponibili per l'utilizzo in Analysis Workspace. Pertanto, non sono supportati dai nuovi avvisi. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi mediante metriche di partecipazione </p> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_participation.html"  > Le metriche di partecipazione </a> sono disponibili in Reporting e analisi, ma al momento non sono disponibili nel nuovo sistema di avvisi in Analysis Workspace. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi mensili per suite di rapporti per il calendario personalizzate </p> </td> 
   <td colname="col2"> <p>Questo interessa solo i clienti con avvisi impostati per le suite di rapporti che hanno date di inizio mese <a href="https://marketing.adobe.com/resources/help/en_US/arb/custom_calendar.html"  > personalizzate </a> (Federazione Nazionale Vendita al Dettaglio/NRF e Tipi di calendario personalizzati). </p> <p>Non influisce sugli avvisi relativi alle suite di rapporti gregoriane o gregoriane modificate. Precedentemente questi avvisi erano stati inviati il primo giorno del mese gregoriano (ad esempio, 1° gennaio, 1° febbraio ecc.). Ciò non funzionerà con la nuova funzione Anomaly Detection (Rilevamento anomalo) degli avvisi, che tiene conto dei dati dei mesi precedenti al momento del rilevamento delle anomalie. In futuro, aggiungeremo il supporto al nostro sistema di programmazione per i calendari personalizzati in modo che sia gli Avvisi che i Progetti programmati possano essere programmati per l'invio il primo giorno del mese di calendario personalizzato invece che il primo giorno del mese gregoriano. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non ancora disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi non in esecuzione da settembre 2015. </p> </td> 
   <td colname="col2"> <p>Esistono diversi motivi per cui gli avvisi non sarebbero stati eseguiti da settembre 2015, tra cui: </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">Fai clic su "Disattiva" nell'avviso nella Gestione avvisi. </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">L'avviso è in esecuzione in caso di errori e non viene mai completato correttamente. </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> Questi avvisi non verranno migrati nel nuovo sistema. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avvisi contrassegnati come "disabilitati" </td> 
   <td colname="col2"> Al momento non è possibile disattivare/riattivare gli avvisi nella nuova interfaccia utente, anche se è prevista l’aggiunta di questa funzionalità. <p> </p> </td> 
   <td colname="col3"> Questi avvisi non verranno migrati nel nuovo sistema. </td> 
  </tr> 
 </tbody> 
</table>

