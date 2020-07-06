---
description: Una classificazione è un modo per classificare  dati variabili Analytics e quindi visualizzare i dati in modi diversi al momento della generazione dei rapporti.
subtopic: Classifications
title: Informazioni sulle classificazioni
topic: Admin tools
uuid: abc1a1be-8e37-4b7e-81fd-3e99ac27fc6a
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 20%

---


# Informazioni sulle classificazioni

Una classificazione è un modo per classificare  dati variabili Analytics e quindi visualizzare i dati in modi diversi al momento della generazione dei rapporti.

Video introduttivo sulle classificazioni [Analytics](https://video.tv.adobe.com/v/16853/?captions=ita).

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > *`<Traffic or Conversion>`*

Quando si classifica, si crea una relazione tra la variabile e i metadati correlati a tale variabile. Le classificazioni vengono utilizzate più frequentemente nelle campagne. I dati raccolti utilizzando le informazioni sulle variabili (eVar, prop ed eventi) possono essere aggregati applicando metadati ai valori raccolti nelle variabili.

![Informazioni sul passaggio](assets/sub_class_create.png)

Una volta classificato, qualsiasi rapporto che puoi generare utilizzando la variabile chiave può essere generato anche utilizzando gli attributi associati. Ad esempio, potete classificare [!UICONTROL Product IDs] con attributi di prodotto aggiuntivi, quali nome del prodotto, colore, dimensione, descrizione e SKU. L&#39;aumento dei dati di reporting e analisi con attributi aggiuntivi offre opportunità di reporting più approfondite e complesse.

>[!IMPORTANT]
>
>La possibilità di importare le classificazioni Numeriche 2 e Abilitate per data è stata rimossa dal codebase. Questa modifica entrerà in vigore con la versione di manutenzione di giugno 2019. Se nel file di importazione sono presenti colonne numeriche o abilitate per data, tali celle verranno automaticamente ignorate e gli altri dati del file verranno importati come di consueto. Le classificazioni esistenti possono ancora essere esportate attraverso il flusso di lavoro di classificazione standard e continueranno a essere disponibili nei rapporti.

>[!NOTE]
>
>Nella versione di manutenzione di Analytics del 10 maggio 2018, Adobe ha iniziato a limitare le funzionalità delle classificazioni numeriche e abilitate per le date. Questi tipi di classificazione sono stati rimossi dalle interfacce Admin (Amministratore) e Classification Importer (Importazione classificazione). Non è possibile aggiungere nuove classificazioni numeriche e abilitate per le date. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti.

Dopo aver creato le classificazioni, puoi sfruttare i nuovi attributi di dati in Adobe  Analytics.

**Esempio di codici di tracciamento**

Supponiamo che, invece di visualizzare le campagne solo tramite il codice di tracciamento, sia necessario visualizzare i risultati delle campagne tramite Motore di ricerca, Parola chiave e Canale campagna. Invece di dedicare le variabili di conversione per ciascuna di queste, potete creare tre classificazioni della variabile della campagna per rappresentare il motore di ricerca, la parola chiave e il canale della campagna. Questa strategia consente di visualizzare gli eventi di successo del sito per tutte e quattro le variabili, senza tag aggiuntivi.

Reporting e analisi include classificazioni predefinite per la variabile del codice di tracciamento, che offre rapporti basati sulla classificazione denominati Creative Elements e Campagne. Devi configurare manualmente le classificazioni per tutte le altre variabili di conversione e di traffico.

Consulta Classificazioni [del traffico e classificazioni](/help/admin/admin/c-traffic-variables/traffic-classifications.md) [](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html)di conversione.

Nella tabella seguente sono descritti i diversi tipi di classificazioni disponibili e i tipi di variabili che li supportano. Esaminare le informazioni in Struttura [file](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) generale prima di caricare i file di dati.

<table id="table_279728C28D9C40EE832ACC9F211B5F17"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>TYPE </p> </th> 
   <th colname="col2" class="entry"> <p>DISPONIBILITÀ </p> </th> 
   <th colname="col3" class="entry"> <p>DESCRIPTION </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Testo</span> </p> </td> 
   <td colname="col2"> <p>Variabili di conversione e traffico </p> </td> 
   <td colname="col3"> <p>Le classificazioni di testo definiscono una categoria che consente di raggruppare i dati variabili a fini di reporting. </p> <p>Ad esempio, se vendi camicie, potresti voler classificare le vendite di magliette (conversioni) per colore, dimensione e stile in modo da poter generare report che ti consentano di visualizzare le vendite di camicie organizzate in base a queste categorie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Testo con data abilitata</span> </p> <p>Nota:  Nella versione di manutenzione di Analytics del 10 maggio 2018,  Adobe ha iniziato a limitare le funzionalità delle classificazioni abilitate per le date. Questi tipi di classificazione sono stati rimossi dalle interfacce Admin (Amministratore) e Classification Importer (Importazione classificazione). Non è possibile aggiungere nuove classificazioni abilitate per le date. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti. </p> </td> 
   <td colname="col2"> <p>Variabili di conversione </p> </td> 
   <td colname="col3"> <p>Una classificazione di testo abilitata per la data consente di assegnare intervalli di date a una classificazione di testo. Questa funzione è in genere utilizzata con le classificazioni delle campagne, in modo da poter sfruttare la visualizzazione Diagramma di Gantt nel rapporto <span class="wintitle"> Campagne</span> . </p> <p>È possibile includere nel file di dati le date effettive della campagna per la compilazione dei dati di classificazione. </p> <p>Reporting e  Analytics raccoglie i codici di tracciamento campagna anche se la data di fine della campagna è già passata, ma i dati della campagna raccolti dopo la data di fine della campagna non sono associati alla campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Numeriche</span> <p>Nota:  Nella versione di manutenzione di Analytics del 10 maggio 2018,  Adobe ha iniziato a limitare le funzionalità delle classificazioni numeriche. Questi tipi di classificazione sono stati rimossi dalle interfacce Admin (Amministratore) e Classification Importer (Importazione classificazione). Non è possibile aggiungere nuove classificazioni numeriche. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti. </p> </p> </td> 
   <td colname="col2"> <p>Variabili di conversione </p> </td> 
   <td colname="col3"> <p>Le classificazioni numeriche consentono di applicare valori numerici fissi ai rapporti <span class="wintitle"> Conversione</span> . Tali classificazioni vengono visualizzate come metriche nei report. </p> <p>Quando si considera l'aggiunta di una classificazione <span class="wintitle"> Numerica</span> , il valore numerico deve essere fisso e immutabile nel tempo. </p> </td> 
  </tr> 
 </tbody> 
</table>

