---
description: Elenco di variabili personalizzate utilizzate in Analytics.
keywords: Implementazione di Analytics
seo-description: Elenco di variabili personalizzate utilizzate in Analytics.
seo-title: Variabili personalizzate
solution: Analytics
title: Variabili personalizzate
topic: Sviluppatore e implementazione
uuid: 54 adf 622-7 f 05-49 c 0-b 7 e 6-702 bb 2 f 17 b 1 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variabili personalizzate

Elenco di variabili personalizzate utilizzate in Analytics.

<table id="table_E8C7871F63F648A59644638FB56BD0E1"> 
 <thead> 
  <tr> 
   <th class="entry"> Variabile </th> 
   <th class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Variabili di traffico </td> 
   <td> Verificate il valore di prop 1 - 75. Elenco di elementi da controllare. 
    <ul id="ul_0EE2D50BA90F4F21BD63268A5082F980"> 
     <li id="li_A6E4D66E8A03400491A26A08E4945908">È utilizzata la pratica corretta? «Valuea» è un record diverso da «valuea». Potete utilizzare tutti minuscoli perché un piccolo sottoinsieme di browser converte tutte le variabili in minuscole. </li> 
     <li id="li_65CBFB908E7B4ED5AF9518FE5B58D4E2">Sono disponibili valori inferiori a 100 caratteri? In caso contrario, può verificarsi un ritaglio dei valori. </li> 
     <li id="li_CC506D114AFE44699D89AB84BBCCEBFC"> Sono presenti tutti i valori in una singola variabile correlata, o se alcuni valori sono fuori sede? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Variabili di conversione </td> 
   <td> <span class="wintitle"> Le</span> variabili di Econversion includono evar 1 - 75. Di seguito è riportato un elenco dei problemi che consentono di controllare le seguenti situazioni. 
    <ul id="ul_CA10C5B9F24B4C49A64CA84A9DCE8E63"> 
     <li id="li_8CCD92F3AD5E49EBA91C9B008DA47016">È utilizzata la pratica corretta? «Valuea» è un record diverso da «valuea». Potete utilizzare tutti minuscoli perché un piccolo sottoinsieme di browser converte tutte le variabili in minuscole. </li> 
     <li id="li_5B6FDEDB2C32409AA59D6BB0DF2346CB">Sono disponibili valori inferiori a 255 caratteri? In caso contrario, può verificarsi un ritaglio dei valori. </li> 
     <li id="li_C31AFBAC99D84E96A1244E795CE7765D">Tutti i valori sono relativi a una singola evar, oppure alcuni valori sono fuori sede? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Eventi personalizzati </td> 
   <td> Events include both standard values (<span class="wintitle"> prodView</span>, <span class="wintitle"> scOpen</span>, <span class="wintitle"> scAdd</span>, <span class="wintitle"> scCheckout</span>, <span class="wintitle"> purchase</span>), as well as custom events from event1 to event100. Tutti gli eventi vengono inviati nella variabile degli eventi. Più eventi nella stessa pagina devono essere delimitati da virgole (nessuno spazio vuoto). 
    <ul id="ul_2213CC9DE892433FAF6FC1F5A2B841B4"> 
     <li id="li_15E31A9FF1654DFA93C158F422B9EAE3">Per tutti gli eventi di conversione standard, i prodotti devono essere compilati anche con i prodotti applicabili. Per tutti gli eventi tranne l'acquisto, gli elementi di qty e price sono facoltativi. </li> 
     <li id="li_03ED9AAC45DA47A58AB482E2CEBF5108">The <span class="wintitle"> purchase</span> event, must be set only once in a session after the purchase has been completed and confirmed. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

