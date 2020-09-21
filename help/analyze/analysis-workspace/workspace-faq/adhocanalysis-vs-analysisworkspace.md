---
description: Confronta la terminologia e le attività di Ad Hoc Analysis ad Analysis Workspace.
title: Confronto tra Analysis Workspace e Ad Hoc Analysis
uuid: e4b3e40f-2b08-49a0-95f1-384d85c1640d
translation-type: tm+mt
source-git-commit: 5d96a2868bee48e2294ec2fb27e0340a3bcc50ae
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 98%

---


# Confronto tra Analysis Workspace e Ad Hoc Analysis

>[!IMPORTANT]
>
> Adobe si sta muovendo  Ad Hoc Analysis fino alla fine del suo ciclo di vita il 1 marzo 2021. [Ulteriori informazioni](https://adobe.ly/discoverworkspace)

Confronta la terminologia e le attività di Ad Hoc Analysis ad Analysis Workspace.

Analysis Workspace porta moltissime delle funzionalità di Ad Hoc Analysis nel flusso di lavoro del browser. Anche se alcuni termini e funzionalità restano invariati tra i prodotti, in Analysis Workspace sono stati introdotti nuovi termini e approcci all’analisi.

Per un confronto tecnico delle funzionalità principali e dei requisiti di sistema tra questi due prodotti, fai clic [qui](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-overview/analytics-product-comparison.html).

## Confronto della terminologia chiave {#section_6109406B83B043A18E46D38F130B1D2E}

| Ad Hoc Analysis | Analysis Workspace |
|--- |--- |
| Progetto | Workspace o progetto |
| Workspace | Pannello |
| Rapporto | Tabella a forma libera |
| Grafico/Grafico | Visualizzazione |
| Gerarchia: Progetto > Workspace > Rapporti | Gerarchia: Progetto > Pannelli > Tabelle |
| Classificati, Con tendenze, modelli rapporto dei totali | Visualizzazione tabella a forma libera |
| Modello di flusso | Visualizzazione flusso |
| Abbandono | Visualizzazione abbandono |

## Confronto delle attività chiave {#section_F31446F1DFA742D794A30D713E223440}

<table id="table_90D4461F04F34D70844C5E3FBB0BBE44"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ad Hoc Analysis Attività </th> 
   <th colname="col2" class="entry"> Attività Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Aggiungere dimensioni e segmenti alle colonne di metrica </p> </td> 
   <td colname="col2"> <p>Puoi importare elementi dimensionali o segmenti come intestazioni di colonna per creare visualizzazioni comparative delle metriche. <a href="https://www.youtube.com/watch?v=P9W0hhIHhCs"  > Video: Lavorare con le dimensioni</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Applicare i segmenti </p> </td> 
   <td colname="col2"> <p>I segmenti sono disponibili nel menu componente Segmento e possono essere applicati in 3 posizioni in Analysis Workspace: </p> 
    <ol id="ol_800D81FE2C84459B94B085C51E140330"> 
     <li id="li_F2E050902F9A4831BBA57F466E07DEAE">A <b>livello di pannello</b>, per diverse visualizzazioni nel pannello. È simile all’applicazione di un segmento a un Workspace in Ad Hoc. </li> 
     <li id="li_2D88E43E0161485C95B08DC3C593EFD9">Come <b>righe in una tabella</b>. Simile all’aggiunta di segmenti alla sezione “Righe/Interruzioni” del Generatore tabella in Ad Hoc. </li> 
     <li id="li_102E1A1DAA9247C08FC46C5AB3D78113">Come <b>colonne di una tabella</b>. Simile all’aggiunta di segmenti alla sezione “Colonne” del Generatore tabella in Ad Hoc Analysis o all’applicazione di un segmento a livello di Rapporto in Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://www.youtube.com/watch?v=QlUCdQDnni4"  > Video: Utilizzo dei segmenti in Workspace</a> </p> <p><a href="https://www.youtube.com/watch?v=YjaRlJoQqRA"  > Video: Applicazione dei sementi in un pannello</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creare segmenti temporanei (“ad hoc”) </p> </td> 
   <td colname="col2"> <p>Puoi <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  >creare segmenti istantanei e temporanei (“ad hoc”)</a> in Analysis Workspace trascinando elementi dimensionali nella zona di rilascio del segmento nella parte superiore del pannello. È inoltre possibile aggiungere filtri a discesa nella zona di rilascio del pannello per creare più segmenti temporanei alla volta, consentendo interazioni controllate tra i progetti. </p> <p><a href="https://www.youtube.com/watch?v=NKm7Rj23TtE"  > Video: Segmenti ad hoc in Analysis Workspace</a> </p> <p><a href="https://www.youtube.com/watch?v=vpJywtsFVPI"  > Video: Filtri a discesa in Analysis Workspace</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scegliere intervalli di date e granularità </p> </td> 
   <td colname="col2"> <p>Gli intervalli di date e le granularità sono disponibili nel menu del componente Tempo e possono essere utilizzati in 3 modi: </p> 
    <ol id="ol_8B57C8A840694A879B22B809C58E7482"> 
     <li id="li_58FAE6A87B494A5C9007CD35BB101608">Gli intervalli di date possono essere applicati alle colonne/righe e ignorare l’intervallo delle date selezionato nel pannello. È simile agli intervalli delle date a livello di Rapporto. </li> 
     <li id="li_85BB89EFF9C8466A992815BB7804EA37">“Applica” applica un intervallo date a tutte le visualizzazioni in un pannello. È simile a un intervallo date Workspace in Ad Hoc Analysis. </li> 
     <li id="li_BC18564A8FBB48F4A522BCAC60838759">“Applica a tutti i pannelli” applica un intervallo date a tutte le visualizzazioni in un progetto Workspace. È simile a un intervallo date Progetto in Ad Hoc Analysis. </li> 
    </ol> <p><a href="https://www.youtube.com/watch?v=ybmv6EBmhn0"  > Video: Lavorare con le date in Analysis Workspace</a> </p> <p><a href="https://www.youtube.com/watch?v=L4FSrxr3SDA"  > Video: Intervalli date personalizzati</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usare l’abbandono e i funnel di conversione </p> </td> 
   <td colname="col2"> <p>Le <a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  >visualizzazioni Abbandono</a> sono disponibili in Analysis Workspace nel menu del componente Visualizzazione. Simile ad Ad Hoc Analysis: </p> 
    <ol id="ol_625FF45AED4E403DBEE1A906282E8531"> 
     <li id="li_7B6C5F2682774641B82D2021786AE5C4">Abbandono può abbracciare una visita o un visitatore e, se lo desideri, è possibile includere “Tutte le visite”. Le tendenze dell’abbandono possono essere rapidamente elaborate mediante il menu di scelta rapida. </li> 
     <li id="li_CFBDDAB8E96A445DB0624640AEB25994">Gli elementi dimensionali possono essere connessi da un operatore OR (simile ai gruppi) ed è possibile utilizzare gli eventi nel funnel. </li> 
     <li id="li_6638E6A62C744A27B2C066E5F9EC62C0">Mediante il menu di scelta rapida è inoltre possibile effettuare il rendering dei passi successivi di Prosecuzione e Abbandono. </li> 
    </ol> <p>Inoltre, Abbandono in Analysis Workspace consente <a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md"  > dimensioni diverse</a> tra le varie fasi, un miglioramento rispetto ad Ad Hoc Analysis. Dimensioni diverse nei passaggi vengono gestite con un operatore AND. </p> <p><a href="https://www.youtube.com/watch?v=VcrfHSyIoj8"  > Video: Abbandono e Funnel</a> </p> <p><a href="https://www.youtube.com/watch?v=EeLV366pQag"  > Video: Utilizzo di più dimensioni di abbandono</a> </p> <p><a href="https://www.youtube.com/watch?v=H-oT3QZlyZQ"  > Video: Confronto di segmenti in Abbandono</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esaminare il flusso (percorso) </p> </td> 
   <td colname="col2"> <p>Le <a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  >visualizzazioni Flusso</a> sono disponibili in Analysis Workspace nel menu del componente Visualizzazione. Simile ad Ad Hoc Analysis: </p> 
    <ul id="ul_42D259310823496499F7D1474E1639AF"> 
     <li id="li_5DE6980EF66A49E58B8946A0422BC02C">Flow può estendere una visita o un visitatore. </li> 
     <li id="li_70A692266D32416BA3D70C1F8999F837">Le statistiche chiave vengono visualizzate in termini di visualizzazioni di percorso %. </li> 
    </ul> <p>Inoltre, Flusso consente <a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  > dimensioni diverse</a> e la possibilità di fare clic con il pulsante destro del mouse e creare un segmento, un miglioramento rispetto all’Ad Hoc Analysis. </p> <p>Attualmente, Flusso in Analysis Workspace <b>non può</b> consentire agli utenti di scegliere un evento riuscito. </li> 
    </ul> <p><a href="https://www.youtube.com/watch?v=3R1HTM7y_RM"  > Video: Panoramica della Visualizzazione Flusso</a> </p> <p><a href="https://www.youtube.com/watch?v=m1Wa6inC1rQ"  > Video: Flusso multidimensionale</a> </p> <p><a href="https://www.youtube.com/watch?v=XrJoNQy6RaQ"  > Video: Creazione dei segmenti da Flusso</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eseguire suddivisioni illimitate </p> </td> 
   <td colname="col2"> <p>Analysis Workspace ti consente di eseguire il drill down a infiniti livelli nel browser. Segmenti e dimensioni possono essere mescolati tra loro. Più elementi dimensionali alla volta possono essere suddivisi effettuando una selezione multipla e trascinando su una dimensione di suddivisione. </p> <p><a href="https://www.youtube.com/watch?v=3mQ2HN7-lIc"  > Video: Suddivisioni migliorate</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati di tendenza rapidi </p> </td> 
   <td colname="col2"> <p>I dati possono essere visualizzati rapidamente facendo clic sull’icona del grafico nella riga rapporto Inoltre, queste visualizzazioni rapide verranno collegate alla tabella d’origine in modo che tu possa fare clic da un valore all’altro nella tabella e vedere il grafico aggiornarsi automaticamente. </p> <p><a href="https://www.youtube.com/watch?v=kzlPjsBVYFQ"  > Video: Collegamento in tempo reale del grafico dimensionale</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Selezionare suite di rapporti </p> </td> 
   <td colname="col2"> <p>È possibile aggiungere più suite di rapporti a un singolo progetto in Analysis Workspace.  </p> <p><a href="https://www.youtube.com/watch?v=kRPTBDNLJKk"  > Video: Più suite di rapporti in Workspace</a> </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribution IQ </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/attribution/overview.md"  > Attribution IQ</a> in Analysis Workspace consente di aggiungere molti nuovi tipi di modelli di attribuzione a tabelle a forma libera, visualizzazioni e metriche calcolate. Include oltre 10 modelli algoritmici e basati sulle regole. </p>  <p><a href="https://www.youtube.com/watch?v=aYbGcQvAN1E"  > Video: Attribution IQ nelle tabelle a forma libera</a> </p> </td> 
  </tr>  
 </tbody> 
</table>

