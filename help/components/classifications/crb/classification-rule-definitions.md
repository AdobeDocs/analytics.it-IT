---
description: Definizioni degli elementi dell’interfaccia nelle pagine del Generatore di regole di classificazione.
subtopic: Classifications
title: 'Regole di classificazione: definizioni'
feature: Strumenti di amministrazione
uuid: 77af8669-6e11-435c-9cc3-b03eb627c855
exl-id: 514501d1-7e1b-45da-b8fe-c68331e59dab
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 24%

---

# Regole di classificazione: definizioni

Definizioni degli elementi dell’interfaccia nelle pagine del Generatore di regole di classificazione.

## Pagina delle regole {#section_4A5BF384EEEE4994B6DC888339833529}

In questa pagina vengono visualizzate le regole in un set di regole.

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
   <td colname="col2"> <p><b>Suite di rapporti</b> </p> <p>Le suite di rapporti a cui si applica il set di regole. </p> <p><b>Variabile</b> </p> <p>Puoi applicare una sola variabile quando crei un set di regole di classificazione. Per creare più set di regole per una variabile, è necessario applicare ciascun set di regole a più suite di rapporti. </p> <p>Nota: Puoi utilizzare solo le variabili a cui hai accesso nelle suite di rapporti. Le variabili vengono visualizzate nel pannello <span class="wintitle"> Nuovo set di regole</span> solo dopo che è stata definita almeno una classificazione per quella variabile. </p> <p> Puoi creare classificazioni su una variabile in <span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Report Suites</span> &gt; <span class="uicontrol"> Traffic</span> &gt; <span class="uicontrol"> Traffic Classifications</span> (o <span class="uicontrol"> Conversion</span> &gt; <span class="uicontrol"> Conversion Classifications</span>). Quindi seleziona la variabile , quindi fai clic su <span class="uicontrol"> Aggiungi classificazione</span>. </p> <p>Consulta <a href="https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-classifications.html"  > Classificazioni di traffico</a> e <a href="https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html"  > Classificazioni di conversione</a> nella Guida dell'amministratore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Attiva</span> </p> </td> 
   <td colname="col2"> <p>Convalida e attiva una regola. Le regole attive vengono elaborate ogni giorno ed esaminano i dati di classificazione che risalgono in genere a un mese. Le regole verificano automaticamente la presenza di nuovi valori e caricano le classificazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Disattiva</span> </p> </td> 
   <td colname="col2"> <p>Disattiva le regole in modo da poterle modificare e testare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurare suite di rapporti e variabili </p> </td> 
   <td colname="col2"> <p>Visualizza la pagina <span class="wintitle"> Suite di rapporti disponibili</span>, in cui puoi selezionare una o più suite di rapporti disponibili da utilizzare per tutti i set di regole. (Questa pagina viene visualizzata anche quando esegui per la prima volta il <span class="wintitle"> Generatore regole di classificazione</span>.) </p> <p>Questa funzione ha lo scopo di ridurre il tempo di caricamento della suite di rapporti, nel caso in cui siano disponibili centinaia di suite di rapporti. </p> <p>Le suite di rapporti selezionate vengono rese disponibili a livello di regola quando fai clic su <span class="uicontrol"> Aggiungi suite</span> durante la creazione di una regola. </p> <p>Nota: Una suite di rapporti diventa disponibile <span class="term"> solo</span> quando le suite di rapporti hanno almeno una classificazione definita per la variabile in <span class="wintitle"> Strumenti di amministrazione</span>. <p>(Per una spiegazione di questo prerequisito, consulta <span class="term"> Variable</span> in <a href="/help/components/classifications/crb/classification-rule-set.md"  > Classification Rule Sets</a> .) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole sovrascrivono eventuali valori esistenti </p> </td> 
   <td colname="col2"> <p> (Impostazione predefinita) Sovrascrivi sempre le chiavi di classificazione esistenti, comprese le classificazioni caricate tramite l’importazione (SAINT). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole sovrascrivono solo i valori non impostati </p> </td> 
   <td colname="col2"> <p>Compila solo celle vuote (non impostate). Le classificazioni esistenti non saranno modificate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervallo di lookback </p> </td> 
   <td colname="col2"> <p>Quando attivi e convalida le regole, puoi specificare se queste devono sovrascrivere le classificazioni esistenti per le chiavi interessate. (Sono interessate solo le chiavi classificate che sono state passate in precedenza in <span class="keyword"> Adobe Analytics</span> entro il periodo di tempo specificato.) </p> <p>Se non si specifica un intervallo di lookback <span class="term"></span>, le regole restituiscono un look indietro di circa un mese (a seconda del giorno corrente del mese). Le classificazioni esistenti non vengono mai sovrascritte a meno che tu non attivi questa opzione. </p> <p><b>Centro</b> sviluppo: I partner possono creare regole di classificazione nel  <span class="wintitle"> centro sviluppatori</span>. Queste regole vengono implementate quando il cliente attiva un'integrazione. In <span class="wintitle"> Dev Center</span>, l'opzione <span class="uicontrol"> Sovrascrivi da</span> consente al partner di specificare se il cliente può determinare il valore di sovrascrittura quando attiva o modifica un'integrazione. </p> <p>Per ulteriori informazioni sull’elaborazione delle regole, consulta <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Modalità di elaborazione delle regole</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Aggiungi regola </a> </td> 
   <td colname="col2"> <p>Consente di aggiungere regole al set di regole. </p> <p>Nota:  Se un valore viene confrontato due o più volte in un insieme di regole, il sistema utilizza l'ultima regola per classificare il valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Bozza</span> </td> 
   <td colname="col2"> Consente di specificare che una regola è in modalità bozza. Lo stato Bozza consente di verificare la regola prima di eseguirla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Duplica</span> </td> 
   <td colname="col2"> Duplica (copia) un set di regole in modo da poterlo applicare a un’altra variabile o alla stessa variabile in una suite di rapporti diversa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Set di regole di test  </a> </p> </td> 
   <td colname="col2"> <p>Consente di verificare la validità di un set di regole. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Condizione di corrispondenza</span> </td> 
   <td colname="col2"> Specifica le condizioni desiderate per la regola. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Azione di classificazione</span> </td> 
   <td colname="col2"> <p>Specifica l'azione da eseguire quando si verifica la condizione corrispondente. </p> <p>Ad esempio, imposta un Nome campagna su $2, che identifica la posizione 2 in un codice di tracciamento come Nome campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>Numero della regola. </p> <p>Per ulteriori informazioni, consulta <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Modalità di elaborazione delle regole</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Seleziona tipo di regola</span> </td> 
   <td colname="col2"> <p>Ogni set di regole si applica a una variabile specifica. Le selezioni valide sono: </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">Inizia con </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">Termina con </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">Contiene </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  >Regular Expression (Espressione regolare)</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Inserisci criteri di corrispondenza</span> </td> 
   <td colname="col2"> Il pattern di testo che si sta cercando in una chiave. Questi criteri possono essere termini di ricerca, caratteri o espressioni regolari. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Imposta classificazione</span> </td> 
   <td colname="col2"> La colonna di classificazione da impostare se i criteri di corrispondenza sono soddisfatti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Su</span> </td> 
   <td colname="col2"> Il valore da specificare per la colonna di classificazione selezionata se i criteri di corrispondenza sono soddisfatti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> Consente di cercare le regole. </td> 
  </tr> 
 </tbody> 
