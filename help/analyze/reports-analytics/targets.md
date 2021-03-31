---
description: Gli obiettivi consentono di misurare le prestazioni del sito web e tenere traccia dell’avanzamento rispetto agli obiettivi target. Ad esempio, potrebbe essere utile aumentare il numero di visitatori provenienti da un’area geografica, le entrate per ordine o il numero di hit derivanti da un referente specifico.
title: Target
uuid: bfe29dc8-8da8-4107-8bb1-4a7494f12bc9
feature: Nozioni di base su Reports & Analytics
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 2%

---


# Target

Gli obiettivi consentono di misurare le prestazioni del sito web e tenere traccia dell’avanzamento rispetto agli obiettivi target. Ad esempio, potrebbe essere utile aumentare il numero di visitatori provenienti da un’area geografica, le entrate per ordine o il numero di hit derivanti da un referente specifico.

## Target {#concept_6516E81923E845198B7FC5D8F81DC35C}

Gli obiettivi consentono di misurare le prestazioni del sito web e tenere traccia dell’avanzamento rispetto agli obiettivi target. Ad esempio, potrebbe essere utile aumentare il numero di visitatori provenienti da un’area geografica, le entrate per ordine o il numero di hit derivanti da un referente specifico.

Quando crei dei target, seleziona le metriche attributo o eVar da misurare oppure puoi scegliere di misurare l’intero sito rispetto alla metrica selezionata.

Ad esempio, puoi misurare il numero di visitatori univoci del sito web e utilizzarlo come destinazione. In questo caso, scegli l’intero sito web. Tuttavia, se desideri eseguire il targeting del numero di visitatori unici del tuo sito web da Chicago, puoi specificare tale eVar anziché guardare l’intero sito.

## Descrizioni dei campi di destinazione {#section_44DFFB4A7AC54D65BC2345411686B2AD}

**[!UICONTROL Analytics]** (Analytics) > **[!UICONTROL Components]** (Componenti) > **[!UICONTROL Targets]** (Progetti programmati).

Descrizioni dei campi e delle opzioni nella pagina [!UICONTROL Add/Edit Target].

<table id="table_E08728BECC204DF59F0AC99957A68CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Target Nome </td> 
   <td colname="col2">Specifica un nome di destinazione, che viene visualizzato nella pagina <span class="wintitle"> Target Manager</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Applica a </td> 
   <td colname="col2"> Consente di applicare il target a tutto il sito o a un attributo o eVar selezionato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seleziona elemento </td> 
   <td colname="col2"> <p>Visualizza il modulo di selezione per l'attributo o l'eVar selezionato, in modo da poter eseguire una ricerca avanzata per gli elementi correlati. Ad esempio, se si seleziona l'eVar <span class="uicontrol"> Nazioni</span>, l'elenco di voci consente di specificare quale paese. Se si seleziona l'eVar <span class="uicontrol"> Prodotti</span>, l'elenco delle voci consente di specificare quale prodotto. Le variabili di informazioni personalizzate sono elencate anche nel menu . Se hai una variabile di insight personalizzata impostata per misurare gli intervalli di età dei visitatori, l’elenco degli elementi visualizza gli intervalli delle pagine, ad esempio 18-24, 25-35 e così via. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metrica </td> 
   <td colname="col2">Consente di applicare il target a una metrica. Questo menu visualizza solo le metriche applicabili a un dato eVar. Ad esempio, se selezioni <span class="uicontrol"> Prodotti</span> come eVar, una metrica come <span class="uicontrol"> Uscite pagina</span> non si applica a essa. La metrica <span class="uicontrol"> Uscite pagina</span> può essere applicata a un eVar di pagina web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Punto </td> 
   <td colname="col2"> <p>Consente di definire le impostazioni <span class="uicontrol"> Intervallo date</span> e <span class="uicontrol"> Granularità</span> del target. A seconda delle specifiche dell’intervallo di date, alcune opzioni di granularità non sono applicabili. Quando digiti dei valori per le metriche, digita un valore per ciascuna impostazione di granularità. Ad esempio, se l’intervallo di date è il mese di febbraio e la selezione della granularità è settimanale, digita un valore per ogni settimana del mese di febbraio. I rapporti di destinazione vengono visualizzati per ogni impostazione di granularità. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori </td> 
   <td colname="col2"> <p>Consente di specificare i valori di destinazione per il periodo di tempo e la metrica selezionata. Questo valore sono i numeri di destinazione che si sta tentando di raggiungere. Ad esempio, se il target si basa su ricavi e si mirava a $ 10.000 di ricavi per un dato mese, si immetterebbero 10.000 nel campo del valore per il mese. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aggiungere una destinazione {#task_94915391E26E4F808F2538AA92BC7E71}

Passaggi che descrivono come aggiungere un target.

<!-- 

t_add_a_target.xml

 -->

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Targets]**.
1. Nella pagina [!UICONTROL Target Manager], fai clic su **[!UICONTROL Add New]**.
1. Configura le opzioni descritte in [Descrizioni dei campi di destinazione](/help/analyze/reports-analytics/targets.md#section_44DFFB4A7AC54D65BC2345411686B2AD).
1. Fai clic su **[!UICONTROL OK]**.

## Modificare una destinazione {#task_946C558D2ECC4922ABD4A5A6183A095A}

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Targets]**.
1. Nella colonna **[!UICONTROL Manage]**, fai clic sull&#39;icona **[!UICONTROL Edit]**.
1. Configura le opzioni descritte in [Descrizioni dei campi di destinazione](/help/analyze/reports-analytics/targets.md#section_44DFFB4A7AC54D65BC2345411686B2AD).
1. Fai clic su **[!UICONTROL OK]**.
