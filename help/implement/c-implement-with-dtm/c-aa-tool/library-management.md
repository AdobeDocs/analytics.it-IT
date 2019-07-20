---
description: Descrizioni dei campi e delle opzioni nelle impostazioni Gestione libreria in Gestione tag dinamica.
keywords: gestione libreria; codice della pagina; load library at; gestito da adobe; custom; il codice ospitato; s_ code ospitato
seo-description: Descrizioni dei campi e delle opzioni nelle impostazioni Gestione libreria in Gestione tag dinamica.
seo-title: Gestione della libreria
solution: Marketing Cloud, Gestione tag dinamica
title: Gestione della libreria
uuid: 4 cfa 47 f 9-ae 98-4 feb-a 58 d-a 3 a 6 e 45 f 8 d 5 b
translation-type: tm+mt
source-git-commit: 3489f00bd7dddefda0420fc361056416f6f10d3f

---


# Gestione della libreria

Descrizioni dei campi e delle opzioni nelle impostazioni Gestione libreria in Gestione tag dinamica.

**[!UICONTROL  *`Property`*]**&gt;![](assets/settings_gear.png)**[!UICONTROL Edit Tool]**&gt;**[!UICONTROL Library Management]**

>[!NOTE]
>
>Se in una singola proprietà Web sono utilizzati più strumenti Adobe Analytics, ogni strumento deve avere un nome di variabile univoco. I nomi delle variabili oggetto duplicati tra gli strumenti di Adobe Analytics all'interno di una singola proprietà Web causeranno conflitti.

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
   <td colname="col2"> <p> Prevents Dynamic Tag Management from installing <span class="keyword"> Adobe Analytics</span> page code if the code is already present on your site. </p> <p>Questa funzione consente di utilizzare Gestione tag dinamica per aggiungere all'implementazione esistente, anziché iniziare da zero. Assicurarsi di impostare correttamente il nome della variabile tracker quando si seleziona questa casella. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Load library at &lt;<span class="term"> Page Top</span> or <span class="term"> Page Bottom</span>&gt; </p> </td> 
   <td colname="col2"> <p>Specifica dove e quando caricare il codice della pagina. Indipendentemente dalla selezione, tutte le regole che utilizzano lo strumento Analytics devono avere la stessa impostazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestito da Adobe (consigliato) </p> </td> 
   <td colname="col2"> <p>Abilita Gestione tag dinamica per gestire la tua libreria. </p> <p>Se selezioni questa opzione, diventa disponibile l'opzione seguente: </p> <p> <b>Library Version: </b>(Versione libreria) seleziona la versione più recente dal menu <span class="wintitle">Library Version. </span> Gestione tag dinamica notifica quando sono disponibili nuove versioni. È possibile ripristinare una versione precedente, a seconda delle necessità. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Personalizzato </p> </td> 
   <td colname="col2"> <p>Potete configurare il codice della libreria. </p> <p>Se selezionate questa opzione, diventano disponibili le seguenti opzioni: </p> <p> <b>Imposta suite di rapporti utilizzando il codice personalizzato seguente: </b>Quando questa casella è selezionata, Gestione tag dinamica cerca una variabile nel codice personalizzato denominato <span class="varname"> s_ account</span>. Questa variabile deve contenere un elenco separato da virgole delle suite di rapporti a cui desiderate inviare i dati. </p> <p> <b>Hosting del codice: </b>Scegliete un'opzione per ospitare il <span class="filepath"> codice s_ code</span>: </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>In Gestione dinamica dei tag</b>: Puoi ospitare il <span class="filepath"> codice s_</span> all'interno di Gestione tag dinamica. Click <span class="uicontrol"> Edit Code</span> to cut and paste the file directly into the editor. </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL</b>: Se disponete di un file <span class="filepath"> s_ code</span> valido e siete soddisfatti del processo di aggiornamento, potete fornire l'URL al file qui. Dynamic tag management then consumes that <span class="filepath"> s_code</span> file for its implementation of <span class="keyword"> Adobe Analytics</span>. </li> 
    </ul> <p> <b>Editor aperto: </b>Consente <a href="../../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658" format="dita" scope="local"> di inserire codice appmeasurement principale</a>. This code is populated automatically when using the automatic configuration method described in <a href="../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8" format="dita" scope="local"> Adobe Analytics Settings</a>. </p> <p> <b>Nome variabile tracciatore: </b>Se desiderate eseguire due istanze di <span class="keyword"> Adobe Analytics</span> in parallelo (una in Gestione tag dinamica e in modo nativo), potete rinominare l'oggetto <span class="term"> s</span> principale. La ridenominazione del nome dell'oggetto evita la collisione. </p> </td> 
  </tr> 
 </tbody> 
</table>

