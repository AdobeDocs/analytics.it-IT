---
description: Definizioni degli elementi dell'interfaccia nelle pagine del Generatore di regole di classificazione.
subtopic: Classifications
title: 'Regole di classificazione: definizioni'
topic: Admin tools
uuid: 77af8669-6e11-435c-9cc3-b03eb627c855
translation-type: tm+mt
source-git-commit: 89a5524ac0e96d63acd54c2ef3e22c17314f332d
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 5%

---


# Regole di classificazione: definizioni

Definizioni degli elementi dell&#39;interfaccia nelle pagine del Generatore di regole di classificazione.

## Pagina Regole {#section_4A5BF384EEEE4994B6DC888339833529}

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
   <td colname="col2"> <p><b>Suite di rapporti</b> </p> <p>Suite di rapporti a cui si applica il set di regole. </p> <p><b>Variabile</b> </p> <p>È possibile applicare una sola variabile quando si crea un set di regole di classificazione. Per creare più set di regole per una variabile, è necessario applicare ciascun set di regole a più suite di rapporti. </p> <p>Nota: Puoi utilizzare solo le variabili a cui hai accesso nelle suite di rapporti. Le variabili vengono visualizzate nel pannello <span class="wintitle"> Nuovo set</span> di regole solo dopo che è stata definita almeno una classificazione per quella variabile. </p> <p> Puoi creare classificazioni su una variabile in <span class="uicontrol"> Admin</span> (Amministratore) &gt; <span class="uicontrol"> Report Suites (Suite</span> di rapporti) &gt; <span class="uicontrol"> Traffic (Traffico</span> ) &gt; <span class="uicontrol"> Traffic Classifications (Classificazioni</span> traffico) (o <span class="uicontrol"> Conversion</span> (Conversione <span class="uicontrol"></span>) &gt; Conversion Classifications (Classificazioni conversione)). Quindi selezionate la variabile, quindi fate clic su <span class="uicontrol"> Aggiungi classificazione</span>. </p> <p>Consulta <a href="https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-classifications.html"  > Classificazioni</a> del traffico e classificazioni <a href="https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html"  ></a> di conversione nell'Aiuto di amministrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Attiva</span> </p> </td> 
   <td colname="col2"> <p>Convalida e attiva una regola. Le regole attive vengono elaborate ogni giorno, esaminando i dati di classificazione che risalgono in genere a un mese. Le regole verificano automaticamente la presenza di nuovi valori e caricano le classificazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Disattiva</span> </p> </td> 
   <td colname="col2"> <p>Disattiva le regole in modo da poterle modificare e testare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurare suite di rapporti e variabili </p> </td> 
   <td colname="col2"> <p>Visualizza la pagina <span class="wintitle"> Suite</span> di rapporti disponibili, in cui è possibile selezionare una o più suite di rapporti disponibili da utilizzare per tutti i set di regole. (Questa pagina viene visualizzata anche quando si esegue per la prima volta il Generatore <span class="wintitle"></span>regole di classificazione.) </p> <p>Questa funzione ha lo scopo di ridurre il tempo di caricamento della suite di rapporti, nel caso in cui disponiate di centinaia di suite di rapporti disponibili. </p> <p>Le suite di rapporti selezionate qui sono disponibili a livello di regola, quando fate clic su <span class="uicontrol"> Aggiungi suite</span> durante la creazione di una regola. </p> <p>Nota: Una suite di rapporti diventa disponibile <span class="term"> solo</span> quando nelle suite di rapporti è definita almeno una classificazione per la variabile in <span class="wintitle"> Strumenti</span>di amministrazione. <p>Per una spiegazione di questo prerequisito, vedere <span class="term"> Variabile</span> in <a href="/help/components/classifications/crb/classification-rule-set.md"  > Set</a> regole di classificazione. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole sovrascrivono eventuali valori esistenti </p> </td> 
   <td colname="col2"> <p> (Impostazione predefinita) Sovrascrivi sempre le chiavi di classificazione esistenti, comprese le classificazioni caricate tramite l'importatore (SAINT). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole sovrascrivono solo i valori non impostati </p> </td> 
   <td colname="col2"> <p>Compilare solo celle vuote (non impostate). Le classificazioni esistenti non saranno modificate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervallo di lookback </p> </td> 
   <td colname="col2"> <p>Quando attivate e convalidate le regole, potete specificare se queste devono sovrascrivere le classificazioni esistenti per le chiavi interessate. Vengono interessate solo le chiavi classificate che sono state passate in <span class="keyword"> Adobe Analytics</span> nel periodo di tempo specificato. </p> <p>Se non si specifica una finestra <span class="term"> di</span>lookback, le regole tornano indietro di circa un mese (a seconda del giorno corrente del mese). Le classificazioni esistenti non vengono mai sovrascritte a meno che non sia stata abilitata questa opzione. </p> <p><b>Dev Center</b>: I partner possono creare regole di classificazione in <span class="wintitle"> Dev Center</span>. Queste regole vengono distribuite quando il cliente attiva un'integrazione. In <span class="wintitle"> Dev Center</span>, l'opzione <span class="uicontrol"> Sovrascrivi dal</span> consente al partner di specificare se il cliente può determinare il valore di sovrascrittura quando si attiva o si modifica un'integrazione. </p> <p>Per ulteriori informazioni sull'elaborazione delle regole, vedere <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Elaborazione</a> delle regole. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Aggiungi regola </a> </td> 
   <td colname="col2"> <p>Consente di aggiungere regole al set di regole. </p> <p>Nota:  Se a un valore corrisponde due o più volte in un insieme di regole, il sistema utilizza l'ultima regola per classificare il valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Bozza</span> </td> 
   <td colname="col2"> Consente di specificare che una regola è in modalità bozza. Lo stato Bozza consente di verificare la regola prima di eseguirla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Duplica</span> </td> 
   <td colname="col2"> Duplica (copia) un set di regole in modo da poter applicare il set di regole a un'altra variabile o alla stessa variabile in un'altra suite di rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Set di regole di test </a> </p> </td> 
   <td colname="col2"> <p>Consente di verificare la validità di un set di regole. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Condizione corrispondente</span> </td> 
   <td colname="col2"> Specifica le condizioni desiderate per la regola. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Azione classificazione</span> </td> 
   <td colname="col2"> <p>Specifica l'azione da eseguire quando si verifica la condizione corrispondente. </p> <p>Ad esempio, puoi impostare un Nome campagna su $2, che identifica la posizione 2 in un codice di tracciamento come Nome campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>Numero della regola. </p> <p>Per ulteriori informazioni, vedere <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Modalità di elaborazione</a> delle regole. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Seleziona tipo di regola</span> </td> 
   <td colname="col2"> <p>Ciascun set di regole si applica a una variabile specifica. Le selezioni valide sono: </p> 
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
   <td colname="col2"> Colonna di classificazione da impostare se i criteri di corrispondenza sono soddisfatti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> A</span> </td> 
   <td colname="col2"> Il valore che si desidera specificare per la colonna di classificazione selezionata se i criteri di corrispondenza sono soddisfatti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> Consente di cercare le regole. </td> 
  </tr> 
 </tbody> 
