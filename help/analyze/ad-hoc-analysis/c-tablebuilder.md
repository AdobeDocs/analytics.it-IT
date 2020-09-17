---
description: Utilizzate il Generatore di tabelle per creare un rapporto con qualsiasi configurazione di metriche, dimensioni e segmenti. Ad esempio, puoi aggiungere più metriche al Generatore di tabelle, quindi applicare il segmento a tutte contemporaneamente. È possibile applicare elementi dai riquadri degli strumenti come righe e suddivisioni o come colonne e ruotare facilmente la tabella per una visualizzazione diversa. Dopo aver creato la tabella, puoi interagire direttamente con la tabella di dati risultante per un'ulteriore analisi. Tenere presente che la generazione di una tabella di dati dal Generatore tabelle esegue una query e crea una nuova tabella di dati.
title: Generatore tabella
uuid: d5dbd05e-9ebd-4571-b3a5-3856c28b65f3
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 2%

---


# Generatore tabella

>[!IMPORTANT]
>
> Adobe sta spostando  Ad Hoc Analysis a fine ciclo di vita il 1 marzo 2021. [Ulteriori informazioni...](https://adobe.ly/discoverworkspace).

Utilizzate il Generatore di tabelle per creare un rapporto con qualsiasi configurazione di metriche, dimensioni e segmenti. Ad esempio, puoi aggiungere più metriche al Generatore di tabelle, quindi applicare il segmento a tutte contemporaneamente. È possibile applicare elementi dai riquadri degli strumenti come righe e suddivisioni o come colonne e ruotare facilmente la tabella per una visualizzazione diversa. Dopo aver creato la tabella, puoi interagire direttamente con la tabella di dati risultante per un&#39;ulteriore analisi. Tenere presente che la generazione di una tabella di dati dal Generatore tabelle esegue una query e crea una nuova tabella di dati.

## Generatore tabella {#concept_574FEDC73B244101935D3C86C39DB70F}

Utilizzate il Generatore di tabelle per creare un rapporto con qualsiasi configurazione di metriche, dimensioni e segmenti. Ad esempio, puoi aggiungere più metriche al Generatore di tabelle, quindi applicare il segmento a tutte contemporaneamente. È possibile applicare elementi dai riquadri degli strumenti come righe e suddivisioni o come colonne e ruotare facilmente la tabella per una visualizzazione diversa. Dopo aver creato la tabella, puoi interagire direttamente con la tabella di dati risultante per un&#39;ulteriore analisi. Tenere presente che la generazione di una tabella di dati dal Generatore tabelle esegue una query e crea una nuova tabella di dati.

L&#39;opzione [!UICONTROL Table Builder] non è disponibile per alcuni report di percorso come [!UICONTROL Site Analysis], [!UICONTROL Fallout], [!UICONTROL Flow] e [!UICONTROL Virtual Focus].

## Descrizioni di Generatore di tabelle {#section_4B7B96546B864142AB91DF3996918590}

<table id="table_C11D78E62DEF48A78B50EFB8669817BC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Righe/Suddivisioni</span> </td> 
   <td colname="col2"> <p>Crea righe e suddivisioni da elementi aggiunti. Il primo elemento trascinato in <span class="wintitle"> Righe/Suddivisioni</span> diventa la colonna sinistra nella tabella di dati o l'elemento principale in una suddivisione. L'aggiunta di elementi successivi crea delle suddivisioni. </p> <p>Ad esempio, se aggiungi le dimensioni Pagina e Città, il rapporto suddivide la pagina per città. Per configurare il numero di righe e suddivisioni da visualizzare per ogni elemento, utilizzate i seguenti menu: </p> 
    <ul id="ul_702F215DFB814398B8F1879EDFEC103F"> 
     <li id="li_95C4DF2B33524C94BBD2E07397393300"> <span class="uicontrol"> Mostra</span> e <span class="uicontrol"> suddivisione</span>: Consente di specificare il numero di elementi e suddivisioni da visualizzare. </li> 
     <li id="li_D594C7F31A094D1EA1A070B80794E006"> <span class="uicontrol"> Predefinito</span>: Utilizza le impostazioni configurate in <span class="wintitle"> Proprietà</span>sottogruppo. </li> 
    </ul> <p>È inoltre possibile configurare un elenco di valori fissi per, ad esempio, suddividere una metrica per più metriche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Proprietà suddivisione</span> </td> 
   <td colname="col2"> <p><img placement="inline"  src="assets/Settings_Illustrative.png" id="image_C46860621CF94E88AF592B8660F28E57"> </img> </p> <p>Consente di specificare le impostazioni predefinite per il numero di righe e suddivisioni da visualizzare, in base all'ordine in cui vengono aggiunti gli elementi. È possibile specificare il numero totale di risultati per pagina da visualizzare e il numero di righe da suddividere. </p> <p>Le impostazioni effettuate in Generatore <span class="wintitle"> di</span> tabelle prevalgono su quelle predefinite nelle <span class="wintitle"> Proprietà</span>per sottogruppi di lavoro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Modifica elementi</span> </td> 
   <td colname="col2"> <p><img  src="assets/Edit_Buttcon.png" id="image_E44BCC4B0BFF453D8564047E3DA2501A"> </img> </p> <p>Scegliete un elenco di elementi dimensionali per creare un elenco fisso per le suddivisioni. Quando aggiungete elementi a questo elenco, questi diventano persistenti in un rapporto salvato e non verranno compressi quando aprite un rapporto salvato o pianificato. </p> <p>Vedere <a href="/help/analyze/ad-hoc-analysis/c-reports-configure.md#task_29BEE0AF09DA4625B9B44BAB77D7C841"  > Scomposizione dei dati</a>di tabella. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Colonne</span> </td> 
   <td colname="col2"> <p>Consente di creare colonne con elementi da dimensioni, segmenti e metriche. È inoltre possibile eseguire il pivot delle colonne utilizzando l'icona freccia, che consente di ruotare gli assi X e Y. </p> <p> <span class="uicontrol"> Mostra</span>: Consente di limitare il numero di colonne generate nella tabella di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Riepilogo</span> </td> 
   <td colname="col2"> <p>Mostra il layout strutturale del rapporto in modo da sapere quante righe e colonne verranno create. Il riepilogo riflette la configurazione specificata nei gruppi <span class="uicontrol"> Righe/Suddivisioni</span> e <span class="uicontrol"> Colonne</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Sostituisci tabella</span> </td> 
   <td colname="col2"> <p>Crea (e sostituisce) la tabella esistente, in base alla configurazione di <span class="wintitle"> Table Builder</span> . </p> <p>Nota: Facendo clic su <span class="uicontrol"> Sostituisci tabella</span> , il rapporto viene ripetuto e i dati vengono sostituiti nella griglia della tabella. Se si aggiungono elementi alla griglia di tabella, la correlazione tra la tabella e il Generatore <span class="wintitle"> di</span> tabelle non è più valida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Attenzione </td> 
   <td colname="col2"> <p><img id="image_619E1068C6084D41853DA3DD6B85DFC9"  src="assets/AlertRed_Illustrative.png" placement="inline" /> </p> <p>Indica che la configurazione di <span class="wintitle"> Table Builder</span>non restituirà dati o che non è selezionata alcuna metrica. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Generazione di un rapporto dal Generatore di tabelle {#task_B04801AC9848485C93DF02E96C9A9902}

Passaggi che descrivono l’utilizzo di [!UICONTROL Table Builder].

<!-- 

t_table_builder.xml

 -->

1. Per accedere al [!UICONTROL Table Builder]rapporto, esegui un rapporto supportato, quindi fai clic su **[!UICONTROL Table Builder]**.
1. Trascina gli elementi (dimensioni, metriche, segmenti) dai riquadri degli strumenti al pannello [!UICONTROL Table Builder].
1. Configurate gli elementi come righe, suddivisioni e colonne.
1. Click **[!UICONTROL Replace Table]** to generate the report.

   Facendo clic **[!UICONTROL Replace Table]** si esegue una nuova query e si crea una nuova tabella di dati. Le modifiche manuali alla tabella di dettaglio non vengono riportate nel Generatore di tabelle.

