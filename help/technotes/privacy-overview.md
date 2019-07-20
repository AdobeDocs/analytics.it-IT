---
description: Panoramica dei dati raccolti da Adobe Analytics e di altre considerazioni sulla privacy.
keywords: privacy
seo-description: Panoramica dei dati raccolti da Adobe Analytics e di altre considerazioni sulla privacy.
seo-title: Panoramica sulla privacy
solution: Analytics
title: Panoramica sulla privacy
uuid: f 19 a 8 b 35-3 e 10-47 ae -93 c 1-6 a 9924 b 11313
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Panoramica sulla privacy

Panoramica dei dati raccolti da Adobe Analytics e di altre considerazioni sulla privacy.

## Data Collection Breakdown {#section_F59D958D7AE44747846993E643CD4BF2}

Adobe Analytics raccoglie i seguenti dati:

| Tipo di dati | Adobe Analytics raccoglie questi dati? |
|---|---|
| URL delle pagine Web all'interno del sito del cliente | Sì |
| Nome della pagina Web | Sì |
| Tempo trascorso sulla pagina | Sì |
| Ora del giorno | Sì |
| URL di pagine Web su siti non associati | **No** |
| ID cookie (generati in modo casuale) | Sì |
| URL della pagina su cui si trovava l'utente prima della visita del cliente | Sì |
| Ricerca query quando il consumatore fa clic sul collegamento alla pagina del cliente | Sì |
| Tipo di browser | Sì |
| Tipo di dispositivo | Sì |
| Versione | Sì |
| ISP/Velocità di connessione | Sì |
| Impostazioni di visualizzazione (ad esempio dimensione schermo e risoluzione) | Sì |
| Indirizzo IP (utilizzato per approssimare la posizione) | Sì* |
| Informazioni sui clienti che forniscono nei moduli sul sito del cliente | Sì |
| Informazioni sui clienti che forniscono moduli sui siti social | **No** |
| Se il consumatore ha fatto clic su di esso | Sì |
| Se il consumatore fa clic sul collegamento, l'immagine o il testo sul sito | Sì |
| Se il consumatore ha scaricato un file, un'immagine, ecc. | Sì |
| Elementi acquistati dal consumatore | Sì |
| Elementi rimanenti nel carrello acquisti | Sì |
| Informazioni sulla rete social (comprese foto, ID utente, età, genere, posizione) | **No** |
| Informazioni personali fornite dall'utente al di fuori dei nostri servizi | Sì |
| Percentuali di successo delle campagne pubblicitarie | Sì |
| Informazioni sul prodotto, quali colori, prezzi, stili, foto | Sì |

* A meno che il cliente Adobe non decida di rimuovere l'IP.

## Other Privacy Considerations {#section_60AF6AD6FBD046EEAF9F083A9726EF8A}

