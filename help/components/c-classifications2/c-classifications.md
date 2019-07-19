---
description: Una classificazione è un modo per categorizzare i dati variabili di Analytics, quindi visualizzare i dati in modi diversi quando generate rapporti.
seo-description: Una classificazione è un modo per categorizzare i dati variabili di Analytics, quindi visualizzare i dati in modi diversi quando generate rapporti.
seo-title: Informazioni sulle classificazioni
solution: Analytics
subtopic: Classificazioni
title: Informazioni sulle classificazioni
topic: Strumenti di amministrazione
uuid: abc 1 a 1 be -8 e 37-4 b 7 e -81 fd -3 e 99 ac 27 fc 6 a
translation-type: tm+mt
source-git-commit: 2d01f9edb976a57c18641fea03e01ad029893eea

---


# Informazioni sulle classificazioni

Una classificazione è un modo per categorizzare i dati variabili di Analytics, quindi visualizzare i dati in modi diversi quando generate rapporti.

Video overview of [Analytics Classifications](https://video.tv.adobe.com/v/16853/?captions=ita).

**[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; *`<Traffic or Conversion>`*

Durante la classificazione, si sta specificando una relazione tra la variabile e i metadati relativi a tale variabile. Le classificazioni vengono utilizzate più frequentemente nelle campagne. I dati raccolti utilizzando variabili (evar, prop ed eventi) possono essere aggiornati applicando metadati ai valori raccolti nelle variabili.

![Informazioni passo](assets/sub_class_create.png)

Una volta classificati, qualsiasi rapporto che è possibile generare utilizzando la variabile key può essere generato anche utilizzando gli attributi associati. For example, you can classify [!UICONTROL Product IDs] with additional product attributes, such as product name, color, size, description, and SKU. L'aumento dei dati di reporting e analisi con attributi aggiuntivi fornisce opportunità di reporting più avanzate e più complesse.

>[!IMPORTANT]
>
>La possibilità di importare le classificazioni Numeriche 2 e Abilitate per data è stata rimossa dal codebase. Questa modifica entrerà in vigore con la versione di manutenzione di giugno 2019. Se nel file di importazione sono presenti colonne numeriche o abilitate per data, tali celle verranno automaticamente ignorate e gli altri dati del file verranno importati come di consueto. Le classificazioni esistenti possono ancora essere esportate attraverso il flusso di lavoro di classificazione standard e continueranno a essere disponibili nei rapporti.

>[!NOTE]
>
>Nella versione del 10 maggio 2018 di Analytics, Adobe ha iniziato a limitare la funzionalità delle classificazioni numeriche e abilitate per le date. Questi tipi di classificazione sono stati rimossi dalle interfacce Admin (Amministratore) e Classification Importer (Importazione classificazione). Non è possibile aggiungere nuove classificazioni numeriche e abilitate per le date. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti.

Dopo aver creato le classificazioni, puoi sfruttare i nuovi attributi di dati in Adobe Analytics.

**Esempio di codici di tracciamento**

Supponiamo che invece di visualizzare le campagne solo per il codice di tracciamento, desideri vedere i risultati delle campagne tramite Motore di ricerca, Parola chiave e Canale campagna. Invece di disattivare le variabili di conversione per ciascuno di essi, puoi creare tre classificazioni della variabile della campagna per rappresentare Motore di ricerca, Parola chiave e Canale campagna. Questa strategia consente di visualizzare eventi di successo del sito da tutte e quattro le variabili, senza tag aggiuntivi.

Reporting e analisi includono classificazioni predefinite per la variabile del codice di tracciamento, che offre report basati sulla classificazione denominati Creative Elements e Campagne. Devi configurare manualmente le classificazioni per tutte le altre variabili di conversione e traffico.

See [Traffic Classifications](/help/admin/admin/c-traffic-variables/traffic-classifications.md) and [Conversion Classifications](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=conversion_classifications).

Nella tabella seguente sono descritti i diversi tipi di classificazioni disponibili e i tipi di variabili che li supportano. Review the information in [General File Structure](../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9EFF968DF5D244A887DE94075431C1BE) before uploading data files.

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
   <td colname="col3"> <p>Le classificazioni del testo definiscono una categoria che consente di raggruppare i dati variabili a scopo di reporting. </p> <p>Ad esempio, se vendete delle magliette, potete categorizzare le vendite delle magliette (conversioni) in base a colore, dimensioni e stile per generare rapporti che consentono di vedere le vendite di camicie organizzate in base a queste categorie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Testo abilitato per la data</span> </p> <p>Nota: Nella versione del 10 maggio 2018 di Analytics, Adobe ha iniziato a limitare la funzionalità delle classificazioni abilitate per le date. Questi tipi di classificazione sono stati rimossi dalle interfacce Admin (Amministratore) e Classification Importer (Importazione classificazione). Non è possibile aggiungere nuove classificazioni abilitate per date. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti. </p> </td> 
   <td colname="col2"> <p>Variabili di conversione </p> </td> 
   <td colname="col3"> <p>Una classificazione di testo abilitata per le date consente di assegnare intervalli di date a una classificazione testuale. This is typically used with campaign classifications so that you can take advantage of the Gantt chart view in the <span class="wintitle"> Campaigns</span> report. </p> <p>È possibile includere le date effettive della campagna nel file di dati che compila i dati di classificazione. </p> <p>Reporting e analisi raccoglie i codici di tracciamento campagna anche se la data di fine della campagna è già passata, ma i dati della campagna raccolti dopo la data di fine della campagna non sono associati alla campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Numeriche</span> <p>Nota: Nella versione del 10 maggio 2018 di Analytics, Adobe ha iniziato a limitare la funzionalità delle classificazioni numeriche. Questi tipi di classificazione sono stati rimossi dalle interfacce Admin (Amministratore) e Classification Importer (Importazione classificazione). Non è possibile aggiungere nuove classificazioni numeriche. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti. </p> </p> </td> 
   <td colname="col2"> <p>Variabili di conversione </p> </td> 
   <td colname="col3"> <p>Numeric classifications let you apply fixed numeric values to <span class="wintitle"> Conversion</span> reports. Queste classificazioni vengono visualizzate come metriche nei report. </p> <p>When considering whether to add a <span class="wintitle"> Numeric</span> classification, the numeric value must be fixed and unchanging over time. </p> </td> 
  </tr> 
 </tbody> 
</table>

