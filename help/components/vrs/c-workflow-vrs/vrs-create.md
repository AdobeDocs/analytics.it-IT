---
description: Prima di iniziare a creare suite di rapporti virtuali, tenete presente alcune informazioni.
keywords: Suite di rapporti virtuali
seo-description: Prima di iniziare a creare suite di rapporti virtuali, tenete presente alcune informazioni.
seo-title: Creare suite di rapporti virtuali
solution: Analytics
title: Creare suite di rapporti virtuali
topic: Reports & Analytics
uuid: 022 a 6656-808 e -4 c 92-b 7 ec -4 d 2 a 42 e 84 fa 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Creare suite di rapporti virtuali

Prima di iniziare a creare suite di rapporti virtuali, tenete presente alcune informazioni.

* Gli utenti non amministratori non possono visualizzare il gestore suite di rapporti virtuale.
* Le suite di rapporti virtuali non possono essere condivise. " Condivisione "viene effettuata tramite gruppi/autorizzazioni.
* Nella suite di rapporti virtuali, puoi vedere solo le tue suite di rapporti virtuali. È necessario fare clic su «Mostra tutti» per vedere gli altri.

1. Navigate to **[!UICONTROL Components]** &gt; **[!UICONTROL Virtual Report Suites]**.
1. Fai clic su **[!UICONTROL Add +]**.

   ![](assets/new_vrs.png)

1. Compila i campi:

<table id="table_0F85B56480BB46CBA5BE236BBD70156D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> <p>Il nome della suite di rapporti virtuali non viene ereditato dalla suite di rapporti principale e deve essere distinto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descrizione </td> 
   <td colname="col2"> <p>Aggiungi una descrizione valida a beneficio degli utenti aziendali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tag </td> 
   <td colname="col2"> <p>Puoi aggiungere tag per organizzare le suite di rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groups (Gruppi) </td> 
   <td colname="col2"> <p>Seleziona i gruppi di autorizzazioni che desideri accedere a questa VRS. (You can also manage group permissions from <span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> User Management</span> &gt; <span class="uicontrol"> Groups</span></span>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suite di rapporti principale </td> 
   <td colname="col2"> <p>La suite di rapporti dalla quale questa suite di rapporti virtuali eredita le impostazioni seguenti. La maggior parte dei livelli e delle funzioni del servizio (ad esempio le impostazioni evar, le regole di elaborazione, le classificazioni e così via) vengono ereditate. To make a changes to these inherited settings on a VRS, you must edit the parent report suite (<span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Report Suites</span></span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fuso orario </td> 
   <td colname="col2"> <p>La scelta di un fuso orario è facoltativa. </p> <p>Se scegliete un fuso orario, verrà salvato insieme alla VRS. Se non si seleziona un fuso orario, verrà utilizzato quello della suite di rapporti padre. </p> <p>Quando si modifica una VRS, il fuso orario salvato con la VRS viene visualizzato nel selettore a discesa. Se la VRS è stata creata prima del supporto del fuso orario, nel selettore a discesa viene visualizzato il fuso orario della suite di rapporti principale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segmenti </td> 
   <td colname="col2"> <p>You can add just one segment or you can <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_stack.html" format="https" scope="external"> stack segments</a>. </p> <p> <p>Nota: Quando si sovrappongono due segmenti, questi vengono uniti da un'istruzione AND. Non può essere modificato in un'istruzione OR. </p> </p> <p>Quando tentate di eliminare o modificare un segmento attualmente utilizzato in una suite di rapporti virtuale, viene visualizzato un avviso. </p> </td> 
  </tr> 
 </tbody> 
</table>

