---
description: I diritti delle metriche calcolate sono diversi tra utenti a livello di amministratore e non amministratori.
title: Metriche calcolate, diritti basati su ruoli
uuid: 7c14d32d-370c-4afa-8f80-5bbd8fc12ec7
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Metriche calcolate: diritti basati su ruolo

I diritti delle metriche calcolate sono diversi tra utenti a livello di amministratore e non amministratori.

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
   <td colname="col02"> Gli amministratori possono creare metriche calcolate e <a href="https://marketing.adobe.com/resources/help/en_US/reference/groups.html"  > gruppi </a> per limitare i diritti degli utenti di creare metriche calcolate. </td> 
   <td colname="col2"> Può essere condiviso con l’intera società, con i gruppi di utenti e con i singoli utenti. </td> 
   <td colname="col3"> <span class="keyword"> [!UICONTROL Reports &amp; Analytics] </span>: Può visualizzare/modificare/eliminare/ecc. metriche calcolate personalizzate e di altri utenti. <p> <span class="keyword"> Analisi ad hoc </span> e Generatore di <span class="keyword"> report </span>: Può visualizzare/modificare/eliminare/ecc. le proprie metriche calcolate e quelle condivise con esse. </p> </td> 
   <td colname="col4"> Può approvare metriche calcolate come canoniche. </td> 
   <td colname="col5"> Può applicare qualsiasi metrica calcolata all'intera organizzazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Utenti non amministratori</b> </td> 
   <td colname="col02"> Per impostazione predefinita, gli utenti possono creare metriche calcolate. Tuttavia, questi diritti possono essere limitati dagli amministratori. </td> 
   <td colname="col2"> Condivisione con singoli utenti </td> 
   <td colname="col3">  Può visualizzare/modificare/eliminare/ecc. solo le proprie metriche calcolate. <p>Gli utenti non amministratori devono avere accesso a tutti gli eventi dei componenti per poter visualizzare le metriche condivise (le autorizzazioni in Admin Console sono ancora applicate). </p> <p>Se un dashboard o un report pianificato viene condiviso con un utente non amministratore e non ha la metrica condivisa con lui, il report verrà eseguito con la metrica applicata (sempre che disponga delle autorizzazioni necessarie per visualizzare gli eventi). Tuttavia, non potranno visualizzare la definizione o modificare la metrica. </p> </td> 
   <td colname="col4"> Può utilizzare solo metriche calcolate approvate; impossibile contrassegnare come approvato. </td> 
   <td colname="col5"> Può applicare le proprie metriche calcolate e i segmenti condivisi con loro. </td> 
  </tr> 
 </tbody> 
</table>

