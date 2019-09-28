---
description: Un set di regole è un gruppo di regole di classificazione per una specifica variabile. Si applica una variabile al set di regole. Per creare più set di regole per una variabile, è necessario applicare ciascun set di regole a più suite di rapporti.
seo-description: Un set di regole è un gruppo di regole di classificazione per una specifica variabile. Si applica una variabile al set di regole. Per creare più set di regole per una variabile, è necessario applicare ciascun set di regole a più suite di rapporti.
seo-title: Set di regole di classificazione
solution: Analytics
subtopic: Classificazioni
title: Set di regole di classificazione
topic: Strumenti di amministrazione
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Set di regole di classificazione

Un set di regole è un gruppo di regole di classificazione per una specifica variabile. Si applica una variabile al set di regole. Per creare più set di regole per una variabile, è necessario applicare ciascun set di regole a più suite di rapporti.

## Set di regole di classificazione {#concept_CD3D510F5070486584F3BB535AE41524}

Un set di regole è un gruppo di regole di classificazione per una specifica variabile. Si applica una variabile al set di regole. Per creare più set di regole per una variabile, è necessario applicare ciascun set di regole a più suite di rapporti.

## Classification Rule Builder Page {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]**

I campi e le opzioni seguenti sono disponibili sul [!UICONTROL Classifications Rule Builder].

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
   <td colname="col2"> Visualizza lo stato dell'attività del set di regole, ad esempio Bozza o Attivo. Le regole attive vengono elaborate ogni giorno, esaminando i dati di classificazione che risalgono in genere a un mese. Le regole verificano automaticamente la presenza di nuovi valori e caricano le classificazioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ultima modifica </p> </td> 
   <td colname="col2"> Indica quando è stato modificato il set di regole. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duplica </p> </td> 
   <td colname="col2"> Duplica (copia) un set di regole in modo da poter applicare il set di regole a un'altra variabile o alla stessa variabile in un'altra suite di rapporti. </td> 
  </tr> 
 </tbody> 
</table>

## Creare un set di regole di classificazione {#task_86F216DFD2534FA181E64ABDF306782B}

<!-- 

t_classification_rule_set.xml

 -->

Denominate il set di regole di classificazione, applicate la variabile e specificate le impostazioni di sovrascrittura.

1. (Prerequisito) Definite la struttura di classificazione in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.

   (vedere [Classificazioni](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) in Strumenti di amministrazione per l’aggiunta di classificazioni).

   Le variabili vengono visualizzate nel [!UICONTROL New Rule Set] pannello solo dopo che è stata definita almeno una classificazione per quella variabile.

   Potete creare classificazioni su una variabile in **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Traffic]** &gt; **[!UICONTROL Traffic Classifications]** (o **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**). Selezionate quindi la variabile e fate clic su **[!UICONTROL Add Classification]**.

1. Per creare il set di regole, fate clic su **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]** &gt; **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. Denominate il set di regole, quindi fate clic su **[!UICONTROL Create Rule Set]**.
1. Selezionare il set di regole per la modifica.

   ![](assets/classification_rules_page.png)

1. Fai clic su **[!UICONTROL Select Report Suites and Variables]**.

   La suite di rapporti e l'elenco delle variabili vengono compilati con tutte le variabili classificate disponibili in tutte le suite di rapporti della società di accesso. Una singola variabile in una suite di rapporti può appartenere a un solo set di regole.

   Per ulteriori informazioni, vedere *`Variable`* nelle definizioni della pagina [Generatore](../../../components/c-classifications2/crb/classification-rule-definitions.md#section_4D1A70A607C9419EB2116A5174EACB72) regole di classificazione.
1. Specifica le suite di rapporti e le variabili da utilizzare, quindi fai clic su **[!UICONTROL Save]**.
1. Continua [aggiungendo regole](../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B) di classificazione al set di regole.
