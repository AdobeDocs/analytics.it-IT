---
description: La pagina Metodi di ricerca identifica il modo in cui i vari rapporti sui metodi di ricerca ricevono credito per gli eventi di successo di conversione sul sito. Ad esempio, se un motore di ricerca fa riferimento a un visitatore del sito che effettua un acquisto, i metodi di ricerca specificano il modo in cui il motore di ricerca riceve il credito per il riferimento.
solution: Analytics
title: Metodi di ricerca
topic: Admin tools
uuid: 1053993e-7fc4-4874-84fa-367ecdcd7b45
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Metodi di ricerca

La pagina Metodi di ricerca identifica il modo in cui i vari rapporti sui metodi di ricerca ricevono credito per gli eventi di successo di conversione sul sito. Ad esempio, se un motore di ricerca fa riferimento a un visitatore del sito che effettua un acquisto, i metodi di ricerca specificano il modo in cui il motore di ricerca riceve il credito per il riferimento.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Finding Methods]**.

## Ricerca di descrizioni dei metodi {#section_8B6278DB75224EAB9F49D89A86274E8A}

<table id="table_8ABC1C9BD63F419082E4C4C69E401526"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Metodo di ricerca da modificare </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allocazione </td> 
   <td colname="col2"> Specifica come applicare il credito per un riferimento. Le opzioni di allocazione supportate includono: <p> <span class="uicontrol"> Più recente (ultimo): Attribuisce </span> tutto il merito all'ultimo referente (impostazione predefinita). </p> <p> <span class="uicontrol"> Valore originale: Attribuisce </span> tutto il merito al primo referente. </p> <p> <span class="uicontrol"> Lineare: Divide </span>il credito tra tutti i referenti in modo uniforme. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scade dopo </td> 
   <td colname="col2"> 
    <ul id="ul_95EB224CAD164E9997B148E08AFA5F9B"> 
     <li id="li_C240460C21E14AA498D2EA62B9354710"> <span class="uicontrol"> Visita: </span> dopo un determinato periodo di inattività; di solito circa 30 minuti. </li> 
     <li id="li_A3AE5438919E44B68DF99BEEA60C44EE"> <span class="uicontrol"> Visualizzazione pagina: Non </span> appena si apre una qualsiasi pagina del sito. </li> 
     <li id="li_D5E20FEF313E4C5B99E7097CA175761A"> <span class="uicontrol"> Minuto: </span> Dopo 1 minuto di inattività. </li> 
     <li id="li_7315AA3EDDBB47A2BEA3C173881378A1"> <span class="uicontrol"> Acquisto: Al </span> momento dell'acquisto. </li> 
     <li id="li_C0CF07581654472C9C9EC944E6F18164"> <span class="uicontrol"> Visualizzazione prodotto: </span> Quando un visitatore visualizza una pagina Web di un prodotto. </li> 
     <li id="li_A1B04065150B407491D2EC78EC0DBDF5"> <span class="uicontrol"> Apertura carrello: </span> Quando un visitatore apre un nuovo carrello acquisti online. </li> 
     <li id="li_2AA50C6B9CB14500B67909CDF2AA700C"> <span class="uicontrol"> Checkout carrello: </span> Quando un visitatore effettua il check-out utilizzando un carrello online. </li> 
     <li id="li_F58CE6FB8DCE4BE4927FFCB35A6D8E31"> <span class="uicontrol"> Aggiungi carrello: </span> Quando un visitatore aggiunge un prodotto a un carrello online. </li> 
     <li id="li_AD7C846F46604FC48E0919ACB7515E14"> <span class="uicontrol"> Rimuovi carrello: </span> Quando un visitatore rimuove un prodotto da un carrello online. </li> 
     <li id="li_EB66E0563F564C9F985BE922DABD0A56"> <span class="uicontrol"> Apertura carrello: </span> Quando un visitatore visualizza il contenuto di un carrello acquisti online. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Tutti i metodi di ricerca scadono al termine della visita. Se si sceglie Scade dopo un altro evento (ad esempio, Cart Checkout), il metodo di ricerca scade quando si verifica il Cart Checkout durante la visita. Se durante la visita non si verifica un checkout carrello, il metodo di ricerca continua a scadere al termine della visita.

