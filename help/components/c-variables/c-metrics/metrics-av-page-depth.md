---
description: Visualizza in media la distanza all’interno di una visita in cui è stato attivato ogni valore. Questa metrica è utile per determinare fino a che punto all’interno di una visita il pubblico raggiunge una determinata pagina o un determinato valore di proprietà. Profondità pagina media è disponibile su qualsiasi variabile con percorso abilitato.
seo-description: Visualizza in media la distanza all’interno di una visita in cui è stato attivato ogni valore. Questa metrica è utile per determinare fino a che punto all’interno di una visita il pubblico raggiunge una determinata pagina o un determinato valore di proprietà. Profondità pagina media è disponibile su qualsiasi variabile con percorso abilitato.
seo-title: Profondità media della pagina
solution: Analytics
title: Profondità media della pagina
topic: Metriche
uuid: 4d8a3a3c-c698-4210-8dd8-a02a1638483c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Profondità media della pagina

Visualizza in media la distanza all’interno di una visita in cui è stato attivato ogni valore. Questa metrica è utile per determinare fino a che punto all’interno di una visita il pubblico raggiunge una determinata pagina o un determinato valore di proprietà. Profondità pagina media è disponibile su qualsiasi variabile con percorso abilitato.

Ad esempio, se una visita contiene il percorso seguente: Pagina A &gt; Pagina B &gt; Pagina C &gt; Pagina D &gt; Pagina E &gt; Pagina F, la profondità è un indice della posizione della pagina. Ad esempio, "Pagina A" ha una profondità pari a 0, mentre "Pagina F". ha una profondità di cinque. La media si basa su una combinazione di tutte le visite. Una profondità di pagina con un valore inferiore a uno (ad esempio 0,9) è il valore medio di tutte le pagine visitate prima della pagina in questione.

[!UICONTROL Page Depth] aiuta a capire dove una determinata pagina si trova solitamente in un percorso utente, indipendentemente dalle pagine precedenti o successive in questo percorso. In questo modo, è possibile esaminare in che modo la pagina si adatta all'immagine generale dell'esperienza dell'utente sul sito. Questo concetto può essere visualizzato al meglio in un [!UICONTROL Pages] rapporto.

<table id="table_E92B185A487C40E28C70EA30EDF73A40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Usi </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Traffico </td> 
   <td colname="col2"> <p>Calcolo degli eventi di pagina e delle pagine visualizzate divise per visite, con il numero medio di clic di una pagina. Considera lo stesso percorso della visita: </p> <p>A &gt; B &gt; B &gt; C &gt; D &gt; B </p> <p>Il numero di clic è calcolato per ogni evento di pagina e pagina, compresi i ricarichi quando l'opzione "Conta istanze ripetute" è abilitata (questa opzione è attivata per impostazione predefinita nell'analisi ad hoc ed è sempre attiva in Reporting e analisi di marketing). In questa visita, la pagina A riceve il numero di clic 0. Per la pagina B, i numeri di clic sono 1, 2 e 5. Il calcolo per la media sarebbe [(1+2+5) / 3] per una profondità media di pagina di 2,67 per la pagina B. </p> <p>Quando l'opzione "Conta istanze ripetute" è disattivata, la pagina B riceve 1 e 4. Il secondo non verrà conteggiato. Il calcolo sarebbe [(1+4) / 2 = 2,5]. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversione </td> 
   <td colname="col2"> N/D </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Rapporto Profondità pagina](/help/components/c-variables/dimensionslist/reports-page-depth.md)