<table id="table_247B425E774F403288233824870D070E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Regione/Paese </th> 
   <th colname="col2" class="entry"> Considerazioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Adobe consiglia vivamente ai clienti di evitare di trasmettere informazioni personali (PII) ad Adobe, soprattutto in situazioni in cui il PII non è necessario per Analytics. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Gli utenti devono essere forniti con avviso e scelta durante il profiling. Questa funzione è necessaria per legge in Canada, Australia, Unione Europea (opt-in per alcuni paesi) e molti Paesi in America Latina e Asia-Pacifico. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Se utilizzate cookie di prime parti, la rinuncia di Analytics è univoca per un cliente; non puoi fare affidamento su un opt-out su Adobe. com. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Le analisi di prime parti non rientrano nell'ambito del programma autonomo per la pubblicità comportamentale online ("adchoices"). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> I dati su più dispositivi non devono essere uniti se non sono associati a un identificatore fornito dal cliente (ad esempio, nome utente con hash). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> È probabile che siano previste restrizioni sulla combinazione di informazioni ad impression su PII. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Europa </td> 
   <td colname="col2"> La maggior parte dei paesi dell'Unione Europea non considera i cookie di analisi strettamente necessari. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Europa </td> 
   <td colname="col2"> Adobe ha attivato l'impostazione dell'IP-Obfuscation: Abilitato - IP rimosso (x. x. x. x) per impostazione predefinita per tutti i clienti con una suite di rapporti impostata nell'area EMEA. Con questa impostazione, l'indirizzo IP verrà sostituito completamente con il valore (x. x. x. x) dopo il geolookup e non sarà più disponibile come punto dati. <p>Questo metodo di sostituzione di base non può essere eseguito indietro a un indirizzo IP univoco specifico. Né il cliente né Adobe possono accedere all'indirizzo IP; viene anonimo. Per ulteriori informazioni sulle altre impostazioni di offuscamento IP, consulta </p> <p> <a href="https://marketing.adobe.com/resources/help/en_US/reference/index.html#General_Account_Settings" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/index.html#General_Account_Settings </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Un cliente può impostare la variabile "lifetime" del cookie nel codice di misurazione javascript su un valore "none", "session" o un altro valore specificato in secondi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Europa </td> 
   <td colname="col2"> Adobe ha sviluppato una nuova impostazione «privacy by design» che ora può essere abilitata dalla versione Adobe clientcare per Adobe Analytics (già sitecatalyst) 14.9 e 15.4. Quando questa nuova impostazione è abilitata, l'ultimo ottetto (l'ultima parte) dell'indirizzo IP viene sostituito immediatamente con il valore 0 dopo che l'indirizzo IP è stato raccolto da Adobe. Questo anonimizzazione viene eseguito prima di qualsiasi elaborazione dell'indirizzo IP, inclusa la ricerca geografica opzionale e la ricerca ISP dell'indirizzo IP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Germania </td> 
   <td colname="col2"> <p>Se i clienti non dispongono già di un contratto di elaborazione dati per Adobe Analytics presso Adobe, devono contattare il proprio Adobe Account Manager o Customer Success Manager, che collaborerà con il Reparto legale Adobe per ottenere il DPA. </p> <p>Adobe ha preparato un Contratto di elaborazione dati (Vertrag fuer Auftragsdatenverarbeitung - ADV) per Analytics che è stato rivisto e approvato dalla Bavarian Data Protection Authority (Bayerisches Landesamt fuer Datenschutzaufsicht - baylda). L'ADV è disponibile in tedesco e inglese. </p> </td> 
  </tr> 
 </tbody> 
</table>

## EMEA Data Center Locations {#section_3DD2329B983849D3B8C24AEF7CD8DFB3}

I seguenti centri dati EMEA ospitano attualmente i dati di Adobe Analytics:

<table id="table_65794B3790FD4B519EE89CF4F4B88314"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adobe Name </th> 
   <th colname="col2" class="entry"> Indirizzo </th> 
   <th colname="col3" class="entry"> Tipo di struttura (operatore) </th> 
   <th colname="col4" class="entry"> Componenti della soluzione supportati </th> 
   <th colname="col5" class="entry"> Certificazioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AMS1 </td> 
   <td colname="col2"> <p>Luttenbergweg 4 </p> <p>Amsterdam 1101 EC </p> <p>I Paesi Bassi </p> </td> 
   <td colname="col3"> <p>Colocation Architecture </p> <p>(Equinix) </p> </td> 
   <td colname="col4"> <p>Analisi multicanale, </p> <p>Digital Analytics </p> </td> 
   <td colname="col5"> <p>ISO 9001:2008 </p> <p>ISO 14001:2004 </p> <p>OHSAS 18001:2007 </p> <p>ISO 27001:2005 </p> <p>ISO 50001:2011 </p> <p>PCI-DSS </p> <p> <a href="https://www.equinix.com/solutions/by-services/colocation/standards-and-compliance/iso-certified-data-centers/#table" format="http" scope="external"> Equinix </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LON5 </td> 
   <td colname="col2"> <p>3 Centro </p> <p>Metodo bordi </p> <p>Hemel Hempstead HP 2 7 SU </p> <p>Regno Unito </p> </td> 
   <td colname="col3"> <p>Colocation Architecture </p> <p>(Gyron) </p> </td> 
   <td colname="col4"> <p>Analisi multicanale, </p> <p>Digital Analytics </p> </td> 
   <td colname="col5"> SSAE 16 </td> 
  </tr> 
 </tbody> 
</table>
