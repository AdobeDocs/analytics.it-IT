---
description: Le classificazioni vengono utilizzate per classificare i valori in gruppi e per creare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne di ricerca a pagamento in una categoria come i termini musicali pop e generare report sul successo di quella categoria in relazione a metriche come Istanze (click-through) e conversione in eventi di successo.
seo-description: Le classificazioni vengono utilizzate per classificare i valori in gruppi e per creare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne di ricerca a pagamento in una categoria come i termini musicali pop e generare report sul successo di quella categoria in relazione a metriche come Istanze (click-through) e conversione in eventi di successo.
seo-title: Classificazioni di conversione
solution: Analytics
subtopic: Classifications
title: Classificazioni di conversione
topic: Strumenti di amministrazione
uuid: 4c8726c9-f527-44e1-be01-8c7b3b5c20f0
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Classificazioni di conversione

Le classificazioni vengono utilizzate per classificare i valori in gruppi e per creare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne di ricerca a pagamento in una categoria come i termini musicali pop e generare report sul successo di quella categoria in relazione a metriche come Istanze (click-through) e conversione in eventi di successo.

## Classificazioni di conversione {#concept_B4B1478A8CB540599AC9D4A58CA4B6FE}

Le classificazioni vengono utilizzate per classificare i valori in gruppi e per creare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne di ricerca a pagamento in una categoria come i termini *musicali* pop e generare report sul successo di quella categoria in relazione a metriche come Istanze (click-through) e conversione in eventi di successo.

Le classificazioni di conversione consentono di classificare le variabili di conversione. Una volta classificati, qualsiasi rapporto che è possibile generare utilizzando i dati chiave può essere generato anche utilizzando le proprietà dati associate.

Dopo aver attivato le classificazioni, utilizzare Importazione [](../../components/c-classifications2/c-classifications-importer/c-working-with-saint.md#concept_08ED8C7A86C64E7DA5DE3044BB94B2EA) classificazione per assegnare valori specifici alla classificazione appropriata.

## Descrizioni classificazioni conversione {#section_4A98DD5F5C314B9DAEE710AEE4EE51D4}

<table id="table_0B72C485467348E2A34BF913441F4AF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nome</span> </td> 
   <td colname="col2"> Nome della classificazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Data Attivata (Solo Testo)</span> </td> 
   <td colname="col2"> <p>Indica se la classificazione di testo è un intervallo di date per le variabili della campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Opzioni (solo testo)</span> </td> 
   <td colname="col2">Crea un elenco di valori di classificazione disponibili per questa classificazione. Utilizzate <span class="wintitle"> Opzioni</span> con variabili di campagna per fornire agli utenti un elenco di valori supportati per la classificazione in <span class="wintitle"> Campaign Manager</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tipo di numero (solo numerico)</span> </td> 
   <td colname="col2">Specifica il tipo di numero nella classificazione numerica. Le opzioni includono <span class="wintitle"> Numerico</span>, <span class="wintitle"> Percentuale</span>e <span class="wintitle"> Valuta</span>. </td> 
  </tr> 
 </tbody> 
</table>

## Aggiungi classificazioni conversione {#task_D535D09E3EAF4CD1A15A6B93C0BB1BB5}

<!-- 

t_classification_conversion.xml

 -->

Procedura che descrive come aggiungere classificazioni di conversione in Amministratore.

1. Fai clic su **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Seleziona una suite di rapporti.
1. Clic **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**.
1. Dall’elenco a **[!UICONTROL Select Classification Type]** discesa, selezionate la variabile in cui desiderate aggiungere una classificazione.

   ![Informazioni sul passaggio](assets/sub_class_create.png)

1. Passate il puntatore del mouse sull' **[!UICONTROL Edit Classification]** icona, quindi selezionate **[!UICONTROL Add Classification]**.
1. Nel **[!UICONTROL Select Type]** campo, selezionare il tipo di classificazione che si desidera aggiungere alla variabile.

   Le opzioni includono **[!UICONTROL Text]** e **[!UICONTROL Numeric]**. Per ulteriori informazioni sui tipi di classificazione, vedere [Informazioni sulle classificazioni](../../components/c-classifications2/c-classifications.md#concept_4CEC7FF1A9E24204A7DA6B9AC70709DE).
1. Nella finestra di **[!UICONTROL Text Classifications]** dialogo, configurare la classificazione come desiderato.

   Per informazioni su questi elementi, consultate Descrizioni [delle classificazioni di](../../components/c-classifications2/conversion-classifications.md#section_4A98DD5F5C314B9DAEE710AEE4EE51D4) conversione.

1. Nella finestra di **[!UICONTROL Dropdown List]** dialogo, aggiungere o rimuovere le opzioni.

   L'aggiunta di opzioni crea un elenco di valori di classificazione disponibili per questa classificazione. Puoi utilizzare questa opzione con le variabili Campaign per fornire agli utenti un elenco di valori supportati per la classificazione in Campaign Manager. Utilizzate questa opzione per le dimensioni di classificazione in cui è presente un numero limitato di valori consentiti che raramente o mai cambiano. Ad esempio, potete eseguire diverse campagne mirate a diversi livelli di fedeltà dei clienti: Argento, Oro e Platino. Potreste quindi utilizzare l'elenco a discesa per assicurarvi che gli unici valori accettati siano quelli che corrispondono ai vostri tre livelli. Se qualcuno tenta di utilizzare un valore diverso, viene eliminato.
1. Fai clic su **[!UICONTROL Save]**.

## Eliminare una classificazione di conversione {#task_566651BC245944618A6A833E58211FDE}

<!-- 

t_classification_delete_conversion.xml

 -->

Elimina una classificazione di conversione quando non è più necessaria.

1. Aprite il Gestore delle suite di rapporti facendo clic su **[!UICONTROL Admin]**&gt; **[!UICONTROL Report Suites]** nell’intestazione della suite.
1. Seleziona una suite di rapporti.
1. Clic **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**.
1. Dall’elenco a **[!UICONTROL Select Classification Type]** discesa, selezionate la variabile da cui desiderate eliminare una classificazione.
1. Passate il puntatore del mouse sull' **[!UICONTROL Edit Classification]** icona, quindi selezionate **[!UICONTROL Delete Classification]**.
1. Nella finestra di dialogo Elimina classificazione, fare clic su **[!UICONTROL Delete]**.
