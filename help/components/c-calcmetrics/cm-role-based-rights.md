---
description: I diritti delle metriche calcolate sono diversi tra utenti a livello di amministratore e non amministratori.
title: Diritti basati su ruolo delle metriche calcolate
uuid: 7c14d32d-370c-4afa-8f80-5bbd8fc12ec7
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 13%

---

# Metriche calcolate: diritti basati su ruolo

I diritti delle metriche calcolate sono diversi tra utenti a livello di amministratore e non amministratori.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> Creare </th> 
   <th colname="col2" class="entry"> Condividi </th> 
   <th colname="col3" class="entry"> Visualizza/Gestisci </th> 
   <th colname="col4" class="entry"> Approva </th> 
   <th colname="col5" class="entry"> Applica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Utenti amministratori</b> </td> 
   <td colname="col02"> Gli amministratori possono creare metriche calcolate e gruppi <a href="https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html"  > </a> per limitare i diritti degli utenti di creare metriche calcolate. </td> 
   <td colname="col2"> Possono condividere con l’azienda, con i gruppi di utenti e con i singoli utenti. </td> 
   <td colname="col3"> <span class="keyword"> Reports &amp; Analytics</span>: Possono visualizzare/modificare/eliminare/ecc. metriche calcolate personalizzate e di altri utenti. <p> <span class="keyword"> Report Builder  </span>: Possono visualizzare/modificare/eliminare/ecc. le proprie metriche calcolate e quelle condivise con esse. </p> </td> 
   <td colname="col4"> Può approvare le metriche calcolate come canoniche. </td> 
   <td colname="col5"> Può applicare qualsiasi metrica calcolata in tutta l’organizzazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Utenti non amministratori</b> </td> 
   <td colname="col02"> Per impostazione predefinita, gli utenti possono creare metriche calcolate. Tuttavia, questi diritti possono essere limitati dagli amministratori. </td> 
   <td colname="col2"> Possono condividere solo con singoli utenti </td> 
   <td colname="col3"> Possono visualizzare/modificare/eliminare/ecc. solo le proprie metriche calcolate. <p>Gli utenti non amministratori devono avere accesso a tutti gli eventi dei componenti per poter visualizzare una metrica condivisa (le autorizzazioni in Admin Console sono ancora applicate). </p> <p>Se un dashboard o un rapporto pianificato viene condiviso con un utente non amministratore e la metrica non è condivisa con esso, il rapporto viene eseguito con la metrica applicata (purché dispongano delle autorizzazioni necessarie per visualizzare gli eventi). Tuttavia, non potranno visualizzare la definizione o modificare la metrica. </p> </td> 
   <td colname="col4"> può utilizzare solo metriche calcolate approvate; impossibile contrassegnare come approvato. </td> 
   <td colname="col5"> Possono applicare le metriche calcolate personalizzate e i segmenti condivisi con loro. </td> 
  </tr> 
 </tbody> 
</table>
