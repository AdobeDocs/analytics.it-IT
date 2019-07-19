---
description: Un set di regole è un gruppo di regole di classificazione per una variabile specifica. Potete applicare una variabile al set di regole. Se desiderate creare più set di regole per una variabile, dovete applicare ogni regola impostata a più suite di rapporti.
seo-description: Un set di regole è un gruppo di regole di classificazione per una variabile specifica. Potete applicare una variabile al set di regole. Se desiderate creare più set di regole per una variabile, dovete applicare ogni regola impostata a più suite di rapporti.
seo-title: Set di regole di classificazione
solution: Analytics
subtopic: Classificazioni
title: Set di regole di classificazione
topic: Strumenti di amministrazione
uuid: c 4 d 7 b 77 c-fa 98-44 be -955 f -9 aee 7 f 73480 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Set di regole di classificazione

Un set di regole è un gruppo di regole di classificazione per una variabile specifica. Potete applicare una variabile al set di regole. Se desiderate creare più set di regole per una variabile, dovete applicare ogni regola impostata a più suite di rapporti.

## Classification rule sets {#concept_CD3D510F5070486584F3BB535AE41524}

Un set di regole è un gruppo di regole di classificazione per una variabile specifica. Potete applicare una variabile al set di regole. Se desiderate creare più set di regole per una variabile, dovete applicare ogni regola impostata a più suite di rapporti.

## Classification Rule Builder Page {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]**

The following fields and options are available on the [!UICONTROL Classifications Rule Builder].

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B" format="dita" scope="local"> Aggiungi set di regole</a> </p> </td> 
   <td colname="col2"> <p>Crea un set di regole. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regole </p> </td> 
   <td colname="col2"> Visualizza il numero di regole contenute nel set. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato </p> </td> 
   <td colname="col2"> Visualizza lo stato dell'attività del set di regole, ad esempio Bozza o Attivo. Le regole attive vengono elaborate ogni giorno, esaminando in genere i dati di classificazione di un mese. Le regole verificano automaticamente nuovi valori e caricano le classificazioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ultima modifica </p> </td> 
   <td colname="col2"> Indica la data di modifica del set di regole. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duplica </p> </td> 
   <td colname="col2"> Duplica (copia) un set di regole, per applicare il set di regole a un'altra variabile o alla stessa variabile in una suite di rapporti diversa. </td> 
  </tr> 
 </tbody> 
</table>

## Create a Classification Rule Set {#task_86F216DFD2534FA181E64ABDF306782B}

<!-- 

t_classification_rule_set.xml

 -->

Denominate il set di regole di classificazione, applicate la variabile e specificate le impostazioni di sovrascrittura.

1. (Prerequisite) Define the classification structure in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.

   (See [Classifications](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=classifications) in Admin Tools help on adding classifications.)

   Variables will display in the [!UICONTROL New Rule Set] panel only after they have at least one classification defined for that variable.

   You can create classifications on a variable in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Traffic]** &gt; **[!UICONTROL Traffic Classifications]** (or **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**). Then select the variable, then click **[!UICONTROL Add Classification]**.

1. To create the rule set, click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]** &gt; **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. Name the rule set, then click **[!UICONTROL Create Rule Set]**.
1. Selezionate il set di regole per la modifica.

   ![](assets/classification_rules_page.png)

1. Fai clic su **[!UICONTROL Select Report Suites and Variables]**.

   La suite di rapporti e l'elenco variabile sono popolati con tutte le variabili classificate disponibili in tutte le suite di rapporti della tua società di accesso. Una singola variabile in una suite di rapporti può appartenere a un solo set di regole.

   See *`Variable`* in the definitions for the [Classification Rule Builder](../../../components/c-classifications2/crb/classification-rule-definitions.md#section_4D1A70A607C9419EB2116A5174EACB72) page for more information.
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. Continue by [adding classification rules](../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B) to the rule set.
