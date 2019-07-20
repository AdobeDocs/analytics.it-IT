---
description: Definizioni degli elementi dell'interfaccia nelle pagine del Generatore di regole di classificazione.
seo-description: Definizioni degli elementi dell'interfaccia nelle pagine del Generatore di regole di classificazione.
seo-title: Regole di classificazione - definizioni
solution: Analytics
subtopic: Classificazioni
title: Regole di classificazione - definizioni
topic: Strumenti di amministrazione
uuid: 77 af 8669-6 e 11-435 c -9 cc 3-b 03 eb 627 c 855
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Regole di classificazione - definizioni

Definizioni degli elementi dell'interfaccia nelle pagine del Generatore di regole di classificazione.

## Rules Page {#section_4A5BF384EEEE4994B6DC888339833529}

Questa pagina visualizza le regole in un set di regole.

![](assets/classification_rules_page.png)

**Definizioni**

<table id="table_2B3A8BB7BDE14836ACA6A1D444B011CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Selezione di suite per report e variabili </p> </td> 
   <td colname="col2"> <p><b>Suite di rapporti</b> </p> <p>Le suite di rapporti a cui si applica il set di regole. </p> <p><b>Variabile</b> </p> <p>Durante la creazione di un set di regole di classificazione è possibile applicare una sola variabile. Se desiderate creare più set di regole per una variabile, dovete applicare ogni regola impostata a più suite di rapporti. </p> <p>Nota: Puoi utilizzare solo le variabili a cui hai accesso nelle suite di rapporti. Variables will display in the <span class="wintitle"> New Rule Set</span> panel only after they have at least one classification defined for that variable. </p> <p>For example, to make <span class="term"> Pages</span> available as a variable to the rule set, ensure that the report suite has <a href="https://marketing.adobe.com/resources/help/en_US/reference/traffic_classifications.html" format="http" scope="external"> traffic classifications</a> implemented for <span class="term"> Page</span>. </p> <p> You can create classifications on a variable in <span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Report Suites</span> &gt; <span class="uicontrol"> Traffic</span> &gt; <span class="uicontrol"> Traffic Classifications</span> (or <span class="uicontrol"> Conversion</span> &gt; <span class="uicontrol"> Conversion Classifications</span>). Then select the variable, then click <span class="uicontrol"> Add Classification</span>. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=traffic_classification_admin" format="https" scope="external"> Traffic Classifications</a> and <a href="https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=conversion_classifications" format="https" scope="external"> Conversion Classifications</a> in Admin Help. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Attiva</span> </p> </td> 
   <td colname="col2"> <p>Convalida e attiva una regola. Le regole attive vengono elaborate ogni giorno, esaminando in genere i dati di classificazione di un mese. Le regole verificano automaticamente nuovi valori e caricano le classificazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Disattiva</span> </p> </td> 
   <td colname="col2"> <p>Disattiva le regole per modificarle e verificarle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurare suite di rapporti e variabili </p> </td> 
   <td colname="col2"> <p>Displays the <span class="wintitle"> Available Report Suites</span> page, where you can select one or more available report suites to use for all your rule sets. (This page also displays when you first run the <span class="wintitle"> Classification Rule Builder</span>.) </p> <p>Questa funzione è utile per ridurre il tempo di caricamento delle suite di rapporti, nel caso in cui si disponga di centinaia di suite di rapporti disponibili. </p> <p>The report suites you select here are made available at the rule level, when you click <span class="uicontrol"> Add Suites</span> when creating a rule. </p> <p>Note: A report suite becomes available <span class="term"> only</span> when the report suites have at least one classification defined for the variable in <span class="wintitle"> Admin Tools</span>. <p>(See <span class="term"> Variable</span> in <a href="../../../components/c-classifications2/crb/classification-rule-set.md#concept_CD3D510F5070486584F3BB535AE41524" format="dita" scope="local"> Classification Rule Sets</a> for an explanation about this prerequisite.) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole sovrascrivono eventuali valori esistenti </p> </td> 
   <td colname="col2"> <p> (Impostazione predefinita) Sovrascrive sempre le chiavi di classificazione esistenti, incluse le classificazioni caricate mediante l'importazione (SAINT). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole sovrascrivono solo i valori non impostati </p> </td> 
   <td colname="col2"> <p>Riempire solo le celle vuote (non impostate). Le classificazioni esistenti non saranno modificate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Finestra di lookback </p> </td> 
   <td colname="col2"> <p>Quando attivate e convalidate le regole, potete specificare se le regole devono sovrascrivere le classificazioni esistenti per le chiavi interessate. (Only classified keys that have been previously passed into <span class="keyword"> Adobe Analytics</span> within the time period you specify are affected.) </p> <p>If you to not specify a <span class="term"> lookback window</span>, the rules look back roughly one month (depending on current day of the month.) Le classificazioni esistenti non vengono mai sovrascritte, a meno che non attiviate questa opzione. </p> <p><b>Dev Center</b>: I partner possono creare regole di classificazione in <span class="wintitle"> Dev Center</span>. Queste regole vengono distribuite quando il cliente attiva un'integrazione. In the <span class="wintitle"> Dev Center</span>, the <span class="uicontrol"> Overwrite Since</span> option lets the partner specify whether the customer can determine the overwrite value when activating or editing an integration. </p> <p>See <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_A67A23F523844D37898583C632DB9D25" format="dita" scope="local"> How Rules Are Processed</a> for more information about rule processing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_86F216DFD2534FA181E64ABDF306782B" format="dita" scope="local"> Aggiungi regola </a> </td> 
   <td colname="col2"> <p>Consente di aggiungere regole al set di regole. </p> <p>Nota: Se un valore viene associato due o più volte in un set di regole, il sistema utilizza l'ultima regola per classificare il valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Bozza</span> </td> 
   <td colname="col2"> Consente di specificare che una regola è in modalità Bozza. Lo stato Bozza consente di verificare la regola prima di eseguirla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Duplica</span> </td> 
   <td colname="col2"> Duplica (copia) un set di regole, per applicare il set di regole a un'altra variabile o alla stessa variabile in una suite di rapporti diversa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_618A1E7CC8664E728F312250E8367158" format="dita" scope="local"> Set di regole di prova </a> </p> </td> 
   <td colname="col2"> <p>Consente di verificare la validità di un set di regole. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Condizione di corrispondenza</span> </td> 
   <td colname="col2"> Specifica le condizioni desiderate per la regola. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Azione di classificazione</span> </td> 
   <td colname="col2"> <p>Specifica l'azione da intraprendere quando si verifica la condizione corrispondenza. </p> <p>Ad esempio, impostate un Nome campagna su $ 2, che identifica la posizione 2 in un codice di tracciamento come Nome campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>Il numero di regole. </p> <p>See <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_A67A23F523844D37898583C632DB9D25" format="dita" scope="local"> How Rules Are Processed</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Seleziona tipo di regola</span> </td> 
   <td colname="col2"> <p>Ciascun set di regole si applica a una variabile specifica. Le selezioni valide sono: </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">Inizia con </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">Termina con </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">Contiene </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D" format="dita" scope="local"> Espressione regolare </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Inserire criteri di corrispondenza</span> </td> 
   <td colname="col2"> Il pattern di testo che stai cercando in una chiave. Questi criteri possono essere termini di ricerca, caratteri o espressioni regolari. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Imposta classificazione</span> </td> 
   <td colname="col2"> La colonna di classificazione che si desidera impostare se i criteri di corrispondenza sono soddisfatti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> A</span> </td> 
   <td colname="col2"> Il valore che si desidera specificare per la colonna di classificazione selezionata se i criteri di corrispondenza sono soddisfatti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> Consente di cercare regole. </td> 
  </tr> 
 </tbody> 
</table>

## Regular Expression Page {#section_C932A5469E774841B2229965A154163C}

You can edit regular expressions on the [!UICONTROL Regular Expression] page.

![](assets/regex_tracking_code.png)

**Definizioni**

| Elemento | Descrizione |
|---|---|
| Chiave di esempio | Stringa di prova da utilizzare. Ad esempio, è possibile creare una classificazione da caratteri specifici in un codice di tracciamento. È possibile associare caratteri, parole o pattern particolari di caratteri. |
| Corrispondenza gruppi | Mostra come l'espressione regolare corrisponde ai caratteri ID campagna, in modo da poter classificare una posizione nell'ID della campagna. |
| Risultato corrispondenza | Visualizza le parti di una stringa che corrispondono correttamente all'espressione regolare. |

See [Regular Expressions in Classification Rules](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D).

## Testing Page {#section_EC926F97901C4E65901413F9683AA70A}

Questa pagina consente di testare le regole in un set.

**Definizioni**

| Elemento | Descrizione |
|---|---|
| Eseguire il test | Quando sottoponete a test il set di regole, utilizzate le chiavi del report per vedere come verranno influenzate dal set di regole. |
| Filtro | Filters the values in the [!UICONTROL Results] panel. |

