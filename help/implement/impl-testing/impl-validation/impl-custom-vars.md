---
description: Elenco delle variabili personalizzate utilizzate in Analytics.
keywords: Implementazione di Analytics
seo-description: Elenco delle variabili personalizzate utilizzate in Analytics.
seo-title: Variabili personalizzate
solution: Analytics
title: Variabili personalizzate
topic: Sviluppatore e implementazione
uuid: 54adf622-7f05-49c0-b7e6-702bb2f17b1c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Variabili personalizzate

Elenco delle variabili personalizzate utilizzate in Analytics.

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
   <td> Controllare il valore di prop1 - 75. Elenco di controllo degli elementi da controllare.
    <ul id="ul_0EE2D50BA90F4F21BD63268A5082F980"> 
     <li id="li_A6E4D66E8A03400491A26A08E4945908">Viene utilizzato il caso corretto? "ValueA" è un record diverso da "valueA". È possibile utilizzare tutte le lettere minuscole poiché un piccolo sottoinsieme di browser converte tutte le variabili in lettere maiuscole. </li> 
     <li id="li_65CBFB908E7B4ED5AF9518FE5B58D4E2">I valori sono inferiori a 100 caratteri? In caso contrario, è possibile che i valori vengano ritagliati. </li> 
     <li id="li_CC506D114AFE44699D89AB84BBCCEBFC"> Tutti i valori di una singola variabile di proprietà sono correlati oppure alcuni valori risultano fuori luogo? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Variabili di conversione </td> 
   <td> <span class="wintitle"> Le variabili di conversione</span> includono eVar 1 - 75. Di seguito è riportato un elenco di problemi da verificare:
    <ul id="ul_CA10C5B9F24B4C49A64CA84A9DCE8E63"> 
     <li id="li_8CCD92F3AD5E49EBA91C9B008DA47016">Viene utilizzato il caso corretto? "ValueA" è un record diverso da "valueA". È possibile utilizzare tutte le lettere minuscole poiché un piccolo sottoinsieme di browser converte tutte le variabili in lettere maiuscole. </li> 
     <li id="li_5B6FDEDB2C32409AA59D6BB0DF2346CB">I valori sono inferiori a 255 caratteri? In caso contrario, è possibile che i valori vengano ritagliati. </li> 
     <li id="li_C31AFBAC99D84E96A1244E795CE7765D">Tutti i valori di una singola eVar sono correlati, oppure alcuni valori risultano fuori luogo? </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Eventi personalizzati </td> 
   <td> Gli eventi includono sia valori standard (<span class="wintitle"> prodView</span>, <span class="wintitle"> scOpen</span>, <span class="wintitle"> scAdd</span>, <span class="wintitle"> scCheckout</span>, <span class="wintitle"> purchase</span>), sia eventi personalizzati da event1 a event100. Tutti gli eventi vengono inviati nella variabile degli eventi. Più eventi sulla stessa pagina devono essere delimitati da virgole (senza spazi vuoti).
    <ul id="ul_2213CC9DE892433FAF6FC1F5A2B841B4"> 
     <li id="li_15E31A9FF1654DFA93C158F422B9EAE3">Per tutti gli eventi di conversione standard, i prodotti devono essere compilati con i prodotti applicabili. Per tutti gli eventi eccetto acquisto, gli elementi relativi alla quantità e al prezzo sono facoltativi. </li> 
     <li id="li_03ED9AAC45DA47A58AB482E2CEBF5108">L'evento di <span class="wintitle"> acquisto</span> deve essere impostato una sola volta in una sessione dopo che l'acquisto è stato completato e confermato. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