</table>

## Pagina Espressione regolare {#section_C932A5469E774841B2229965A154163C}

Potete modificare le espressioni regolari sulla [!UICONTROL Regular Expression] pagina.

![](assets/regex_tracking_code.png)

**Definizioni**

| Elemento | Descrizione |
|---|---|
| Chiave di esempio | Stringa di prova da utilizzare. Ad esempio, puoi creare una classificazione da caratteri specifici in un codice di tracciamento. È possibile associare caratteri, parole o pattern particolari di caratteri. |
| Corrispondenza gruppi | Mostra come l&#39;espressione regolare corrisponde ai caratteri ID campagna, in modo da poter classificare una posizione nell&#39;ID campagna. |
| Risultato corrispondenza | Visualizza le parti di una stringa che corrispondono correttamente all&#39;espressione regolare. |

Vedere Espressioni [regolari nelle regole](/help/components/classifications/crb/classification-quickstart-rules.md)di classificazione.

## Pagina di test {#section_EC926F97901C4E65901413F9683AA70A}

Questa pagina consente di sottoporre a test le regole in un set.

**Definizioni**

| Elemento | Descrizione |
|---|---|
| Esegui test | Quando si verifica il set di regole, utilizzare le chiavi del rapporto per vedere in che modo verranno influenzate dal set di regole. |
| Filtro | Filtra i valori nel [!UICONTROL Results] pannello. |

