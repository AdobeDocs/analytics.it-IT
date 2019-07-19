---
description: Visualizza i dati sulla posizione del visitatore. I rapporti di geosegmentazione includono Paesi, Regioni, Città, Stati degli Stati Uniti e DMA (Digital Marketing Area) degli Stati Uniti. I rapporti di geosegmentazione sono abilitati per tutti i clienti.
seo-description: Visualizza i dati sulla posizione del visitatore. I rapporti di geosegmentazione includono Paesi, Regioni, Città, Stati degli Stati Uniti e DMA (Digital Marketing Area) degli Stati Uniti. I rapporti di geosegmentazione sono abilitati per tutti i clienti.
seo-title: Geosegmentazione
solution: Analytics
title: Geosegmentazione
topic: Rapporti
uuid: 66 aa 22 c 4-dcbc -491 a-b 23 c -0 c 3 d 87444 d 23
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Geosegmentazione

Visualizza i dati sulla posizione del visitatore. I rapporti di geosegmentazione includono Paesi, Regioni, Città, Stati degli Stati Uniti e DMA (Digital Marketing Area) degli Stati Uniti. I rapporti di geosegmentazione sono abilitati per tutti i clienti.

Tutte le metriche disponibili altrove in Reporting e analisi vengono incluse automaticamente nei paesi, regioni, città, stati degli Stati Uniti e rapporti DMA: metriche di conversione e visita, nonché metriche calcolate. For more information, see this Adobe [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) post.

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
   <td colname="col2"> <p> La più grande divisione geografica. Oltre alle visualizzazioni standard Ranked e Trended disponibili nella maggior parte dei rapporti, esiste anche una visualizzazione Mappa che codifica i paesi in base al contributo relativo al traffico totale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aree geografiche </td> 
   <td colname="col2"> <p> Area geografica più piccola di un paese, ma più grande di una città. In alcuni paesi, un'area è uno stato, una provincia o una prefettura. In altre aree, si tratta di un paese, un dipartimento o un'area metropolitana. A destra di ogni regione visualizzata, il paese dell'area viene visualizzato anche tra parentesi. </p> <p>Nel dettaglio della tabella, fate clic su Esegui un rapporto città per regione (la lente di ingrandimento) per eseguire un rapporto che mostra come le città nell'area selezionata vengono eseguite rispetto ad altre città della regione. </p> <p>See <a href="../../../components/c-variables/dimensionslist/reports-geosegmentation-reference.md#concept_F7D998B418544B39ACD8838B48B732F1" format="dita" scope="local"> GeoSegmentation Regions and Postal Code usage by Country</a> to see which countries use regions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Città </td> 
   <td colname="col2"> <p> La divisione geografica più piccola. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stati Stati Uniti </td> 
   <td colname="col2"> <p> Mappa di calore che mostra i visitatori a ogni stato degli Stati Uniti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DMA USA </td> 
   <td colname="col2"> <p> (Area di marketing digitale) Divisioni di mercato multimediali per radio e televisori negli Stati Uniti. Puoi filtrare il rapporto per mostrare solo le aree di marketing all'interno di uno stato specifico. Questi dati vengono forniti tramite una partnership tra Adobe e Nielsen Media Research, Inc. </p> <p>Nota: La voce Non specificata nel rapporto USA. S. DMA indica i visitatori che non sono stati associati a una specifica DMA. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Precisione rapporto </td> 
   <td colname="col2"> <p>Adobe ha avviato una partnership con Digital Dispaty, uno dei principali fornitori di soluzioni di gestione di IP e di autenticazione, per offrire geosegmentazione, una funzionalità di misurazione geografica basata sugli indirizzi IP degli utenti finali. Anche se la precisione basata sui singoli set di dati può variare, in genere l'emittente digitale offre più del 99% di precisione a livello di paese, oltre il 97% a livello di precisione a livello di regione e oltre il 90% a livello di città. </p> <p>Nota: Tali numeri presuppongono che [l'impostazione] (/help/admin/admin/general-acct-settings-admin. md) rimuova l'ultimo ottetto dell'indirizzo IP. </p> <p>Gli indirizzi IP sono mappati a codici postali e ogni città è definita dai codici postali definiti dall '«autorità locale» come parte della città. Ad esempio, i sottoinsiemi di Berlino non sono inclusi nella definizione di Berlino, ma ogni città/città viene elencata separatamente, presupponendo che gli indirizzi IP possano essere mappati con precisione a un codice postale in una di queste città. </p> <p>Alcuni fattori che possono influenzare i dati di geosegmentazione includono: </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">Indirizzi IP che rappresentano i proxy aziendali. Possono essere visualizzate come traffico attraverso la rete aziendale dell'utente, che in realtà potrebbe essere un percorso diverso se l'utente funziona in remoto. </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">Indirizzi IP mobili. Il targeting IP mobile funziona a livelli diversi a seconda del percorso e della rete. Molti gestori passano il traffico IP attraverso pops centralizzati o regionali. </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">Indirizzi IP appartenenti agli utenti di ISP satellite. Identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano provenire dalla posizione dell'applicazione. </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">IP militare e governativo. Ciò spesso rappresenta il personale che viaggia in tutto il mondo e accede attraverso la posizione iniziale, anziché la base o l'ufficio in cui sono attualmente posizionati. </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">I nostri dati di geosegmentazione/IP vengono forniti da un fornitore 3 rd-party e vengono aggiornati regolarmente in base alle informazioni fornite da isps e da altre sorgenti di rete. Le ricerche IP sono intrinsecamente volatili, perché vengono acquistate e vendute frequentemente in tutto il mondo. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

