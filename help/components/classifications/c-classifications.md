---
title: Panoramica delle classificazioni
description: Personalizza il raggruppamento di elementi dimensionali.
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 98%

---

# Panoramica delle classificazioni

Una classificazione è un modo per classificare i dati delle variabili di Analytics e visualizzarli in modi diversi quando si generano i rapporti.

Panoramica video delle [classificazioni di Analytics](https://video.tv.adobe.com/v/16853/).

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > *`<Traffic or Conversion>`*

La classificazione crea una relazione tra la variabile e i metadati correlati a essa. Le classificazioni vengono utilizzate soprattutto nelle campagne. I dati raccolti utilizzando le informazioni delle variabili (eVar, prop ed eventi) possono essere raggruppati applicando i metadati ai valori raccolti nelle variabili.

![Informazioni sul passaggio](assets/sub_class_create.png)

Una volta effettuata la classificazione, qualsiasi rapporto che puoi generare utilizzando la variabile chiave può essere generato anche utilizzando gli attributi associati. Ad esempio, puoi classificare i [!UICONTROL Product IDs] con attributi di prodotto aggiuntivi, quali nome del prodotto, colore, dimensione, descrizione e SKU. Il potenziamento dei dati di Reports and Analytics con attributi aggiuntivi offre opportunità di reporting più approfondite e complesse.

Dopo aver creato le classificazioni, puoi sfruttare i nuovi attributi di dati in Adobe Analytics.

## Esempio di codici di tracciamento

Supponiamo che, invece di visualizzare le campagne solo tramite il codice di tracciamento, desideri visualizzare i risultati delle campagne per motore di ricerca, parola chiave e canale della campagna. Invece di utilizzare variabili di conversione per ciascuno di questi, puoi creare tre classificazioni della variabile della campagna per rappresentare motore di ricerca, parola chiave e canale della campagna. Questa strategia consente di visualizzare gli eventi di successo del sito per tutte e quattro le variabili, senza tag aggiuntivi.

Reports and Analytics include classificazioni predefinite per la variabile del codice di tracciamento, che offre rapporti basati sulle classificazioni denominati Elementi creativi e Campagne. Devi configurare manualmente le classificazioni per tutte le altre variabili di conversione e di traffico.

Consulta [Classificazioni di traffico](/help/admin/admin/c-traffic-variables/traffic-classifications.md) e [Classificazioni di conversione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html).

Nella tabella seguente sono descritti i diversi tipi di classificazioni disponibili e i tipi di variabili che li supportano. Consulta le informazioni in [Struttura generale dei file](/help/components/classifications/importer/c-saint-data-files.md) prima di caricare i file di dati.

<table id="table_279728C28D9C40EE832ACC9F211B5F17"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>TIPO </p> </th> 
   <th colname="col2" class="entry"> <p>DISPONIBILITÀ </p> </th> 
   <th colname="col3" class="entry"> <p>DESCRIZIONE </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Testo</span> </p> </td> 
   <td colname="col2"> <p>Variabili di conversione e di traffico </p> </td> 
   <td colname="col3"> <p>Le classificazioni di testo definiscono una categoria che consente di raggruppare i dati delle variabili a fini di reporting. </p> <p>Ad esempio, se vendi magliette, potresti voler classificare le vendite di magliette (conversioni) per colore, taglia e stile in modo da poter generare rapporti che ti consentano di visualizzare le vendite organizzate in base a queste categorie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Testo con data abilitata</span> </p> <p>Nota: nella versione di manutenzione di Analytics del 10 maggio 2018, Adobe ha iniziato a limitare le funzionalità delle classificazioni con data abilitata. Le classificazioni di questo tipo sono state rimosse dalle interfacce Admin e Importazione delle classificazioni. Non è possibile aggiungere nuove classificazioni con data abilitata. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti. </p> </td> 
   <td colname="col2"> <p>Variabili di conversione </p> </td> 
   <td colname="col3"> <p>È possibile aggiungere intervalli di date a una classificazione di testo con data abilitata. Questa funzione è in genere utilizzata con le classificazioni delle campagne, in modo da poter sfruttare la visualizzazione a diagramma di Gantt nel rapporto <span class="wintitle">Campagne</span>. </p> <p>Puoi includere le date effettive della campagna nel file di dati per la compilazione dei dati di classificazione. </p> <p>Reports &amp; Analytics raccoglie i codici di tracciamento della campagna anche se la data di fine è già passata, ma i dati della campagna raccolti dopo la data di fine non sono associati alla campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Numeriche</span> <p>Nota: nella versione di manutenzione di Analytics del 10 maggio 2018, Adobe ha iniziato a limitare le funzionalità delle classificazioni numeriche. Le classificazioni di questo tipo sono state rimosse dalle interfacce Admin e Importazione delle classificazioni. Non è possibile aggiungere nuove classificazioni numeriche. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti. </p> </p> </td> 
   <td colname="col2"> <p>Variabili di conversione </p> </td> 
   <td colname="col3"> <p>Le classificazioni numeriche consentono di applicare valori numerici fissi ai rapporti <span class="wintitle">Conversione</span>. Tali classificazioni vengono visualizzate come metriche nei rapporti. </p> <p>Quando consideri di aggiungere una classificazione <span class="wintitle">numerica</span>, il valore numerico deve rimanere fisso e immutabile nel tempo. </p> </td> 
  </tr> 
 </tbody> 
</table>
