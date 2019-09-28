---
description: Descrizioni dei campi per le impostazioni generali dell'account della suite di rapporti in Amministratore.
seo-description: Descrizioni dei campi per le impostazioni generali dell'account della suite di rapporti in Amministratore.
seo-title: Impostazioni account generali
solution: Analytics
title: Impostazioni account generali
topic: Strumenti di amministrazione
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
translation-type: tm+mt
source-git-commit: 3c5cc9275c9978caf57e4e29704e23405ac24b65

---


# Impostazioni account generali

Descrizioni dei campi per le impostazioni generali dell'account della suite di rapporti in Amministratore.

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
   <td colname="col2"> <p>Identifies your site. Give each report suite a unique site title. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Base URL</span> </td> 
   <td colname="col2"> <p>Specifies the report suite's main website. The Base URL does not affect referrer filtering. Use  internal URL filters instead.<a href="../../admin/admin/internal-url-filter-admin.md#concept_D6BB8358DB7643F0B13E5DC9B7607998" format="dita" scope="local"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fuso orario</span> </td> 
   <td colname="col2"> <p>Determines the date and time associated with your report data. </p> <p>Changing the time zone for a live report suite creates either a spike or gap in report data. To minimize the impact, Adobe recommends changing time zones during non-peak hours to avoid skewing data. </p> <p>Ad esempio, se cambi il fuso orario della suite di rapporti da Centrale a Pacifico alle 15:00, l'ora corrente della suite di rapporti diventa 1:00. Poiché il reporting ha già raccolto i dati per l'ora 1:00, i report mostrano un picco di traffico tra le 1:00 e le 15:00. </p> <p>In alternativa, se cambi il fuso orario della suite di rapporti da Centrale a Orientale alle 15:00, l'ora corrente della suite di rapporti diventa le 16:00. I report non visualizzano dati compresi tra le 15:00 e le 16:00 del giorno in cui è avvenuto il cambiamento di ora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Conversion Level</span> </td> 
   <td colname="col2"> <p> Enables or disables e-commerce variables such as eVars and campaigns. Use the  Enabled, no Shopping Cart option to hide all shopping cart reports if you don't have a shopping cart on your site.<span class="uicontrol"></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Pagina predefinita</span> </td> 
   <td colname="col2"> <p> If your  Most Popular Pages Report contains URLs rather than page names, this setting prevents multiple URLs from representing the same page. <span class="wintitle"></span> Ad esempio, gli URL <span class="filepath"> https://mysite.com</span> e <span class="filepath"> https://mysite.com/index.html</span> sono in genere la stessa pagina. Potete rimuovere i nomi file predefiniti in modo che entrambi questi URL vengano visualizzati come <span class="filepath"> https://mysite.com</span>. </p> <p>Se lasciato vuoto, i seguenti nomi file vengono rimossi dagli URL: <span class="filepath"> index.html</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index.cgi</span>, <span class="filepath"> index.asp</span>, <span class="filepath"> default.htm</span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span>, default.htmlhtm, default.cgi, default.cgi, default.cgi, default.asp, home.html, home.cgi.prepre. </p> <p>Per disattivare completamente lo stripping dei nomi dei file, immettete un valore che non sia mai presente negli URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Sostituire l'ultimo ottetto di indirizzi IP con 0 </span> </td> 
   <td colname="col2"> <p>La rimozione dell'ultimo ottetto viene effettuata prima del filtro IP. Di conseguenza, l'ultimo ottetto viene sostituito con 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano agli indirizzi IP con uno zero alla fine. La corrispondenza * deve corrispondere a 0. </p> <p>Selezionando questa opzione, l'indirizzo IP viene modificato prima dell'elaborazione. Ad esempio, l’indirizzo IP 134.123.567.780 viene modificato in 134.123.567.0. I dati di segmentazione geografica non saranno esattamente come quando viene utilizzato l'intero indirizzo IP. Nello specifico, l'accuratezza della città sarà più influenzata dall'accuratezza di paese o regione. Le regole bot e VISTA sono influenzate dal fatto che l'intero indirizzo IP non è disponibile. Inoltre, tutte le regole di elaborazione basate su IP, incluse le regole del canale di marketing e le regole di elaborazione delle suite di rapporti, sono influenzate da questa impostazione. </p> <p>Nota:   Questa impostazione è abilitata per impostazione predefinita per tutte le nuove suite di rapporti create nel centro dati londinese dopo gennaio 2019, ma solo se le impostazioni per tali suite di rapporti vengono copiate da un modello elencato in Admin Console. Le suite di rapporti le cui impostazioni sono duplicate da altre suite di rapporti erediteranno tutte le impostazioni dalla suite di rapporti selezionata. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Obfuscamento IP</span> </td> 
   <td colname="col2"> <p>Trasforma gli indirizzi IP in stringhe non riconoscibili, sostanzialmente rimuovendoli dagli archivi dati Adobe. Quando l'offuscamento IP è abilitato, gli indirizzi IP originali vengono persi definitivamente. </p> <p>Nota:  Gli indirizzi IP sono oscurati ovunque in Analytics, incluso Data Warehouse. Tuttavia, l'impostazione IP in Target è controllata separatamente, pertanto questa impostazione non ha alcun impatto su Target. </p> <p>Se l'offuscamento IP è abilitato, l'esclusione IP avviene prima che l'indirizzo IP sia oscurato, in modo che i clienti non debbano cambiare nulla quando attivano l'offuscamento IP. </p> <p>Selezionando <span class="uicontrol"> Disattivato</span> , l'indirizzo IP viene lasciato nei dati. </p> <p>Selezionando l’indirizzo <span class="uicontrol"> IP</span> offuscato, l’IP viene modificato in un valore con hash (ad esempio, 234abc6493872038). </p> <p>Selezionando <span class="uicontrol"> Rimuovi indirizzo</span> IP, l'indirizzo IP viene sostituito con x.x.x.x nei dati, dopo la ricerca geografica. </p> <p>Nota: Questa impostazione potrebbe richiedere modifiche alle regole <a href="../../admin/admin/bot-removal/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7" format="dita" scope="local"> bot personalizzate o alle</a> esclusioni<a href="../../admin/admin/exclude-ip.md#concept_265A95A803F740629CAAAA7EB8BE81A4" format="dita" scope="local"></a>IP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Archiviazione ID transazione</span> </td> 
   <td colname="col2"> <p>Consente di utilizzare le origini dati ID <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_Transaction_ID.html" format="https" scope="external"></a> transazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Attiva analisi ad hoc</span> </td> 
   <td colname="col2"> <p>Indica se la suite di rapporti in questione viene visualizzata come una suite di rapporti disponibile in Analisi ad hoc. Utilizzate questa impostazione per limitare le suite di rapporti visualizzate come opzione per l'analisi ad hoc. Ad esempio, puoi disabilitare Analisi ad hoc per lo sviluppo e le suite di rapporti per il controllo della qualità. </p> </td> 
  </tr> 
  <tr> 
   <td><span class="wintitle"> Abilita Data Warehouse</span> </td> 
   <td colname="col2"> <p>Abilita l'interfaccia utente di Data Warehouse in <span class="uicontrol"> Strumenti</span> &gt;<span class="uicontrol"> Data Warehouse</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

