---
description: Visualizza i dati sulla posizione del visitatore. I report di geosegmentazione includono Paesi, Regioni, Città, Stati Uniti e DMA (area di marketing digitale) statunitense. I rapporti di geosegmentazione sono abilitati per tutti i clienti.
seo-description: Visualizza i dati sulla posizione del visitatore. I report di geosegmentazione includono Paesi, Regioni, Città, Stati Uniti e DMA (area di marketing digitale) statunitense. I rapporti di geosegmentazione sono abilitati per tutti i clienti.
seo-title: Geosegmentazione
solution: Analytics
title: Geosegmentazione
topic: Rapporti
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Geosegmentazione

Visualizza i dati sulla posizione del visitatore. I report di geosegmentazione includono Paesi, Regioni, Città, Stati Uniti e DMA (area di marketing digitale) statunitense. I rapporti di geosegmentazione sono abilitati per tutti i clienti.

Tutte le metriche disponibili altrove in Reporting e analisi vengono automaticamente incluse nei report Paesi, Regioni, Città, Stati Uniti e DMA: metriche di conversione e visita, nonché metriche calcolate. Per ulteriori informazioni, consultate questo post di [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) Adobe.

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Report  </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Paesi </td> 
   <td colname="col2"> <p> La più grande divisione geografica. Oltre alle viste classifica e con tendenze standard disponibili nella maggior parte dei rapporti, è disponibile una vista Mappa che codifica i colori dei paesi in base al relativo contributo al traffico totale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aree geografiche </td> 
   <td colname="col2"> <p> Area geografica più piccola di un paese ma più grande di una città. In alcuni paesi, una regione è uno stato, una provincia o una prefettura. In altre aree, è un paese costituente, un dipartimento o una regione metropolitana. A destra di ciascuna regione visualizzata, il paese della regione è indicato anche tra parentesi. </p> <p>Nei dettagli della tabella, fai clic su Run a Cities Report for this Region (la lente di ingrandimento) per eseguire un report che mostra le prestazioni delle città di una regione selezionata rispetto alle altre città della regione. </p> <p>Consulta Regioni <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > di segmentazione geografica e Uso del codice postale per paese</a> per vedere quali paesi utilizzano le aree. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Città </td> 
   <td colname="col2"> <p> La più piccola divisione geografica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stati Uniti </td> 
   <td colname="col2"> <p> Una mappa termica che mostra i visitatori in ogni stato degli Stati Uniti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DMA USA </td> 
   <td colname="col2"> <p> (Area di marketing digitale) Divisioni del mercato dei media per la radio e la televisione negli Stati Uniti. Potete filtrare il rapporto in modo da mostrare solo le aree di marketing all’interno di un particolare stato. Questi dati vengono forniti tramite una partnership tra Adobe e Nielsen Media Research, Inc. </p> <p>Nota:  La voce Non specificata nel rapporto DMA degli Stati Uniti indica i visitatori che non possono essere associati a una DMA specifica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Precisione report </td> 
   <td colname="col2"> <p>Adobe ha collaborato con Digital Envile, uno dei principali fornitori di soluzioni di autenticazione e intelligence IP, per offrire la funzionalità di misurazione geografica basata sugli indirizzi IP degli utenti finali. Sebbene la precisione basata su singoli set di dati possa variare, in genere Digital Envoy offre una precisione superiore al 99% a livello nazionale, oltre il 97% a livello regionale e oltre il 90% a livello di città. </p> <p>Nota: Questi numeri presuppongono che [l'impostazione] (/help/admin/admin/general-acct-settings-admin.md) per rimuovere l'ultimo ottetto dell'indirizzo IP NON sia abilitato. </p> <p>Gli indirizzi IP sono mappati ai codici postali, e ogni città è definita dai codici postali che l'"autorità locale" definisce come parte di quella città. Ad esempio, i sobborghi di Berlino non sono inclusi nella definizione di Berlino, ma ogni città è elencata separatamente, purché gli indirizzi IP possano essere mappati accuratamente su un codice postale in una di queste città. </p> <p>Alcuni fattori che possono influenzare i dati di geosegmentazione includono: </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">Indirizzi IP che rappresentano proxy aziendali. Questi possono apparire come traffico proveniente dalla rete aziendale dell'utente, che in realtà può essere una posizione diversa se l'utente sta lavorando in remoto. </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">Indirizzi IP mobili. Il targeting IP per dispositivi mobili funziona a vari livelli, a seconda della posizione e della rete. Un certo numero di vettori ritorna il traffico IP attraverso POP centralizzati o regionali. </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">Indirizzi IP appartenenti agli utenti di ISP satellitari. Identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano provenire dalla posizione del collegamento. </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">IP militari e governativi. Questo spesso rappresenta il personale che viaggia per il mondo e che accede attraverso la loro sede, piuttosto che la base o l'ufficio dove sono attualmente stazionati. </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">I nostri dati GeoSegmentation/IP vengono forniti da un fornitore di terze parti e vengono aggiornati regolarmente in base alle informazioni fornite dagli ISP e da altre fonti di rete. Le ricerche IP sono intrinsecamente volatili, perché vengono acquistate e vendute frequentemente in tutto il mondo. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

