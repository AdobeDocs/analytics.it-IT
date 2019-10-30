---
description: Panoramica dei dati raccolti da Adobe Analytics e di altre considerazioni sulla privacy.
keywords: privacy
seo-description: Panoramica dei dati raccolti da Adobe Analytics e di altre considerazioni sulla privacy.
seo-title: Panoramica sulla privacy
solution: Analytics
title: Panoramica sulla privacy
uuid: f19a8b35-3e10-47ae-93c1-6a9924b11313
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Panoramica sulla privacy

Panoramica dei dati raccolti da Adobe Analytics e di altre considerazioni sulla privacy.

## Suddivisione raccolta dati {#section_F59D958D7AE44747846993E643CD4BF2}

Adobe Analytics raccoglie i dati seguenti:

| Tipo di dati | Adobe Analytics raccoglie questi dati? |
|---|---|
| URL di pagine Web nel sito del cliente | Sì |
| Nome della pagina Web | Sì |
| Tempo trascorso sulla pagina | Sì |
| Ora del giorno | Sì |
| URL di pagine Web su siti non associati | **No** |
| ID cookie (generati in modo casuale) | Sì |
| URL della pagina su cui si trovava l’utente prima della visita alla pagina del cliente | Sì |
| Ricerca quando il consumatore fa clic sul collegamento alla pagina del cliente | Sì |
| Tipo di browser | Sì |
| Tipo di dispositivo | Sì |
| Versione | Sì |
| Velocità di connessione ISP | Sì |
| Impostazioni di visualizzazione (ad esempio, dimensioni e risoluzione dello schermo) | Sì |
| Indirizzo IP (utilizzato per approssimare la posizione) | Sì* |
| Informazioni fornite dai consumatori nei moduli sul sito del cliente | Sì |
| Informazioni fornite dai consumatori nei moduli sui siti sociali | **No** |
| Se il consumatore ha fatto clic sull'annuncio | Sì |
| Se il consumatore ha fatto clic su un collegamento, un’immagine o un testo sul sito | Sì |
| Se il consumatore ha scaricato un file, un’immagine ecc. | Sì |
| Articoli consumer acquistati | Sì |
| Oggetti rimasti nel carrello | Sì |
| Informazioni social network (incluse foto, ID utente, età, genere, luogo) | **No** |
| Informazioni personali fornite dall'utente al di fuori dei nostri servizi | Sì |
| Tassi di successo delle campagne pubblicitarie | Sì |
| Informazioni sul prodotto, ad esempio colori, prezzi, stili, foto | Sì |

*A meno che il cliente Adobe non scelga di rimuovere l'IP.

## Altre considerazioni sulla privacy {#section_60AF6AD6FBD046EEAF9F083A9726EF8A}

