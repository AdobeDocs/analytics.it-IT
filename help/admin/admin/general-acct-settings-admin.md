---
description: Descrizioni dei campi per le impostazioni generali dell'account della suite in Amministratore.
seo-description: Descrizioni dei campi per le impostazioni generali dell'account della suite in Amministratore.
seo-title: Impostazioni account generali
solution: Analytics
title: Impostazioni account generali
topic: Strumenti di amministrazione
uuid: c 1 ab 5 c 34-2 c 41-4 d 12-a 706-0 e 760 dff 8 a 95
translation-type: tm+mt
source-git-commit: 01ac0011f2e47e6798a520df8ffe5d8393ac0c3c

---


# Impostazioni account generali

Descrizioni dei campi per le impostazioni generali dell'account della suite in Amministratore.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL General Account Settings]**

Queste impostazioni contengono opzioni di modifica per le funzionalità di base della suite di rapporti, come nome e fuso orario.

<table id="table_5448A694DC0A48D2B20C7F1332509F6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Titolo sito</span> </td> 
   <td colname="col2"> <p>Identifica il sito. Assegna a ogni suite di rapporti un titolo univoco del sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> URL di base</span> </td> 
   <td colname="col2"> <p>Specifica il sito Web principale della suite di rapporti. L'URL di base non influisce sui filtri di riferimento. Utilizzare <a href="../../admin/admin/internal-url-filter-admin.md#concept_D6BB8358DB7643F0B13E5DC9B7607998" format="dita" scope="local"> invece filtri</a> URL interni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fuso orario</span> </td> 
   <td colname="col2"> <p>Determina la data e l'ora associate ai dati del rapporto. </p> <p>La modifica del fuso orario per una suite di rapporti live crea un picco o uno spazio nei dati del rapporto. Per ridurre al minimo l'impatto, Adobe consiglia di modificare i fusi orari durante l'orario non-picco per evitare l'inclinazione dei dati. </p> <p>Ad esempio, se cambi il fuso orario della suite di rapporti da Central a Pacific alle 3:00, il tempo corrente della suite di rapporti diventa 1:00 pm. Poiché i rapporti hanno già raccolto dati per l'ora 1:00, i report mostrano un picco del traffico tra le 1:00 e le 3:00 pm. </p> <p>In alternativa, se cambi il fuso orario della suite di rapporti da Central ad Eastern alle 3:00, il tempo corrente della suite di rapporti diventa 4:00 pm. I rapporti non mostrano dati tra le 3:00 e le 4:00 del giorno della modifica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Livello di conversione</span> </td> 
   <td colname="col2"> <p> Abilita o disabilita le variabili di e-commerce come evar e campagne. Utilizzate l'opzione <span class="uicontrol"> Attivato, Nessuna carrello</span> per nascondere tutti i rapporti sul carrello se non disponete di un carrello sul sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Pagina predefinita</span> </td> 
   <td colname="col2"> <p> Se <span class="wintitle"> il rapporto più comuni pagine</span> contiene URL piuttosto che nomi di pagina, questa impostazione impedisce che più URL rappresentino la stessa pagina. Ad esempio, gli URL <span class="filepath"> https://mysite.com</span> e <span class="filepath"> https://mysite.com/index.html</span> sono generalmente la stessa pagina. Potete rimuovere i nomi dei file predefiniti in modo che entrambi vengano visualizzati come <span class="filepath"> https://mysite.com</span>. </p> <p>Se lasciato vuoto, i seguenti nomi file vengono rimossi dagli URL: <span class="filepath"> index.htm</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index. cgi</span>, <span class="filepath"> index. asp</span>, <span class="filepath"> default.htm</span>, <span class="filepath"> default.html</span>, <span class="filepath"> default. cgi</span>, <span class="filepath"> default. asp</span>, <span class="filepath"> home.htm</span>, <span class="filepath"> home.html</span>, <span class="filepath"> home. cgi</span>e <span class="filepath"> home. asp</span>. </p> <p>Per disabilitare la rimozione del nome file, immettete un valore che non sia mai presente negli URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Sostituisce l'ultimo ottetto di indirizzi IP con 0 </span> </td> 
   <td colname="col2"> <p>La rimozione dell'ultimo ottetto viene effettuata prima del filtro IP. Pertanto, l'ultimo ottetto viene sostituito con un 0 e le regole di esclusione IP devono essere aggiornate per corrispondere agli indirizzi IP con uno zero alla fine. Corrispondenza * deve corrispondere a 0. </p> <p>Selezionando questa opzione, l'indirizzo IP viene modificato prima dell'elaborazione. Ad esempio, l'indirizzo IP 134.123.567.780 viene cambiato in 134.123.567.0. I dati di geosegmentazione non saranno esattamente identici a quando viene utilizzato l'indirizzo IP intero. In modo specifico, la precisione della città sarà più influenzata dall'accuratezza del paese o della regione. Sono interessate dalle regole bot e dalle regole VISTA perché l'indirizzo IP completo non è disponibile. Inoltre, questa impostazione interessa tutte le regole di elaborazione basate su IP, incluse regole di canale di marketing e regole di elaborazione suite di rapporti. </p> <p>Nota: Questa impostazione è attivata per impostazione predefinita per tutte le nuove suite di rapporti create nel Centro dati London dopo il 2019 gennaio, ma solo se le impostazioni per tali suite di rapporti vengono copiate da un modello elencato in Admin Console. Le suite di rapporti le cui impostazioni vengono duplicate da altre suite di rapporti erediteranno tutte le impostazioni dalla suite di rapporti selezionata. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Offuscamento IP</span> </td> 
   <td colname="col2"> <p>Trasforma gli indirizzi IP in stringhe non riconoscibili, rimuovendo in pratica tali indirizzi dai negozi di dati Adobe. Quando l'opzione Offuscamento IP è attivata, gli indirizzi IP originali vengono perduti in modo permanente. </p> <p>Nota: Gli indirizzi IP vengono offuscati ovunque in Analytics, incluso Data Warehouse. Tuttavia, l'impostazione IP in Target viene controllata separatamente, pertanto questa impostazione non ha alcun impatto su Target. </p> <p>Se l'offuscamento IP è abilitato, l'esclusione IP avviene prima che l'indirizzo IP non venga oscurato, in modo che i clienti non debbano modificare nulla quando abilitano l'offuscamento IP. </p> <p>Selezionando <span class="uicontrol"> Disattivato</span> l'indirizzo IP viene lasciato nei dati. </p> <p>Selezionando <span class="uicontrol"> l'indirizzo</span> IP offuscate, l'IP passa a un valore con hash (ad es. 234 abc 6493872038). </p> <p>Selezionando <span class="uicontrol"> Rimuovi indirizzo</span> IP, l'indirizzo IP viene sostituito con x. x. x. x nei dati, dopo la ricerca geografica. </p> <p>Nota: Questa impostazione potrebbe richiedere modifiche a regole <a href="../../admin/admin/bot-removal/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7" format="dita" scope="local"> bot personalizzate</a> o<a href="../../admin/admin/exclude-ip.md#concept_265A95A803F740629CAAAA7EB8BE81A4" format="dita" scope="local"> esclusioni IP</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Archiviazione ID transazione</span> </td> 
   <td colname="col2"> <p>Consente di utilizzare <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_Transaction_ID" format="https" scope="external"> le origini dati ID</a> transazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Attivare Analisi ad hoc</span> </td> 
   <td colname="col2"> <p>Indica se la suite di rapporti in questione viene visualizzata come suite di rapporti disponibile in Analisi ad hoc. Utilizzate questa impostazione per limitare le suite di rapporti visualizzate come opzione per Analisi ad hoc. Ad esempio, puoi disabilitare Analisi ad hoc per le suite di sviluppo e di rapporti QA. </p> </td> 
  </tr> 
  <tr> 
   <td><span class="wintitle"> Abilita Data Warehouse</span> </td> 
   <td colname="col2"> <p>Abilita l'interfaccia utente di Data Warehouse in <span class="uicontrol"> Strumenti</span> &gt;<span class="uicontrol"> Data Warehouse</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

