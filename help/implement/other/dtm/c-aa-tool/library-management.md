---
description: Descrizioni dei campi e delle opzioni nelle impostazioni di Gestione libreria in Gestione tag dinamica.
keywords: library management;page code;load library at;managed by adobe;custom;code hosted;s_code hosted
solution: Experience Cloud
title: Gestione della libreria
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 20%

---


# Gestione della libreria

Descrizioni dei campi e delle opzioni nelle impostazioni di Gestione libreria in Gestione tag dinamica.

**[!UICONTROL  *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Library Management]**

>[!NOTE]
>
>Se in un’unica proprietà Web vengono utilizzati più strumenti Adobe Analytics , ogni strumento deve avere un nome univoco per la variabile di tracciamento. I nomi di variabili oggetto duplicati tra  strumenti Adobe Analytics all&#39;interno di una singola proprietà Web causeranno conflitti.

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Il codice della pagina è già presente </p> </td> 
   <td colname="col2"> <p> Impedisce a Gestione tag dinamica di installare <span class="keyword"> codice di pagina Adobe Analytics</span> se il codice è già presente sul sito. </p> <p>Questa funzione consente di utilizzare Gestione tag dinamica per aggiungere nuovi elementi all'implementazione esistente, anziché iniziare da zero. Quando selezionate questa casella, accertatevi di impostare correttamente il nome della variabile di tracciamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carica libreria in &lt;<span class="term"> Page Top</span> o <span class="term"> Page Bottom</span>&gt; </p> </td> 
   <td colname="col2"> <p>Specifica dove e quando caricare il codice della pagina. Indipendentemente dalla selezione, tutte le regole che utilizzano lo strumento Analytics dovranno avere la stessa impostazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestito da  Adobe (consigliato) </p> </td> 
   <td colname="col2"> <p>Abilita Gestione tag dinamica per gestire la libreria. </p> <p>Se selezioni questa opzione, diventa disponibile l'opzione seguente: </p> <p> <b>Library Version: </b>(Versione libreria) seleziona la versione più recente dal menu <span class="wintitle">Library Version. </span> Gestione tag dinamica invia una notifica quando sono disponibili nuove versioni. Se necessario, potete ripristinare una versione precedente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Personalizzato </p> </td> 
   <td colname="col2"> <p>Potete configurare il codice della libreria. </p> <p>Se selezionate questa opzione, diventano disponibili le seguenti opzioni: </p> <p> <b>Imposta le suite di rapporti utilizzando il codice personalizzato seguente: </b>Quando questa casella è selezionata, Gestione tag dinamica cerca una variabile nel codice personalizzato denominata <span class="varname"> s_account</span>. Questa variabile deve contenere un elenco separato da virgole delle suite di rapporti a cui desideri inviare i dati. </p> <p> <b>Codice ospitato: </b>Scegliete un’opzione per ospitare il <span class="filepath"> s_code</span>: </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>In Gestione dinamica dei tag</b>: Puoi ospitare il <span class="filepath"> s_code</span> in Gestione tag dinamica. Fate clic su <span class="uicontrol"> Modifica codice</span> per tagliare e incollare il file direttamente nell’editor. </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL</b>: Se disponete di un buon file <span class="filepath"> s_code</span> e siete soddisfatti del processo di aggiornamento, potete fornire l'URL al file qui. La gestione tag dinamica utilizza quindi il file <span class="filepath"> s_code</span> per l'implementazione di <span class="keyword"> Adobe Analytics</span>. </li> 
    </ul> <p> <b>Open Editor</b> (Apri editor): consente di <a href="/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md"  >inserire il codice AppMeasurement principale</a>. Questo codice viene popolato automaticamente quando si utilizza il metodo di configurazione automatico descritto in <a href="/help/implement/other/dtm/c-aa-tool/analytics-dtm.md"  >Impostazioni di Adobe Analytics</a>. </p> <p> <b>Nome variabile Tracker: </b>Se desiderate eseguire due istanze di <span class="keyword"> Adobe Analytics</span> in parallelo (una in Gestione tag dinamica e una in modo nativo), potete rinominare l'oggetto <span class="term"> s</span> principale. Se rinomini il nome dell’oggetto, non si verificano conflitti. </p> </td> 
  </tr> 
 </tbody> 
</table>

