---
description: La pagina Metodi di ricerca identifica il modo in cui i vari rapporti sui metodi di ricerca ricevono credito per gli eventi di successo della conversione sul sito. Ad esempio, se un motore di ricerca fa riferimento a un visitatore del sito che effettua un acquisto, i metodi di ricerca specificano in che modo il motore di ricerca riceve credito per il riferimento.
title: Metodi di ricerca
feature: Strumenti di amministrazione
uuid: 1053993e-7fc4-4874-84fa-367ecdcd7b45
exl-id: 58c4510c-2343-4b0a-9c09-5583f6d4250f
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 2%

---

# Metodi di ricerca

La pagina Metodi di ricerca identifica il modo in cui i vari rapporti sui metodi di ricerca ricevono credito per gli eventi di successo della conversione sul sito. Ad esempio, se un motore di ricerca fa riferimento a un visitatore del sito che effettua un acquisto, i metodi di ricerca specificano in che modo il motore di ricerca riceve credito per il riferimento.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Finding Methods]**.

## Descrizioni dei metodi di ricerca {#section_8B6278DB75224EAB9F49D89A86274E8A}

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
   <td colname="col2"> Il metodo di ricerca che si desidera modificare </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allocazione </td> 
   <td colname="col2"> Specifica come applicare il credito per un riferimento. Le opzioni di allocazione supportate includono: <p> <span class="uicontrol"> Più recente (ultimo):  </span> Attribuisce tutto il credito all’ultimo referente (impostazione predefinita). </p> <p> <span class="uicontrol"> Valore originale:  </span> Attribuisce tutto il merito al primo referente. </p> <p> <span class="uicontrol"> Lineare:  </span>Divide il credito tra tutti i referrer equamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scade dopo </td> 
   <td colname="col2"> 
    <ul id="ul_95EB224CAD164E9997B148E08AFA5F9B"> 
     <li id="li_C240460C21E14AA498D2EA62B9354710"> <span class="uicontrol"> Visita:  </span> dopo un determinato periodo di inattività; di solito circa 30 minuti. </li> 
     <li id="li_A3AE5438919E44B68DF99BEEA60C44EE"> <span class="uicontrol"> Visualizzazione pagina:  </span> Non appena si apre qualsiasi pagina del sito. </li> 
     <li id="li_D5E20FEF313E4C5B99E7097CA175761A"> <span class="uicontrol"> Minuto:  </span> Dopo 1 minuto di inattività. </li> 
     <li id="li_7315AA3EDDBB47A2BEA3C173881378A1"> <span class="uicontrol"> Acquisto:  </span> Al momento dell'acquisto. </li> 
     <li id="li_C0CF07581654472C9C9EC944E6F18164"> <span class="uicontrol"> Visualizzazione prodotto:  </span> Quando un visitatore visualizza una pagina web del prodotto. </li> 
     <li id="li_A1B04065150B407491D2EC78EC0DBDF5"> <span class="uicontrol"> Apri carrello:  </span> Quando un visitatore apre un nuovo carrello acquisti online. </li> 
     <li id="li_2AA50C6B9CB14500B67909CDF2AA700C"> <span class="uicontrol"> Pagamento carrello:  </span> Quando un visitatore effettua il check-out utilizzando un carrello acquisti online. </li> 
     <li id="li_F58CE6FB8DCE4BE4927FFCB35A6D8E31"> <span class="uicontrol"> Aggiungi carrello:  </span> Quando un visitatore aggiunge un prodotto a un carrello online. </li> 
     <li id="li_AD7C846F46604FC48E0919ACB7515E14"> <span class="uicontrol"> Rimuovi carrello:  </span> Quando un visitatore rimuove un prodotto da un carrello online. </li> 
     <li id="li_EB66E0563F564C9F985BE922DABD0A56"> <span class="uicontrol"> Apri carrello:  </span> Quando un visitatore visualizza il contenuto di un carrello acquisti online. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Tutti i metodi di ricerca scadono al termine della visita. Se scegli Scadenza dopo un evento diverso (ad esempio, Cart Checkout), il metodo di ricerca scade quando il Cart Checkout si verifica durante la visita. Se durante la visita non si verifica un Check-Out del carrello, il Metodo di ricerca scade al termine della visita.