</table>

## Pagina con espressione regolare {#section_C932A5469E774841B2229965A154163C}

Puoi modificare le espressioni regolari nella pagina [!UICONTROL Regular Expression] .

![](assets/regex_tracking_code.png)

**Definizioni**

| Elemento | Descrizione |
|---|---|
| Chiave di esempio | Stringa di prova da utilizzare. Ad esempio, puoi creare una classificazione da caratteri specifici in un codice di tracciamento. È possibile far corrispondere caratteri, parole o pattern di caratteri specifici. |
| Gruppi di corrispondenza | mostra in che modo l’espressione regolare corrisponde ai caratteri dell’ID campagna, in modo da poter classificare una posizione nell’ID campagna. |
| Risultato della corrispondenza | Visualizza le parti di una stringa che corrispondono correttamente all&#39;espressione regolare. |

Consulta [Espressioni regolari nelle regole di classificazione](/help/components/classifications/crb/classification-quickstart-rules.md).

## Pagina di test {#section_EC926F97901C4E65901413F9683AA70A}

Questa pagina ti consente di sottoporre a test le regole in un set.

**Definizioni**

| Elemento | Descrizione |
|---|---|
| Esegui test | Quando verifichi il set di regole, utilizza le chiavi del rapporto per vedere in che modo saranno influenzate dal set di regole. |
| Filtro | Filtra i valori nel pannello [!UICONTROL Results] . |
