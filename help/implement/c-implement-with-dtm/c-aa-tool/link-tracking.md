---
description: Descrizioni dei campi in Gestione tag dinamica per il tracciamento dei collegamenti durante la distribuzione di Analytics.
keywords: Gestione tag dinamica;tracciamento collegamenti;abilita clic;tracciare collegamenti per il download;scaricare estensioni;tracciare collegamenti in uscita;mantenere i parametri degli URL
seo-description: Descrizioni dei campi in Gestione tag dinamica per il tracciamento dei collegamenti durante la distribuzione di Analytics.
seo-title: Tracciamento dei collegamenti
solution: Experience Cloud,Analytics,Gestione tag dinamica
title: Tracciamento dei collegamenti
uuid: 982b744b-5696-4c31-b1d1-410486b0eedd
translation-type: tm+mt
source-git-commit: 506c670e4b2903cc71bb6880cd74c3392bbc751c

---


# Tracciamento dei collegamenti

Descrizioni dei campi in Gestione tag dinamica per il tracciamento dei collegamenti durante la distribuzione di Analytics.

**[!UICONTROL  *`Property`*]**&gt; **[!UICONTROL![](assets/settings_gear.png)

Modifica strumento]** &gt; **[!UICONTROL Link Tracking]**

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
   <td colname="col2"> <p>Determina se i dati della mappa clic visitatore vengono raccolti. </p> <p>Vedere <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.trackInlineStats</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Traccia collegamenti di download </td> 
   <td colname="col2"> <p>Tiene traccia dei collegamenti verso file scaricabili sul sito. </p> <p>See <a href="/help/implement/js-implementation/c-variables/configuration-variables.md">Configuration Variables</a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Download delle estensioni </td> 
   <td colname="col2"> <p>Se il sito contiene collegamenti a file con una delle estensioni elencate, gli URL di questi collegamenti verranno visualizzati nei rapporti. </p>See <a href="/help/implement/js-implementation/c-variables/configuration-variables.md">Configuration Variables</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Traccia collegamenti in uscita </td> 
   <td colname="col2"> <p>Determina se un collegamento su cui è stato fatto clic è un collegamento di uscita. </p> <p>See <a href="/help/implement/js-implementation/c-variables/configuration-variables.md">Configuration Variables</a>. </p> <p><b>Considerazioni sulle app su una sola pagina (SPA):</b> a seconda del modo in cui alcuni siti Web SPA sono codificati, un collegamento interno a una pagina del sito SPA potrebbe sembrare un collegamento in uscita. </p> <p>Puoi usare uno dei seguenti metodi per tenere traccia dei collegamenti in uscita dai siti SPA: </p> 
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9"> 
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>Se non desideri tenere traccia dei collegamenti in uscita dalla tua SPA, inserisci una voce nella sezione <span class="wintitle"> Never Track.</span> </p> <p>Ad esempio, <span class="filepath"> https://testsite.com/spa/#</span> </p> <p>Tutti i collegamenti # a questo host vengono ignorati. Vengono tracciati tutti i collegamenti in uscita ad altri host, ad esempio <span class="filepath"></span>https://www.google.com. </p> </li> 
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>If there are some links that you want to track on your SPA, use the <span class="wintitle"> Always Track</span> section. </p> <p>For example, if you have a <span class="filepath"> spa/#/about</span> page, you could put "about" in the <span class="wintitle"> Always Track</span> section. </p> <p>La pagina "Info" è l'unico collegamento in uscita tracciato. Qualsiasi altro collegamento sulla pagina (ad esempio, <span class="filepath"></span>https://www.google.com) non è tracciato. </p> </li> 
    </ul> <p>Queste due opzioni si escludono a vicenda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mantieni parametri URL </td> 
   <td colname="col2"> <p>Mantiene le stringhe di query. </p> <p>See <a href="/help/implement/js-implementation/c-variables/configuration-variables.md">Configuration Variables</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
