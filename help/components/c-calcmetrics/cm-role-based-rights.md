---
description: I diritti di metrica calcolati differiscono tra gli utenti di livello amministratore e non gli amministratori.
seo-description: I diritti di metrica calcolati differiscono tra gli utenti di livello amministratore e non gli amministratori.
seo-title: Metriche calcolate per i diritti basati sul ruolo
title: Metriche calcolate per i diritti basati sul ruolo
uuid: 7 c 14 d 32 d -370 c -4 afa -8 f 80-5 bbd 8 fc 12 ec 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Metriche calcolate: diritti basati su ruolo

I diritti di metrica calcolati differiscono tra gli utenti di livello amministratore e non gli amministratori.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> Creare    </th> 
   <th colname="col2" class="entry"> Condividi </th> 
   <th colname="col3" class="entry"> Visualizza/Gestisci </th> 
   <th colname="col4" class="entry"> Approva </th> 
   <th colname="col5" class="entry"> Applica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Utenti a livello di amministratore</b> </td> 
   <td colname="col02"> Admins can create calculated metrics as well as create <a href="https://marketing.adobe.com/resources/help/en_US/reference/groups.html" format="https" scope="external"> groups </a> to limit the rights of users to create calculated metrics. </td> 
   <td colname="col2"> Può essere condiviso con l'intera azienda, con gruppi di utenti e con singoli utenti. </td> 
   <td colname="col3"> <span class="keyword"> [! UICONTROL Reporting &amp; Analytics] </span>: Può visualizzare/modificare/eliminare/ecc. le metriche calcolate di altri utenti e di altri utenti. <p> <span class="keyword"> Analisi ad hoc </span> e <span class="keyword"> Generatore </span>di report: Può visualizzare/modificare/eliminare/ecc. le relative metriche calcolate e quelle condivise con loro. </p> </td> 
   <td colname="col4"> Può approvare le metriche calcolate come canonical. </td> 
   <td colname="col5"> Può applicare qualsiasi metrica calcolata nell'intera organizzazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Utenti non amministratori</b> </td> 
   <td colname="col02"> Per impostazione predefinita, gli utenti possono creare metriche calcolate. Tuttavia, tali diritti possono essere limitati dagli amministratori. </td> 
   <td colname="col2"> Può essere condiviso solo con singoli utenti </td> 
   <td colname="col3"> Può visualizzare/modificare/eliminare/ecc. solo le proprie metriche calcolate. <p>Gli utenti non amministratori devono avere accesso a tutti gli eventi dei componenti per poter visualizzare una metrica condivisa (le autorizzazioni nell'Admin Console sono ancora applicate). </p> <p>Se una dashboard o un rapporto pianificato viene condiviso con un utente non amministratore e non dispone della metrica condivisa con loro, il rapporto verrà eseguito con la metrica applicata (purché abbiano le autorizzazioni per visualizzare gli eventi). Tuttavia, non potranno vedere la definizione o modificare la metrica. </p> </td> 
   <td colname="col4"> Può utilizzare solo metriche calcolate approvate; non può essere contrassegnato come approvato. </td> 
   <td colname="col5"> Può applicare le proprie metriche calcolate e segmenti che sono stati condivisi con loro. </td> 
  </tr> 
 </tbody> 
</table>

