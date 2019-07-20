---
description: Un uso comune delle gerarchie di contenuto consiste nel mostrare i percorsi diversi seguiti dai visitatori di una determinata pagina, livello e così via.
keywords: Implementazione di Analytics; geromi di contenuto; hier
seo-description: Un uso comune delle gerarchie di contenuto consiste nel mostrare i percorsi diversi seguiti dai visitatori di una determinata pagina, livello e così via.
seo-title: Conteggio gerarchie di contenuto
solution: Analytics
title: Conteggio gerarchie di contenuto
topic: Sviluppatore e implementazione
uuid: d 41 df 92 d -65 fb -44 de-bf 46-8 fac 24303 papà
translation-type: tm+mt
source-git-commit: 1bc1c7a1e00d7b59cd39f368ac9afb745bea9e47

---


# Conteggio gerarchie di contenuto

Un uso comune delle gerarchie di contenuto consiste nel mostrare i percorsi diversi seguiti dai visitatori di una determinata pagina, livello e così via.

**Come posso tenere traccia?[!UICONTROL content hierarchy]**

You must first understand the reporting requirements for tracking [!UICONTROL content hierarchies]. If the requirements for tracking the hierarchy are very detailed, often times the hierarchy ( *`hier`*) variable is recommended. Le gerarchie in genere richiedono una tassonomia rigida e predefinita, in cui lo stesso nodo secondario raramente vive sotto più nodi padre. Prendi in considerazione l'esempio seguente:

[!UICONTROL Global Hierarchy]

Tutti i siti &gt; Regioni &gt; Paesi &gt; Lingua &gt; Categoria

In questo esempio, la gerarchia potrebbe iniziare a suddividersi al livello del linguaggio. Se un requisito è quello di segnalare il traffico generale dell'inglese, potete eseguire il problema in cui l'inglese viene visualizzato in USA, Inghilterra, Australia e così via. Le gerarchie consentono di approfondire la ricerca. In order to slice horizontally across multiple hierarchies, the best practice is to use a [!UICONTROL custom traffic variable] (prop).

If you want to provide users with the ability to drill down through the site (similar to how users would browse the site) and report on [!UICONTROL Unique Visitors] at each level of the hierarchy, the hierarchy variable is recommended.

There are occasions when using both props and the *`hier`* variable makes sense. Di seguito è riportato un prop supportato per ogni tipo di variabile:

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
   <td> Percorsi </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_EE5ED36AC75F4D648F54858D796F82BD" /> </p> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Visualizzazioni di pagina </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_5BB82776D41642E78C2ECFD71DD33164" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_18F34EE8957946AF9D6C2C9B492CEDB7" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Visitatori univoci </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_A475267547B94DB4A1EEFD903B2CA1EB" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_1E9E302D999146128CDBCE13E52BC38C" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Classificazioni </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_FC5FEFE7BA8C4475BA4F31D57302BE6B" /> </p> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

