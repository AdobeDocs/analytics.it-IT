---
description: Utilizzate la sezione Feed informazioni per denominare il feed, specificare la suite di rapporti in cui eseguire il feed, determinare la ricorrenza del feed e specificare l'inizio e la fine del feed.
keywords: Feed dati; informazioni; name; suite di rapporti; e-mail al termine; email; interval; feed; ritardo elaborazione; delay; start; end; date; feed continuo
seo-description: Utilizzate la sezione Feed informazioni per denominare il feed, specificare la suite di rapporti in cui eseguire il feed, determinare la ricorrenza del feed e specificare l'inizio e la fine del feed.
seo-title: Informazioni sui feed
solution: Analytics
title: Informazioni sui feed
uuid: adf 92 f 42-a 957-4 de 0-a 5 a 1-683 f 2933 af 04
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Informazioni sui feed

Utilizzate la sezione Feed informazioni per denominare il feed, specificare la suite di rapporti in cui eseguire il feed, determinare la ricorrenza del feed e specificare l'inizio e la fine del feed.

![](assets/feed-info.jpg)

<table id="table_C98C7C3CE4194BEF819E792793EBC517">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Campo </th>
   <th colname="col2" class="entry"> Descrizione </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nome (Obbligatorio) </p> </td>
   <td colname="col2"> <p>Immettete un nome di feed. </p> <p>Il nome deve essere univoco nella suite di rapporti selezionata e può contenere fino a 255 caratteri. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Suite di rapporti (obbligatorio) </p> </td>
   <td colname="col2"> <p>Specifica le suite di rapporti per la query feed. </p> <p>È necessario selezionare almeno una suite di rapporti. Non è possibile elencare due volte la stessa suite di rapporti. </p> <p>Tutte le suite di rapporti non virtuali disponibili per l'utente connesso sono disponibili. </p></td>
  </tr>
  <tr>
   <td colname="col1"> <p>E-mail al termine (obbligatorio) </p> </td>
   <td colname="col2"> <p>Specificate il destinatario dell'e-mail che riceverà gli aggiornamenti della distribuzione dei feed. </p> <p>Questo campo non può essere vuoto. Deve contenere un indirizzo e-mail formattato correttamente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Intervallo di feed (richiesto) </p> </td>
   <td colname="col2"> <p>Specifica la ricorrenza della pianificazione. </p> <p>Nota: A causa della dimensione potenziale dei file ZIP dei feed di dati, accertatevi che il processo ETL utilizzi un'utility ZIP a 64 bit. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Ritardo elaborazione (facoltativo) </p> </td>
   <td colname="col2"> <p>Specificate il ritardo da applicare a ciascuna istanza di pianificazione. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Data di inizio e fine (obbligatorio) </p> <p>Feed continuo (facoltativo) </p> </td>
   <td colname="col2"> <p>Pianificate le date in cui il feed verrà avviato e finale. </p> <p>
     <ul id="ul_509977336CD34032924B48E043E8CBC7">
      <li id="li_BFB5B6ADCB184D839C9BA42DB3DCAF32">Data di inizio: impostazioni predefinite per la data odierna </li>
      <li id="li_34F8DB45D9B54076840D1A0B782812D3">Data di fine: impostazioni predefinite per la data di domani </li>
     </ul>
     </p> </td>
  </tr>
 </tbody>
</table>