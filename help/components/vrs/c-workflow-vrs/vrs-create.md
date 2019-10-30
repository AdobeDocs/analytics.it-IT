---
description: Prima di iniziare a creare delle suite di rapporti virtuali, tieni presente alcune cose.
keywords: Suite di rapporti virtuali
seo-description: Prima di iniziare a creare delle suite di rapporti virtuali, tieni presente alcune cose.
seo-title: Creare suite di rapporti
solution: Analytics
title: Creare suite di rapporti
topic: Reports and Analytics
uuid: 022a6656-808e-4c92-b7ec-4d2a42e84fa8
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Creare suite di rapporti

Prima di iniziare a creare delle suite di rapporti virtuali, tieni presente alcune cose.

* Gli utenti non amministratori non possono visualizzare Virtual Report Suite Manager.
* Impossibile condividere le suite di rapporti virtuali. "Condivisione" viene eseguita tramite gruppi/autorizzazioni.
*  In Virtual Report Suite Manager (Gestione suite di rapporti virtuali) puoi visualizzare solo le suite di rapporti virtuali. Devi fare clic su "Mostra tutti" per vedere quelli di tutti gli altri.

1. Passa a **[!UICONTROL Components]** &gt; **[!UICONTROL Virtual Report Suites]**.
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
   <td colname="col2"> <p>Aggiungi una buona descrizione a beneficio dei tuoi utenti aziendali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tag </td> 
   <td colname="col2"> <p>Potete aggiungere dei tag per organizzare le suite di rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groups (Gruppi) </td> 
   <td colname="col2"> <p>Selezionate i gruppi di autorizzazioni a cui desiderate accedere per questa VRS. (Potete anche gestire le autorizzazioni del gruppo da <span class="ignoretag"><span class="uicontrol"> Admin</span> (Amministratore) &gt; <span class="uicontrol"> User Management (Gestione</span> utente) &gt; <span class="uicontrol"> Groups (Gruppi</span></span>).) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suite di rapporti principale </td> 
   <td colname="col2"> <p>La suite di rapporti da cui questa suite di rapporti virtuale eredita le seguenti impostazioni. La maggior parte dei livelli e delle funzioni del servizio (ad esempio, impostazioni eVar, Regole di elaborazione, Classificazioni e così via) vengono ereditati. Per apportare modifiche a queste impostazioni ereditate su una VRS, devi modificare la suite di rapporti principale (<span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Suite</span></span>di rapporti). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fuso orario </td> 
   <td colname="col2"> <p>La scelta di un fuso orario è facoltativa. </p> <p>Se scegliete un fuso orario, questo viene salvato insieme alla VRS. Se non si seleziona un fuso orario, verrà utilizzato quello della suite di rapporti padre. </p> <p>Quando si modifica una VRS, il fuso orario salvato con la VRS viene visualizzato nel selettore a discesa. Se la VRS è stata creata prima dell'aggiunta del supporto per il fuso orario, nel selettore a discesa viene visualizzato il fuso orario della suite di rapporti principale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segmenti </td> 
   <td colname="col2"> <p>Puoi aggiungere un solo segmento o <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_stack.html" format="https" scope="external"> impilare segmenti</a>. </p> <p> <p>Nota:  Quando si sovrappongono due segmenti, essi sono uniti da un'istruzione AND. Questo non può essere modificato in un'istruzione OR. </p> </p> <p>Quando si tenta di eliminare o modificare un segmento attualmente utilizzato in una suite di rapporti virtuali, viene visualizzato un avviso. </p> </td> 
  </tr> 
 </tbody> 
</table>