<table id="table_247B425E774F403288233824870D070E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Regione/Paese </th> 
   <th colname="col2" class="entry"> Considerazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Adobe consiglia vivamente ai clienti di non trasmettere ad Adobe informazioni personali (PII), soprattutto in situazioni in cui il PII non è necessario per Analytics. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Gli utenti devono essere informati e selezionati al momento del profiling. Ciò è richiesto dalla legge in Canada, Australia, Unione europea (opt-in per alcuni paesi) e in molti paesi dell'America latina e dell'Asia-Pacifico. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Se utilizzate i cookie di prime parti, la rinuncia Analytics è univoca per un cliente; non potete fare affidamento su una rinuncia su Adobe.com. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Le analisi di prime parti non rientrano nell'ambito del programma di autoregolamentazione per la pubblicità comportamentale online ("AdChoices"). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> I dati tra dispositivi non devono essere uniti a meno che non siano associati a un identificatore fornito dal cliente (ad esempio il nome utente con hash). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Ci sono probabilmente restrizioni poste al cliente dalla combinazione di informazioni ad impression a PII. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Europa </td> 
   <td colname="col2"> La maggior parte dei paesi dell'Unione europea non considera strettamente necessari i cookie di analisi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Europa </td> 
   <td colname="col2"> Adobe ha attivato l'impostazione IP-Obfuscation: Abilitato - IP rimosso (x.x.x.x) per impostazione predefinita per tutti i clienti con una suite di rapporti nell'area EMEA. Con questa impostazione, l'indirizzo IP verrà completamente sostituito con il valore (x.x.x.x) dopo la geolookup e non sarà più disponibile come punto dati. <p>Questo metodo di sostituzione di base non può essere decodificato in un indirizzo IP univoco specifico. Né il cliente né Adobe possono accedere all’indirizzo IP; è irreversibilmente anonimo. Per maggiori informazioni sulle altre impostazioni di oscuramento IP, consulta </p> <p> <a href="https://marketing.adobe.com/resources/help/en_US/reference/index.html#General_Account_Settings" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/index.html#General_Account_Settings </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Un cliente può impostare la variabile "lifetime" del cookie nel codice di misura JavaScript su un valore "none", "session" o su un altro valore specificato, espresso in secondi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Europa </td> 
   <td colname="col2"> Adobe ha sviluppato una nuova impostazione "privacy by design" che ora può essere abilitata dalle versioni 14.9 e 15.4 di Adobe ClientCare per Adobe Analytics (ex SiteCatalyst). Quando questa nuova impostazione è attivata, l'ultimo ottetto (l'ultima parte) dell'indirizzo IP viene immediatamente sostituito con il valore 0 una volta che l'indirizzo IP viene raccolto da Adobe. Questa anonimizzazione viene eseguita prima di qualsiasi elaborazione dell'indirizzo IP, anche prima di una geo-ricerca opzionale e di una ricerca ISP dell'indirizzo IP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Germania </td> 
   <td colname="col2"> <p>Se i clienti non dispongono già di un accordo di elaborazione dati per Adobe Analytics, devono contattare il proprio Adobe Account Manager o Customer Success Manager, che collaborerà con l'Ufficio legale Adobe per mettere in atto l'applicazione. </p> <p>Adobe ha preparato un accordo sull'elaborazione dei dati (Vertrag fuer Auftragsdatenverarbeitung - ADV) per Analytics che è stato rivisto e approvato dall'Autorità per la protezione dei dati bavarese (Bayerisches Landesamt fuer Datenschutzaufsicht - BayLDA). L'ADV è disponibile in tedesco e inglese. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Posizioni dei centri dati EMEA {#section_3DD2329B983849D3B8C24AEF7CD8DFB3}

I seguenti centri dati EMEA ospitano attualmente i dati di Adobe Analytics:

<table id="table_65794B3790FD4B519EE89CF4F4B88314"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adobe Name </th> 
   <th colname="col2" class="entry"> Indirizzo </th> 
   <th colname="col3" class="entry"> Tipo di impianto (operatore) </th> 
   <th colname="col4" class="entry"> Componenti della soluzione supportati </th> 
   <th colname="col5" class="entry"> Certificazioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AMS1 </td> 
   <td colname="col2"> <p>Luttenbergweg 4 </p> <p>Amsterdam 1101 CE </p> <p>Paesi Bassi </p> </td> 
   <td colname="col3"> <p>Impianto di collocazione </p> <p>(Equinix) </p> </td> 
   <td colname="col4"> <p>Analisi multicanale, </p> <p>Analisi digitale </p> </td> 
   <td colname="col5"> <p>ISO9001:2008 </p> <p>ISO14001:2004 </p> <p>OHSAS18001:2007 </p> <p>ISO27001:2005 </p> <p>ISO50001:2011 </p> <p>PCI-DSS </p> <p> <a href="https://www.equinix.com/solutions/by-services/colocation/standards-and-compliance/iso-certified-data-centers/#table" format="http" scope="external"> Equinix </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LON5 </td> 
   <td colname="col2"> <p>3 Centro </p> <p>Via limite </p> <p>Hemel Hempstead HP2 7SU </p> <p>Regno Unito </p> </td> 
   <td colname="col3"> <p>Impianto di collocazione </p> <p>(Gyron) </p> </td> 
   <td colname="col4"> <p>Analisi multicanale, </p> <p>Analisi digitale </p> </td> 
   <td colname="col5"> SSAE 16 </td> 
  </tr> 
 </tbody> 
</table>
