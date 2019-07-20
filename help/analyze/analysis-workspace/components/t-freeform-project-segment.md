---
description: nulle
seo-description: nulle
seo-title: Segmenti
title: Segmenti
uuid: 677 f 6030-5 b 3 e -4 dfa-bb 79-9 f 27 f 3382 fb 1
translation-type: tm+mt
source-git-commit: f5f5b294f503911108e1693b7c6cd128bee659c6

---


# Segmenti {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## Segment rail {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

La barra dei segmenti nel menu Components (Componenti) mostra i segmenti e i modelli di segmenti, come indicato da queste icone:

![](assets/segment_icons.png)

[Utilizzo dei segmenti in Analysis Workspace su YouTube](https://www.youtube.com/watch?v=QlUCdQDnni4)(6:46)

## Create segments {#section_693CFADA668B4542B982446C2B4CF0F5}

Puoi creare all’istante dei segmenti rilasciando qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, segmento, modello di segmento, intervallo di date) nella zona di rilascio dei segmenti, nella parte superiore di un pannello.

I tipi di componente vengono automaticamente convertiti in segmenti. In alternativa, puoi fare clic sul simbolo “+” nella casella di riepilogo Aggiungi segmento.

Nota bene:

* Nella zona dei segmenti **non è possibile** rilasciare i tipi di componenti seguenti: metriche calcolate e dimensioni/metriche da cui non è possibile creare i segmenti.
* Per eventi e dimensioni intere, Analysis Workspace crea dei segmenti di hit di tipo “esiste”. Esempi: “Hit dove esiste eVar1” oppure “Hit dove esiste event1”.
* Se nella zona di rilascio del segmento non viene specificato "unspecified" o "none", viene automaticamente convertito in un segmento "non esiste" in modo che venga trattato correttamente nella segmentazione.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>I segmenti creati in questo modo sono interni al progetto.

Puoi scegliere di rendere questi segmenti pubblici (globali), seguendo questi passaggi:

1. Passa il mouse sul segmento nella zona di rilascio e fai clic sull’icona “i”.
1. In the information panel that displays, click **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Other methods for applying segments {#section_10FF2E309BA84618990EA5B473015894}

Esistono molti altri metodi per applicare i segmenti a un pannello a forma libera.

<table id="table_45B3839D70674430AF3AC5AA3134F825"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Azione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Crea segmenti dalla selezione </p> </td> 
   <td colname="col2"> <p>Crea un segmento in linea. Seleziona le righe, fai clic con il pulsante destro del mouse sulla selezione e crea un segmento in linea. Questo tipo di segmento si applica solo al progetto aperto e non viene salvato come segmento di Analytics. </p> <p> 
     <ol id="ol_1D1E661387354EBF992CC150915F642E"> 
      <li id="li_B96666FD426F4AEE8EAB61B2C00A07FB">Seleziona le righe. </li> 
      <li id="li_C2245B3EA81F4FAC88A33647922535AF">Fai clic con il pulsante destro del mouse sulla selezione. </li> 
      <li id="li_AB4F8988B9A84920ABA06A91094625F6">Fai clic su <span class="uicontrol">Create Segment from selection (Crea segmenti dalla selezione)</span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Componenti</span> &gt; <span class="uicontrol">Nuovo segmento</span> </td> 
   <td colname="col2"> <p>Visualizza il <span class="wintitle">Generatore di segmenti</span>. Per ulteriori informazioni sulla segmentazione, consulta <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html" format="https" scope="external">Generazione di segmenti</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="ignoretag"><span class="uicontrol"> Condividi</span> &gt; <span class="uicontrol">Condividi progetto</span></span> o </p> <p> <span class="ignoretag"><span class="uicontrol">Condividi</span> &gt; <span class="uicontrol">Cura dati progetto</span></span> </p> </td> 
   <td colname="col2"> <p>In <a href="../../../analyze/analysis-workspace/curate-share/curate.md#concept_4A9726927E7C44AFA260E2BB2721AFC6" format="dita" scope="local">Cura e condivisione</a>, i segmenti applicati al progetto sono disponibili al destinatario nelle analisi condivise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uso dei segmenti come dimensioni </p> </td> 
   <td colname="col2"> <p>Video: <a href="https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39" format="https" scope="external">Uso dei segmenti come dimensioni in Analysis Workspace</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

