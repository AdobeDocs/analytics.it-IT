---
description: Prima di iniziare a creare suite di rapporti virtuali, devi tenere presenti alcuni aspetti.
keywords: Suite di rapporti virtuali
title: Creare suite di rapporti
feature: Reports & Analytics Basics & Analytics Basics
uuid: 022a6656-808e-4c92-b7ec-4d2a42e84fa8
exl-id: 5ff6ff1a-5b99-41cc-a3a7-928197ec9ef9
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 14%

---

# Creare suite di rapporti

Prima di iniziare a creare suite di rapporti virtuali, devi tenere presenti alcuni aspetti.

* Gli utenti non amministratori non possono visualizzare Virtual Report Suite Manager.
* Impossibile condividere le suite di rapporti virtuali. La &quot;condivisione&quot; viene eseguita tramite gruppi/autorizzazioni.
* In Gestione suite di rapporti virtuale è possibile visualizzare solo le suite di rapporti virtuali. Devi cliccare su &quot;mostra tutto&quot; per vedere quello di tutti gli altri.

1. Passa a **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]**.
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
   <td colname="col2"> <p>Aggiungi una buona descrizione a beneficio degli utenti aziendali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tag </td> 
   <td colname="col2"> <p>Puoi aggiungere dei tag per organizzare le suite di rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groups (Gruppi) </td> 
   <td colname="col2"> <p>Seleziona i gruppi di autorizzazioni a cui desideri accedere per questa VRS. (Puoi anche gestire le autorizzazioni del gruppo da <span class="ignoretag"><span class="uicontrol"> Amministratore</span> &gt; <span class="uicontrol"> Gestione utente</span> &gt; <span class="uicontrol"> Gruppi</span></span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Suite di rapporti principale </td> 
   <td colname="col2"> <p>La suite di rapporti da cui questa suite di rapporti virtuale eredita le seguenti impostazioni. La maggior parte dei livelli e delle funzioni del servizio (ad esempio, impostazioni eVar, Regole di elaborazione, Classificazioni e così via) vengono ereditati. Per apportare modifiche a queste impostazioni ereditate in una VRS, devi modificare la suite di rapporti principale (<span class="ignoretag"><span class="uicontrol"> Amministratore</span> &gt; <span class="uicontrol"> Suite di rapporti</span></span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fuso orario </td> 
   <td colname="col2"> <p>La scelta di un fuso orario è facoltativa. </p> <p>Se scegli un fuso orario, questo viene salvato insieme alla VRS. Se non si seleziona un fuso orario, verrà utilizzato quello della suite di rapporti padre. </p> <p>Durante la modifica di una VRS, il fuso orario salvato con la VRS viene visualizzato nel selettore a discesa. Se la VRS è stata creata prima dell’aggiunta del supporto per il fuso orario, il fuso orario della suite di rapporti principale viene visualizzato nel selettore a discesa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segmenti </td> 
   <td colname="col2"> <p>Puoi aggiungere un solo segmento oppure <a href="https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/segmentation-workflow/seg-build.html"  > impilare segmenti</a>. </p> <p> <p>Nota:  Quando si sovrappongono due segmenti, essi sono collegati da un’istruzione AND. Non è possibile modificare questo valore in un'istruzione OR. </p> </p> <p>Quando tenti di eliminare o modificare un segmento attualmente utilizzato in una suite di rapporti virtuale, viene visualizzato un avviso. </p> </td> 
  </tr> 
 </tbody> 
</table>
