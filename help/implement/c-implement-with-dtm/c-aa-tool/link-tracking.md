---
description: Descrizioni dei campi in Gestione tag dinamica per il tracciamento dei collegamenti durante la distribuzione di Analytics.
keywords: Gestione tag dinamica;tracciamento collegamenti;abilita clic;tracciare collegamenti per il download;scaricare estensioni;tracciare collegamenti in uscita;mantenere i parametri degli URL
seo-description: Descrizioni dei campi in Gestione tag dinamica per il tracciamento dei collegamenti durante la distribuzione di Analytics.
seo-title: Tracciamento dei collegamenti
solution: Experience Cloud,Analytics,Gestione tag dinamica
title: Tracciamento dei collegamenti
uuid: 982b744b-5696-4c31-b1d1-410486b0eedd
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

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
   <td colname="col1"> Tracciare i collegamenti di download </td> 
   <td colname="col2"> <p>Tiene traccia dei collegamenti ai file scaricabili sul sito. </p> <p>Consulta [Variabili di configurazione](/help/implementation/js-implementation/c-variables/configuration-variables. md).</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scarica estensioni </td> 
   <td colname="col2"> <p>Se il sito contiene collegamenti a file con una delle estensioni elencate, gli URL di questi collegamenti verranno visualizzati nei rapporti. </p>Consulta [Variabili di configurazione](/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tracciare i collegamenti in uscita </td> 
   <td colname="col2"> <p>Determina se un collegamento selezionato è un collegamento di uscita. </p> <p>Consulta [Variabili di configurazione](/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> <p><b>Considerazioni sulle app a pagina singola: A </b>causa del modo in cui alcuni siti SPA sono codificati, un collegamento interno a una pagina del sito SPA potrebbe essere simile a un collegamento in uscita. </p> <p>Per tenere traccia dei collegamenti in uscita dai siti SPA, potete usare uno dei seguenti metodi: </p> 
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9"> 
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>Se non si desidera tracciare alcun collegamento in uscita dall'SPA, inserire una voce nella sezione <span class="wintitle"> Mai tracciamento</span> . </p> <p>Ad esempio, <span class="filepath"> https://testsite.com/spa/#</span> </p> <p>Tutti i collegamenti # a questo host vengono ignorati. Tutti i collegamenti in uscita verso altri host vengono tracciati, ad esempio <span class="filepath"> https://www.google.com</span>. </p> </li> 
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>Se alcuni collegamenti che desiderate monitorare nell’area SPA, utilizzate la sezione <span class="wintitle"> Traccia</span> sempre. </p> <p>Ad esempio, se disponete di una pagina <span class="filepath"> spa/#/about</span> , potete inserire "about" nella sezione <span class="wintitle"> Always Track</span> . </p> <p>La pagina "informazioni" è l’unico collegamento in uscita tracciato. Eventuali altri collegamenti sulla pagina (ad esempio, <span class="filepath"> https://www.google.com</span>) non vengono tracciati. </p> </li> 
    </ul> <p>Queste due opzioni si escludono a vicenda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mantieni parametri URL </td> 
   <td colname="col2"> <p>Mantiene le stringhe di query. </p> <p>Consulta [Variabili di configurazione](/help/implementation/js-implementation/c-variables/configuration-variables. md). </p> </td> 
  </tr> 
 </tbody> 
</table>

