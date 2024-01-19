---
description: Utilizzare gli avvisi in Reports & Analytics.
subtopic: Alerts
title: Avvisi
uuid: e1333a9b-eba0-45b7-b7e6-46e06190db64
feature: Alerts
role: User, Admin
exl-id: f0a23afb-6c21-41e6-9033-9d3421bb1f4b
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 7%

---

# Avvisi

## Avvisi {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

In qualità di sistema di avvisi globale di Adobe Analytics, gli avvisi intelligenti ti consentono di creare e gestire gli avvisi, fornendo allo stesso tempo funzioni per l’anteprima degli avvisi e il contributo delle regole. È possibile eseguire le seguenti azioni:

* Creare avvisi basati su anomalie (soglie del 90%, 95% o 99%; modifica della percentuale; superiore/inferiore).
* Visualizzare in anteprima la frequenza di attivazione degli avvisi.
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente.
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso.

Puoi accedere a questo nuovo sistema di avvisi da **[!UICONTROL More]** > **[!UICONTROL Alerts]** in qualsiasi rapporto in Reports &amp; Analytics.

Per ulteriori informazioni, consulta la documentazione di Analysis Workspace su [Avvisi intelligenti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html?lang=it).

## Aggiungi un avviso {#task_51187E8BF19544DDA9EF2057E6F11D35}

In Adobe Analytics puoi aggiungere un avviso dal Generatore di avvisi o da un rapporto specifico.

<!-- 

t_add_an_alert.xml

 -->

### Aggiungere un avviso dal Generatore di avvisi

1. Seleziona **[!UICONTROL Analytics]** > **[!UICONTROL Components]** per aprire il Generatore di avvisi.

### Aggiungere un avviso da un singolo rapporto

1. In Reports &amp; Analytics, apri il rapporto in cui desideri impostare un avviso.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Add Alert]**.
1. Verrà visualizzato il [nuovo generatore di avvisi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/alert-builder.html).

## Visualizza o modifica avvisi esistenti {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

<!-- add Task Context-->

1. Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Alerts]**. Questo ti porta al nuovo [Gestione avvisi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/alert-manager.html).

## Migrazione avvisi legacy {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

Diverse funzioni per gli avvisi esistenti di Analytics non saranno inclusi nella nuova funzione di Gestione avvisi, che verrà rilasciata (come parte di Analysis Workspace) in autunno 2016. Nella tabella seguente sono elencate le funzioni di avviso obsolete e alcune delle funzioni di avviso che verranno migrate alla nuova Gestione avvisi in un modulo diverso.

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
   <td colname="col2"> <p>Creare avvisi su tutti gli elementi di un rapporto di dimensione. </p> </td> 
   <td colname="col3"> <p>In alcuni casi, che si crei un avviso su tutti gli elementi di un rapporto di dimensione o che si imposti l’avviso solo sulla metrica aggregata in sé (non applicata a una dimensione), si verifica lo stesso risultato. Ad esempio, supponiamo che tu crei un avviso mensile Tutti gli elementi sulla metrica "Entrate". Lo stesso risultato si ottiene semplicemente eseguendo il rapporto Ricavi e impostando un avviso mensile. </p> <p>In questa situazione, l’avviso legacy Totali (tutti gli elementi) non sarà più disponibile e verrà migrato a quest’ultima versione più semplice. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Primi 1000 elementi </p> <p> </p> </td> 
   <td colname="col2"> <p>Crea avvisi per i primi 1000 elementi di un rapporto. </p> </td> 
   <td colname="col3"> <p>Non più disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi per visitatori univoci basati sul tempo (giornalieri, settimanali, mensili, ecc.) Visitatori univoci) </p> <p> </p> </td> 
   <td colname="col2"> <p>Crea avvisi per rapporti sui visitatori univoci orari, giornalieri, settimanali e mensili. </p> </td> 
   <td colname="col3"> <p>Nella nuova Gestione avvisi, alcuni avvisi basati sul tempo per Visitatore univoco non saranno più supportati. Ad esempio, se in precedenza era possibile impostare un avviso settimanale per Visitatori univoci giornalieri, sarà possibile impostare un avviso giornaliero, settimanale e così via. genera un avviso sulla metrica Visitatori univoci in corso. (Analysis Workspace supporta una metrica Visitatori univoci, ma non Giornaliero/Settimanale/Mensile/ecc.) Metriche Visitatori univoci.) </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ricerca </p> </td> 
   <td colname="col2"> <p>Creare avvisi per un rapporto di dimensione a cui è applicata una ricerca. Si applica solo ai "Totali" ("Tutti gli elementi") o ai "Primi 1000 elementi". </p> <p> </p> </td> 
   <td colname="col3"> <p>Non più disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Rapporti specifici di Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p>Creazione di avvisi per diversi rapporti esistenti in Reports &amp; Analytics che non corrispondono a un rapporto di Analysis Workspace, ad esempio 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">Lunghezza percorso </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">Bot </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">Fusi orari </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">Domini di primo livello </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>Non più disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi con uno slot ASI come suite di rapporti </p> </td> 
   <td colname="col2"> <p>Non è più possibile creare o modificare gli slot ASI che non sono disponibili per l'utilizzo in Analysis Workspace. Pertanto, non sono supportati dai nuovi avvisi. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi mensili per suite di rapporti per calendari personalizzati </p> </td> 
   <td colname="col2"> <p>Questo interessa solo i clienti con avvisi impostati per suite di rapporti che hanno <a href="https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/date-ranges/custom-calendar.html"  > date di inizio del mese personalizzato </a> (tipi National Retail Federation/NRF e Custom Calendar). </p> <p>Non influisce sugli avvisi relativi alle suite di rapporti del calendario gregoriano o gregoriano modificato. In precedenza, questi avvisi venivano inviati il primo giorno del mese gregoriano (ad esempio, il 1° gennaio, il 1° febbraio ecc). Questa funzione non funziona con la nuova funzione di rilevamento delle anomalie degli avvisi, che prende in considerazione i dati dei mesi precedenti per rilevare le anomalie. In futuro, aggiungeremo il supporto al nostro sistema di pianificazione per i calendari personalizzati in modo che sia gli avvisi che i progetti pianificati possano essere programmati per l’invio il primo giorno del mese del calendario personalizzato, invece del primo giorno del mese gregoriano. </p> <p> </p> </td> 
   <td colname="col3"> <p>Non ancora disponibile nella nuova Gestione avvisi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avvisi che non vengono eseguiti da settembre 2015. </p> </td> 
   <td colname="col2"> <p>Ci sono diversi motivi per cui gli avvisi non sarebbero stati eseguiti dal settembre 2015, tra cui: </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">Hai fatto clic su "Disattiva" sull’avviso in Gestione avvisi. </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">L’avviso sta generando errori e non viene mai completato correttamente. </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> La migrazione di questi avvisi al nuovo sistema non verrà eseguita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avvisi contrassegnati come "disabilitati" </td> 
   <td colname="col2"> Non è attualmente possibile disattivare/riattivare gli avvisi nella nuova interfaccia utente, anche se si prevede di aggiungere questa funzionalità. <p> </p> </td> 
   <td colname="col3"> La migrazione di questi avvisi al nuovo sistema non verrà eseguita. </td> 
  </tr> 
 </tbody> 
</table>
