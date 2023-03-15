---
description: Definizioni degli elementi dell’interfaccia nelle pagine del Generatore di regole di classificazione.
title: 'Regole di classificazione: definizioni'
feature: Classifications
exl-id: 514501d1-7e1b-45da-b8fe-c68331e59dab
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 24%

---

# Regole di classificazione: definizioni

Definizioni degli elementi dell’interfaccia nelle pagine del Generatore di regole di classificazione.

## Pagina Regole {#section_4A5BF384EEEE4994B6DC888339833529}

In questa pagina vengono visualizzate le regole di un set di regole.

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
   <td colname="col2"> <p><b>Suite di rapporti</b> </p> <p>Le suite di rapporti a cui si applica il set di regole. </p> <p><b>Variabile</b> </p> <p>Puoi applicare una sola variabile quando crei un set di regole di classificazione. Per creare più set di regole per una variabile, è necessario applicare ciascun set di regole a più suite di rapporti. </p> <p>Nota: nelle suite di rapporti puoi utilizzare solo le variabili a cui hai accesso. Le variabili verranno visualizzate in <span class="wintitle"> Nuovo set di regole</span> solo dopo aver definito almeno una classificazione per tale variabile. </p> <p> Puoi creare classificazioni su una variabile in <span class="uicontrol"> Amministratore</span> &gt; <span class="uicontrol"> Suite di rapporti</span> &gt; <span class="uicontrol"> Traffico</span> &gt; <span class="uicontrol"> Classificazioni traffico</span> (o <span class="uicontrol"> Conversione</span> &gt; <span class="uicontrol"> Classificazioni di conversione</span>). Seleziona quindi la variabile e fai clic su <span class="uicontrol"> Aggiungi classificazione</span>. </p> <p>Consulta <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/traffic-variables/traffic-classifications.html?lang=it"  > Classificazioni traffico</a> e <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html?lang=it"  > Classificazioni di conversione</a> nella Guida dell’amministratore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Attiva</span> </p> </td> 
   <td colname="col2"> <p>Convalida e attiva una regola. Le regole attive vengono elaborate ogni giorno ed esaminano i dati di classificazione che risalgono in genere a un mese. Le regole verificano automaticamente la presenza di nuovi valori e caricano le classificazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Disattivare</span> </p> </td> 
   <td colname="col2"> <p>Disattiva le regole in modo da poterle modificare e testare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurare suite di rapporti e variabili </p> </td> 
   <td colname="col2"> <p>Visualizza la <span class="wintitle"> Suite di rapporti disponibili</span> , in cui è possibile selezionare una o più suite di rapporti disponibili da utilizzare per tutti i set di regole. (Questa pagina viene visualizzata anche quando si esegue per la prima volta <span class="wintitle"> Generatore regole di classificazione</span>.) </p> <p>Questa funzione ha lo scopo di ridurre il tempo di caricamento della suite di rapporti nel caso in cui siano disponibili centinaia di suite di rapporti. </p> <p>Le suite di rapporti selezionate qui sono rese disponibili a livello di regola, quando fai clic su <span class="uicontrol"> Aggiungi suite</span> durante la creazione di una regola. </p> <p>Nota: diventa disponibile una suite di rapporti <span class="term"> solo</span> quando le suite di rapporti hanno almeno una classificazione definita per la variabile in <span class="wintitle"> Strumenti di amministrazione</span>. <p>(vedere <span class="term"> Variabile</span> in <a href="/help/components/classifications/crb/classification-rule-set.md"  > Set di regole di classificazione</a> per una spiegazione di questo prerequisito.) </p> </p> </td> 
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
   <td colname="col2"> <p>Quando attivi e convalidi le regole, puoi specificare se le regole devono sovrascrivere le classificazioni esistenti per le chiavi interessate. (Solo chiavi classificate che sono state precedentemente passate in <span class="keyword"> Adobe Analytics</span> entro il periodo di tempo specificato). </p> <p>Se non si specifica un <span class="term"> intervallo di lookback</span>, le regole vengono visualizzate all’incirca un mese fa (a seconda del giorno corrente del mese). Le classificazioni esistenti non vengono mai sovrascritte, a meno che questa opzione non sia abilitata. </p> <p><b>Dev Center</b>: i partner possono creare regole di classificazione in <span class="wintitle"> Dev Center</span>. Queste regole vengono distribuite quando il cliente attiva un’integrazione. In <span class="wintitle"> Dev Center</span>, il <span class="uicontrol"> Sovrascrivi da</span> consente al partner di specificare se il cliente può determinare il valore di sovrascrittura quando attiva o modifica un’integrazione. </p> <p>Consulta <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Elaborazione delle regole</a> per ulteriori informazioni sull’elaborazione delle regole. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Aggiungi regola </a> </td> 
   <td colname="col2"> <p>Consente di aggiungere regole al set di regole. </p> <p>Nota: se un valore viene abbinato due o più volte in un insieme di regole, il sistema utilizza l'ultima regola per classificare il valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Bozza</span> </td> 
   <td colname="col2"> Consente di specificare che una regola è in modalità bozza. Lo stato Bozza consente di testare la regola prima di eseguirla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Duplica</span> </td> 
   <td colname="col2"> Duplica (copia) un set di regole in modo da poterlo applicare a un’altra variabile o alla stessa variabile in una suite di rapporti diversa. </td> 
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
   <td colname="col1"> <span class="wintitle"> Azione di classificazione</span> </td> 
   <td colname="col2"> <p>Specifica l'azione da eseguire quando si verifica la condizione di corrispondenza. </p> <p>Ad esempio, puoi impostare un Nome campagna su $2, che identifica la posizione 2 in un codice di tracciamento come Nome campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>Numero della regola. </p> <p>Consulta <a href="/help/components/classifications/crb/classification-quickstart-rules.md"  > Elaborazione delle regole</a> per ulteriori informazioni. </p> </td> 
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
   <td colname="col2"> Schema di testo che si sta cercando in una chiave. Questi criteri possono essere termini di ricerca, caratteri o espressioni regolari. </td> 
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

## Pagina Espressione regolare {#section_C932A5469E774841B2229965A154163C}

Puoi modificare le espressioni regolari sul [!UICONTROL Regular Expression] pagina.

![](assets/regex_tracking_code.png)

**Definizioni**

| Elemento | Descrizione |
|---|---|
| Chiave di esempio | Stringa di test da utilizzare. Ad esempio, puoi creare una classificazione da caratteri specifici in un codice di tracciamento. È possibile far corrispondere caratteri, parole o pattern di caratteri specifici. |
| Corrispondenza gruppi | mostra in che modo l’espressione regolare corrisponde ai caratteri dell’ID campagna, in modo da poter classificare una posizione nell’ID campagna. |
| Risultato di corrispondenza | Visualizza le parti di una stringa che corrispondono all&#39;espressione regolare. |

Consulta [Espressioni regolari nelle regole di classificazione](/help/components/classifications/crb/classification-quickstart-rules.md).

## Pagina di prova {#section_EC926F97901C4E65901413F9683AA70A}

Questa pagina consente di testare le regole in un set.

**Definizioni**

| Elemento | Descrizione |
|---|---|
| Esegui test | Quando verifichi il set di regole, utilizza le chiavi del rapporto per vedere in che modo verranno influenzate dal set di regole. |
| Filtro | Filtra i valori in [!UICONTROL Results] pannello. |
