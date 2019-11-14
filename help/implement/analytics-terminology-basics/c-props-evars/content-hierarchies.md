---
description: Un uso comune delle gerarchie di contenuto consiste nel mostrare i diversi percorsi seguiti dai visitatori da una determinata pagina, livello e così via.
keywords: Analytics Implementation;content hierachies;hier
solution: Analytics
title: Conteggio gerarchie di contenuto
topic: Developer and implementation
uuid: d41df92d-65fb-44de-bf46-8fac24303dad
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Conteggio gerarchie di contenuto

Un uso comune delle gerarchie di contenuto consiste nel mostrare i diversi percorsi seguiti dai visitatori da una determinata pagina, livello e così via.

**Come posso tenere traccia della mia[!UICONTROL content hierarchy]identità?**

Devi prima comprendere i requisiti di reporting per il tracciamento [!UICONTROL content hierarchies]. Se i requisiti per il tracciamento della gerarchia sono molto dettagliati, spesso la variabile della gerarchia ( *`hier`*) è consigliata. Le gerarchie in genere richiedono una tassonomia rigida e predefinita in cui lo stesso nodo figlio raramente vive sotto più nodi padre. Prendi in considerazione l'esempio seguente:

[!UICONTROL Global Hierarchy]

Tutti i siti &gt; Regioni &gt; Paesi &gt; Lingua &gt; Categoria

In questo esempio, la gerarchia potrebbe iniziare a essere suddivisa a livello di lingua. Se un requisito è quello di segnalare il traffico "inglese" complessivo, è possibile affrontare il problema in cui l'inglese appare sotto USA, Inghilterra, Australia e così via. Le gerarchie consentono di eseguire solo il drill-down. Per suddividere in orizzontale più gerarchie, è consigliabile utilizzare un [!UICONTROL custom traffic variable] (prop).

Se desiderate fornire agli utenti la possibilità di espandere il sito (in modo simile a come gli utenti potrebbero sfogliare il sito) e creare rapporti su [!UICONTROL Unique Visitors] ogni livello della gerarchia, è consigliabile includere la variabile della gerarchia.

Ci sono occasioni in cui l'uso sia delle proprietà che della *`hier`* variabile ha senso. Di seguito è riportata una proprietà supportata per ogni tipo di variabile:

<table id="table_E960D100DA0F433A94A4B246D6EF0D0A"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> Proprietà </th> 
   <th class="entry"> Gerarchia </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Correlazioni </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2A70A61A78024204B6CEE4FFF9A0851E" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Tracciatura percorso </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_EE5ED36AC75F4D648F54858D796F82BD" /> </p> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Visualizzazioni di pagina </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_5BB82776D41642E78C2ECFD71DD33164" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_18F34EE8957946AF9D6C2C9B492CEDB7" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Visitatori unici </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_A475267547B94DB4A1EEFD903B2CA1EB" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_1E9E302D999146128CDBCE13E52BC38C" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Classifications </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_FC5FEFE7BA8C4475BA4F31D57302BE6B" /> </p> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

