---
description: Descrizioni dei campi in Gestione tag dinamica per il tracciamento dei collegamenti durante la distribuzione di Analytics.
keywords: Gestione tag dinamica; tracciamento dei collegamenti; enable clickmap; tenere traccia dei collegamenti di scaricamento; estensioni di download; tracciare collegamenti in uscita; mantieni parametri url
seo-description: Descrizioni dei campi in Gestione tag dinamica per il tracciamento dei collegamenti durante la distribuzione di Analytics.
seo-title: Tracciamento dei collegamenti
solution: Marketing Cloud, Analytics, Gestione tag dinamica
title: Tracciamento dei collegamenti
uuid: 982 b 744 b -5696-4 c 31-b 1 d 1-410486 b 0 eedd
translation-type: tm+mt
source-git-commit: 1bc1c7a1e00d7b59cd39f368ac9afb745bea9e47

---


# Tracciamento dei collegamenti

Descrizioni dei campi in Gestione tag dinamica per il tracciamento dei collegamenti durante la distribuzione di Analytics.

**[!UICONTROL  *`Property`*]**&gt;** [! UICONTROL![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Link Tracking]**

<table id="table_F23FB0B284E74B66A107B1D69D22A51C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abilita ClickMap </td> 
   <td colname="col2"> <p>Determina se i dati della mappa clic del visitatore vengono raccolti. </p> <p>See <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.trackInlineStats</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tenere traccia dei collegamenti di scaricamento </td> 
   <td colname="col2"> <p>Tiene traccia dei collegamenti verso file scaricabili sul sito. </p> <p>Consultate [Variabili di configurazione] (/help/implementation/js-implementation/c-variables/configuration-variables. md).</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Download delle estensioni </td> 
   <td colname="col2"> <p>Se il sito contiene collegamenti a file con una qualsiasi delle estensioni elencate, nel rapporto saranno visualizzati gli URL di tali collegamenti. </p>Consultate [Variabili di configurazione] (/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tenere traccia dei collegamenti in uscita </td> 
   <td colname="col2"> <p>Determina se un collegamento a cui è stato fatto clic è un collegamento di uscita. </p> <p>Consultate [Variabili di configurazione] (/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> <p><b>Considerazioni sull'app su una sola pagina: </b>A causa del modo in cui alcuni siti Web di SPA sono codificati, un collegamento interno a una pagina sul sito SPA potrebbe avere un collegamento in uscita. </p> <p>Puoi usare uno dei seguenti metodi per tenere traccia dei collegamenti in uscita dai siti SPA: </p> 
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9"> 
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>If you do not want to track any outbound links from your SPA, insert an entry into the <span class="wintitle"> Never Track</span> section. </p> <p>For example, <span class="filepath"> https://testsite.com/spa/#</span> </p> <p>Tutti i # link a questo host vengono ignorati. All outbound links to other hosts are tracked, such as <span class="filepath"> https://www.google.com</span>. </p> </li> 
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>If there are some links that you want to track on your SPA, use the <span class="wintitle"> Always Track</span> section. </p> <p>For example, if you have a <span class="filepath"> spa/#/about</span> page, you could put "about" in the <span class="wintitle"> Always Track</span> section. </p> <p>La pagina «about» è l'unico collegamento in uscita tracciato. Any other links on the page (for example, <span class="filepath"> https://www.google.com</span>) are not tracked. </p> </li> 
    </ul> <p>Queste due opzioni si escludono a vicenda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mantieni parametri URL </td> 
   <td colname="col2"> <p>Mantiene le stringhe di query. </p> <p>Consultate [Variabili di configurazione] (/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> </td> 
  </tr> 
 </tbody> 
</table>

