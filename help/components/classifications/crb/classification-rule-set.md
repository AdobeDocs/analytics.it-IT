---
description: Un set di regole è un gruppo di regole di classificazione per una variabile specifica. Al set di regole viene applicata una variabile. Per creare più set di regole per una variabile, è necessario applicare ciascun set di regole a più suite di rapporti.
subtopic: Classifications
title: Set di regole di classificazione
feature: Strumenti di amministrazione
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 100%

---


# Set di regole di classificazione

Un set di regole è un gruppo di regole di classificazione per una variabile specifica. Al set di regole viene applicata una variabile. Per creare più set di regole per una variabile, è necessario applicare ciascun set di regole a più suite di rapporti.

## Pagina del generatore di regole di classificazione {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

I campi e le opzioni seguenti sono disponibili nel [!UICONTROL Classifications Rule Builder].

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/components/classifications/crb/classification-rule-set.md"  > Aggiungi set di regole</a> </p> </td> 
   <td colname="col2"> <p>Crea un set di regole. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regole </p> </td> 
   <td colname="col2"> Visualizza il numero di regole contenute nel set. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato </p> </td> 
   <td colname="col2"> Visualizza lo stato dell’attività del set di regole, ad esempio Bozza o Attivo. Le regole attive vengono elaborate ogni giorno ed esaminano i dati di classificazione che risalgono in genere a un mese. Le regole verificano automaticamente la presenza di nuovi valori e caricano le classificazioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ultima modifica </p> </td> 
   <td colname="col2"> Indica quando è stato modificato il set di regole. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duplica </p> </td> 
   <td colname="col2"> Duplica (copia) un set di regole in modo da poterlo applicare a un’altra variabile o alla stessa variabile in una suite di rapporti diversa. </td> 
  </tr> 
 </tbody> 
</table>

## Creare un set di regole di classificazione {#create-classification-rule-set}

Denomina il set di regole di classificazione, applica la variabile e specifica le impostazioni di sovrascrittura.

1. (Prerequisito) Definisci la struttura di classificazione in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

   Consulta [Classificazioni](https://docs.adobe.com/content/help/it-IT/analytics/components/classifications/c-classifications.html) nella guida degli Strumenti di amministrazione per l’aggiunta di classificazioni.

   Le variabili vengono visualizzate nel pannello [!UICONTROL New Rule Set] solo dopo che è stata definita almeno una classificazione per quella variabile.

   Puoi creare classificazioni su una variabile in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Traffic]** > **[!UICONTROL Traffic Classifications]** (o **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**). Seleziona quindi la variabile e fai clic su **[!UICONTROL Add Classification]**.

1. Per creare il set di regole, fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]** > **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. Denomina il set di regole, quindi fai clic su **[!UICONTROL Create Rule Set]**.
1. Seleziona il set di regole per la modifica.

   ![](assets/classification_rules_page.png)

1. Fai clic su **[!UICONTROL Select Report Suites and Variables]**.

   La suite di rapporti e l’elenco delle variabili vengono compilati con tutte le variabili classificate disponibili in tutte le suite di rapporti dell’azienda di accesso. Una singola variabile in una suite di rapporti può appartenere a un solo set di regole.

   Per ulteriori informazioni, consulta *`Variable`* nelle definizioni della pagina [Generatore di regole di classificazione](/help/components/classifications/crb/classification-rule-definitions.md).
1. Specifica le suite di rapporti e le variabili da utilizzare, quindi fai clic su **[!UICONTROL Save]**.
1. Continua [aggiungendo regole di classificazione](/help/components/classifications/crb/classification-rule-set.md) al set di regole.
