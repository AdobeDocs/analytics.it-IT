---
description: Utilizzate la sezione Informazioni feed per denominare il feed, specificare la suite di rapporti con cui eseguire il feed, determinare la ricorrenza del feed e specificare quando il feed inizia e termina.
keywords: Feed di dati;informazioni;nome;suite di rapporti;e-mail quando completo;intervallo;feed;ritardo;ritardo;inizio;fine;data;feed continuo
seo-description: Utilizzate la sezione Informazioni feed per denominare il feed, specificare la suite di rapporti con cui eseguire il feed, determinare la ricorrenza del feed e specificare quando il feed inizia e termina.
seo-title: Informazioni sui feed
solution: Analytics
title: Informazioni sui feed
uuid: adf92f42-a957-4de0-a5a1-683f2933af04
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# Informazioni sui feed

Utilizzate la sezione Informazioni feed per denominare il feed, specificare la suite di rapporti con cui eseguire il feed, determinare la ricorrenza del feed e specificare quando il feed inizia e termina.

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
   <td colname="col2"> <p>Immettete un nome per il feed. </p> <p>Il nome deve essere univoco nella suite di rapporti selezionata e può contenere fino a 255 caratteri. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Suite di rapporti (richiesta) </p> </td>
   <td colname="col2"> <p>Specificate le suite di rapporti per la query di feed. </p> <p>È necessario selezionare almeno una suite di rapporti. Non puoi elencare due volte la stessa suite di rapporti. </p> <p>Sono disponibili tutte le suite di rapporti non virtuali disponibili per l'utente che ha effettuato l'accesso. </p></td>
  </tr>
  <tr>
   <td colname="col1"> <p>E-mail al termine (obbligatorio) </p> </td>
   <td colname="col2"> <p>Specificate il destinatario e-mail che riceverà gli aggiornamenti per la distribuzione dei feed. </p> <p>Questo campo non può essere vuoto. Deve contenere un indirizzo e-mail formattato correttamente. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Intervallo feed (obbligatorio) </p> </td>
   <td colname="col2"> <p>Specificate la ricorrenza della pianificazione. </p> <p>Nota:  A causa delle potenziali dimensioni dei file zip dei feed di dati, accertatevi che il processo ETL utilizzi un’utility zip a 64 bit. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Ritardo (facoltativo) </p> </td>
   <td colname="col2"> <p>Specificare il ritardo da applicare a ogni istanza di programmazione. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Data di inizio e di fine (richiesta) </p> <p>Feed continuo (facoltativo) </p> </td>
   <td colname="col2"> <p>Pianificare le date in cui il feed inizierà e terminerà. </p> <p>
     <ul id="ul_509977336CD34032924B48E043E8CBC7">
      <li id="li_BFB5B6ADCB184D839C9BA42DB3DCAF32">Data inizio: impostazione predefinita per la data odierna </li>
      <li id="li_34F8DB45D9B54076840D1A0B782812D3">Data di fine: impostazione predefinita per la data di domani </li>
     </ul>
     </p> </td>
  </tr>
 </tbody>
</table>
