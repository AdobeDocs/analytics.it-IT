---
description: L’IQ segmento (Confronto segmento) è una delle funzionalità più utilizzate in Analysis Workspace e i clienti trovano costantemente modi nuovi e innovativi di metterla in pratica efficacemente. Ti presentiamo solo alcuni di questi casi d’uso estremamente utili.
keywords: IQ segmento
seo-description: L’IQ segmento (Confronto segmento) è una delle funzionalità più utilizzate in Analysis Workspace e i clienti trovano costantemente modi nuovi e innovativi di metterla in pratica efficacemente. Ti presentiamo solo alcuni di questi casi d’uso estremamente utili.
seo-title: Casi d'uso IQ segmento
title: Casi d'uso IQ segmento
uuid: 2 a 98 b 96 b -5529-4 c 7 f-a 787-27920603 d 5 b 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Casi d'uso IQ segmento

L’IQ segmento (Confronto segmento) è una delle funzionalità più utilizzate in Analysis Workspace e i clienti trovano costantemente modi nuovi e innovativi di metterla in pratica efficacemente. Ti presentiamo solo alcuni di questi casi d’uso estremamente utili.

## Use case 1: compare mobile vs desktop implementations {#section_B3A5983E58D0470895C030EA527C4966}

**“Abbiamo confrontato le hit da un sito all’altro e abbiamo rapidamente riscontrato diverse incongruenze a livello di assegnazione tag. In questo modo abbiamo evitato problemi ai dati prima del rilascio del prodotto”.**

**Scenario**: un responsabile prodotto, a cui è affidata la gestione di un sito Web per dispositivi mobili e desktop, ha ricevuto l’incarico di accertarsi che i tag fossero coerenti per entrambi i siti. Per accertarsi di non aver tralasciato nulla di importante ha utilizzato IQ segmento per confrontare le hit derivanti dal sito per dispositivi mobili con le hit derivanti dal sito desktop. Ha notato di essersi dimenticato di assegnare un tag all’evento di uscita sul sito mobile ed è stato in grado di posizionare correttamente i tag corretti, prima della pubblicazione del sito. In questo modo, il responsabile prodotto ha evitato un data disaster causato dalla mancata registrazione delle conversioni da parte del sito Web mobile.

**Come impostare questo confronto:**

<table id="table_B5FA23CB34DE4331A8BD65ED4B351038"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segmento 1 </th> 
   <th colname="col3" class="entry"> Segmento 2 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utilizza/Crea un segmento di livello hit </p> <p> </p> <p> 
     <ul id="ul_1F5D5136620E449D93A771CD2576A18A"> 
      <li id="li_CB32DD1033DA4E5CA3B9AD41030800E6">Tipo dispositivo mobile equivale a Telefono cellulare o Tablet </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Utilizza/Crea un segmento di livello hit </p> <p> </p> <p> 
     <ul id="ul_79CC51C4C9494275B3F37B6D2AB0505E"> 
      <li id="li_83BE21AD1FB34195BAFF3F15421DBB3D">Tipo dispositivo mobile non equivale a Telefono cellulare o Tablet </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Use case 2: compare customers who use a certain feature to those who don't {#section_878B08FDD70A45E186C1F28EBA296636}

**“Abbiamo scoperto che i clienti che utilizzavano la funzionalità di confronto del nostro prodotto avevano il 10% di possibilità di decidere per l’acquisto. L’abbiamo spostata nella parte superiore della pagina, e gli ordini sono cresciuti del 4%!”**

**Scenario:** il team dedicato all’ottimizzazione di sito di commercio al dettaglio desiderava capire meglio gli utenti che interagivano con una funzionalità di confronto dei prodotti che avevano recentemente pubblicato. Creando un segmento di visitatori che aveva interagito con la funzionalità, sono stati in grado di utilizzare IQ segmento per confrontare questi utenti a tutti gli altri frequentatori del sito. IQ segmento ha identificato rapidamente diverse e importanti differenze, tra le quali il fatto che tali utenti avevano il 10% di possibilità in più di effettuare l’acquisto di un prodotto. Il team di ottimizzazione sito ha deciso di testare la funzionalità di confronto del prodotto collocandola in maniera più evidente nella parte superiore della pagina.

**Come impostare questo confronto:**

| Segmento 1 | Segmento 2 |
|--- |--- |
| Utilizza/Crea un segmento a livello di visitatore per i visitatori che hanno interagito con lo strumento di confronto del prezzo. | Utilizza il segmento Tutti gli altri che viene generato automaticamente e ignora tutti quelli non inclusi nel Segmento 1. |

## Use case 3: compare news site visitors to other site section visitors {#section_0EAFC90C450244058B161200AC9901B8}

**“Abbiamo scoperto che i visitatori della nostra sezione news avevano una probabilità di due volte superiore di guardare video pubblicitari, per questo abbiamo aggiunto più opzioni video a quella sezione. I video pubblicitari visualizzati sono aumentati del 7%!”**

