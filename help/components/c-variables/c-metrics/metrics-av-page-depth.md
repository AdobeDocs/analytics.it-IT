---
description: Mostra in media quanto tempo all'interno di una visita ogni valore è stato attivato. Questa metrica è preziosa per determinare quanto all'interno di una visita il pubblico raggiunge un determinato valore di pagina o prop. Profondità pagina media è disponibile su qualsiasi variabile con percorsi abilitati.
seo-description: Mostra in media quanto tempo all'interno di una visita ogni valore è stato attivato. Questa metrica è preziosa per determinare quanto all'interno di una visita il pubblico raggiunge un determinato valore di pagina o prop. Profondità pagina media è disponibile su qualsiasi variabile con percorsi abilitati.
seo-title: Profondità pagina media
solution: Analytics
title: Profondità pagina media
topic: Metrics (Metriche)
uuid: 4 d 8 a 3 a 3 c-c 698-4210-8 dd 8-a 02 a 1638483 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Profondità pagina media

Mostra in media quanto tempo all'interno di una visita ogni valore è stato attivato. Questa metrica è preziosa per determinare quanto all'interno di una visita il pubblico raggiunge un determinato valore di pagina o prop. Profondità pagina media è disponibile su qualsiasi variabile con percorsi abilitati.

Ad esempio, se una visita contiene il percorso seguente: Pagina A &gt; Pagina B &gt; Pagina C &gt; Pagina D &gt; Pagina E &gt; Pagina F, profondità è indice della posizione della pagina. Ad esempio, «Page A» ha profondità pari a 0, mentre «Page F.» ha una profondità di cinque. La media è basata su una combinazione di tutte le visite. Una profondità di pagina con un valore minore di uno (ad esempio 0.9) corrisponde al valore medio di tutte le pagine visitate prima della pagina in questione.

[!UICONTROL Page Depth] consente di comprendere in che punto una determinata pagina si trova in genere in un percorso utente, a prescindere dalle pagine precedenti o successive di tale percorso. Di conseguenza, è utile fornire informazioni su come la pagina rientra nel quadro generale dell'esperienza dell'utente sul sito. This insight can be best seen on a [!UICONTROL Pages] report.

<table id="table_E92B185A487C40E28C70EA30EDF73A40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Usi </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Traffic (Traffico) </td> 
   <td colname="col2"> <p>Il calcolo degli eventi di pagina e delle pagine visualizzate diviso per visite, mostrando il numero medio di clic di una pagina. Considerate lo stesso percorso visita: </p> <p>A &gt; B &gt; B &gt; C &gt; D &gt; B </p> <p>Il numero di clic viene calcolato per ogni evento pagina e pagina, incluso ricarica quando l'opzione «Conta istanze ripetute» è attivata (per impostazione predefinita è attivata in Analisi ad hoc, ed è sempre attiva in Reporting e analisi di marketing). In questa visita, la pagina A riceve il numero di clic 0. Per la pagina B, i numeri di clic sono 1, 2 e 5. Il calcolo per la media sarà [(1+2+5)/3] per una profondità di pagina media per la pagina B. </p> <p>Quando l'opzione «Conta istanze ripetute» è disattivata, la pagina B riceve 1 e 4. La seconda non verrà conteggiata. Il calcolo sarà [(1+4)/2 = 2.5]. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversione   </td> 
   <td colname="col2"> N/D </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Report profondità pagina](/help/components/c-variables/dimensionslist/reports-page-depth.md)