**Scenario:** un’importante casa editrice stava cercando un modo per migliorare l’interesse verso i contenuti da parte del pubblico nella propria sezione news. Per capire meglio il pubblico della sezione news, hanno creato un segmento di visitatori che hanno visitato quella sezione. IQ segmento ha analizzato tutte le metriche e le dimensioni e ha individuato immediatamente che tali utenti avevano una probabilità di due volte superiore di guardare video pubblicitari rispetto ai visitatori di qualsiasi altra sezione del sito. Il team video ha realizzato una sezione video consigliati sulla barra di scorrimento laterale delle news e sono stati in grado di ottenere un aumento del 7% dei video pubblicitari guardati. Considerando tutti gli aspetti a cui avrebbero potuto dedicare tempo e sforzi, si trattava di un’opportunità davvero facile da cogliere e in grado di produrre risultati veloci e misurabili.

**Come impostare questo tipo di confronto:**

| Segmento 1 | Segmento 2 |
|--- |--- |
| Utilizza/crea un segmento a livello di visitatore per i visitatori della sezione news del sito. | Utilizza il segmento Tutti gli altri che viene generato automaticamente e ignora tutti quelli non inclusi nel Segmento 1. |

## Use case 4: compare visitors from paid search to everyone else {#section_73912670409349CAB131FE9D8B4FB11C}

**“I visitatori che accedevano al nostro sito tramite motori di ricerca erano tre volte più propensi all’up-sell rispetto a qualsiasi altro utente. Abbiamo aumentato l’investimento nelle parole chiave specifiche e come risultato abbiamo raggiunto un aumento del 56% negli up-sell”.**

**Scenario:** una grande azienda di servizi B2B desiderava capire il tipo di traffico che le parole chiave paid search portavano al loro sito. La paid search non aveva prodotto direttamente molte conversioni e i responsabili del marketing stavano pensando di diminuire il budget a questa dedicato. Il team marketing ha creato un segmento di visitatori che accedevano al sito tramite paid search e lo ha confrontato a tutti gli altri visitatori che utilizzavano IQ segmento. Hanno scoperto che, anche se questi visitatori non avevano la stessa probabilità di una conversione diretta, erano comunque 3 volte più propensi all’up-sell per un servizio precedentemente acquistato. Il team marketing è stato quindi in grado di concentrare il proprio budget sulle parole chiave correlate all’up-sell, registrando un aumento del 56% degli up-sell.

**Come impostare questo confronto:**

| Segmento 1 | Segmento 2 |
|--- |--- |
| Utilizza/crea un segmento a livello di visitatore per i visitatori derivanti dalle ricerche naturali o per quelli derivati da una campagna SEM. | Utilizza il segmento Tutti gli altri che viene generato automaticamente e ignora tutti quelli non inclusi nel Segmento 1. |

## Use case 5: compare Fitbit purchasers to everyone else {#section_9142B8A270764545B0A516AA309F1785}

**“Abbiamo scoperto che le persone che acquistano Fitbit avevano una probabilità 6 volte maggiore di ricevere il messaggio “non disponibile” rispetto agli altri, per questo abbiamo deciso di aumentare gli ordini di Fitbit evitando di esaurire i pezzi disponibili!”**

**Scenario:** Un grande rivenditore online era interessato alle vendite di Fitbit, uno dei prodotti più ricercati delle feste, e agli aspetti che rendevano unici i suoi acquirenti rispetto agli altri. Con un semplice clic con il pulsante destro del mouse sull’elemento di riga “Fitbit” nei rapporti sui prodotti, il team marketing ha potuto eseguire rapidamente un’analisi IQ segmento. Ciò che hanno scoperto è che gli acquirenti Fitbit avevano una probabilità di 6 volte superiore di ricevere il messaggio “esaurito” rispetto a qualsiasi altro cliente. Dopo ulteriori analisi, il team marketing è stato in grado di dirigere i visitatori ai negozi fisici mentre attendevano che il reparto acquisti ordinasse ulteriori Fitbit da spedire. Come risultato, il rivenditore ha evitato ulteriori messaggi di “esaurimento” ed è stato in grado di soddisfare la maggiore domanda del periodo festivo.

**Come impostare questo confronto:**

<table id="table_9018BEB4C2DE429FA773B250CB5C3E58"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segmento 1 </th> 
   <th colname="col3" class="entry"> Segmento 2 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utilizza/Crea un segmento di livello visitatore, </p> <p> 
     <ul id="ul_52E8ED6F4F7241D5ABE4EE7EA1E556D8"> 
      <li id="li_33750601AB2A43728834B29AF86D5CCF">Ordini ha un valore superiore o uguale a 1, AND </li> 
      <li id="li_4E09D1286DAE4BABA49E4834E73BDC28">Marchio uguale a Fitbit </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Utilizza il segmento <span class="wintitle">Tutti gli altri</span> che viene generato automaticamente e ignora tutti quelli non inclusi nel Segmento 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

