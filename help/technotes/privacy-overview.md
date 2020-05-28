---
description: Panoramica dei dati raccolti da Adobe Analytics e altre considerazioni sulla privacy.
keywords: privacy
title: Panoramica sulla privacy
uuid: f19a8b35-3e10-47ae-93c1-6a9924b11313
translation-type: ht
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Panoramica sulla privacy

Adobe consiglia di fornire ai visitatori del sito web informazioni facili da trovare e da comprendere sulla possibilità di non acconsentire alla raccolta di informazioni di navigazione da parte dei prodotti o servizi Adobe.

I visitatori possono saperne di più sulle finalità per cui Adobe utilizza le informazioni raccolte nel [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy.html). È compito dell’organizzazione divulgare in che modo utilizza i prodotti e i servizi Adobe, in quanto l’organizzazione controlla esclusivamente l’implementazione dei servizi di Adobe. L’utente è responsabile della creazione della propria informativa sulla privacy, del rispetto di quest’ultima, del rispetto del contratto di servizio con Adobe e del rispetto di tutte le leggi applicabili.

## Breakdown della raccolta dati {#section_F59D958D7AE44747846993E643CD4BF2}

Adobe Analytics raccoglie i dati seguenti:

| Tipo di dati | Questi dati sono raccolti da Adobe Analytics? |
|---|---|
| URL di pagine web nel sito del cliente | Sì |
| Nome della pagina web | Sì |
| Tempo trascorso sulla pagina | Sì |
| Ora del giorno | Sì |
| URL di pagine web su siti non affiliati | **No** |
| ID cookie (generati in modo casuale) | Sì |
| URL della pagina su cui si trovava l’utente prima della visita alla pagina del cliente | Sì |
| Query di ricerca quando il consumatore fa clic sul link alla pagina del cliente | Sì |
| Tipo di browser | Sì |
| Tipo di dispositivo | Sì |
| Sistema operativo | Sì |
| Velocità di connessione/ISP | Sì |
| Impostazioni di visualizzazione (ad esempio dimensioni e risoluzione dello schermo) | Sì |
| Indirizzo IP (utilizzato per approssimare la posizione) | Sì* |
| Informazioni fornite dai consumatori nei moduli sul sito del cliente | Sì |
| Informazioni fornite dai consumatori nei moduli sui siti di social networking | **No** |
| Se il consumatore ha fatto clic sull’annuncio | Sì |
| Se il consumatore ha fatto clic su un link, un’immagine o un testo sul sito | Sì |
| Se il consumatore ha scaricato un file, un’immagine, ecc. | Sì |
| Articoli acquistati dal consumatore | Sì |
| Oggetti rimasti nel carrello | Sì |
| Informazioni tratte dai social network (incluse foto, ID utente, età, genere, posizione) | **No** |
| Informazioni personali fornite dall’utente al di fuori dei nostri servizi | Sì |
| Tassi di successo delle campagne pubblicitarie | Sì |
| Informazioni sul prodotto, ad esempio colori, prezzi, stili, foto | Sì |

*A meno che il cliente Adobe non scelga di rimuovere l’IP.

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
   <td colname="col2"> Adobe consiglia vivamente ai clienti di non trasmettere ad Adobe informazioni personali identificabili (PII), soprattutto in situazioni in cui le PII non sono necessarie per Analytics. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Gli utenti devono essere informati e avere la possibilità di scegliere al momento della profilazione. Ciò è richiesto dalla legge in Canada, Australia, Unione europea (opt-in per alcuni paesi) e in molti paesi dell’America latina e dell’Asia Pacifico. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> In caso si faccia uso di cookie di prime parti, la rinuncia ad Analytics è univoca per il cliente. Non è possibile fare affidamento su una rinuncia su Adobe.com. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Le analisi di prime parti non rientrano nell’ambito del programma di autoregolamentazione per la pubblicità comportamentale online (“AdChoices”). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> I dati tra dispositivi non devono essere uniti a meno che non siano associati a un identificatore fornito dal cliente (ad esempio il nome utente con hash). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> È probabile che il cliente debba sottostare a restrizioni per la combinazione di informazioni ad impression e PII. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Europa </td> 
   <td colname="col2"> La maggior parte dei paesi dell’Unione europea non considera strettamente necessari i cookie di analisi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Europa </td> 
   <td colname="col2"> Adobe ha attivato l’impostazione IP-Obfuscation (oscuramento dell’IP): abilitato - IP rimosso (x.x.x.x) per impostazione predefinita per tutti i clienti con una suite di rapporti nell’area EMEA. Con questa impostazione, l’indirizzo IP verrà completamente sostituito con il valore (x.x.x.x) dopo la geo-lookup e non sarà più disponibile come punto dati. <p>Con questo metodo di sostituzione di base non è possibile risalire a un indirizzo IP univoco specifico. Né il cliente né Adobe possono accedere all’indirizzo IP, che diventa irreversibilmente anonimo. Per maggiori informazioni sulle altre impostazioni di oscuramento dell’IP, consulta </p> <p> <a href="https://docs.adobe.com/content/help/it-IT/analytics/landing/home.html#General_Account_Settings"  >https://docs.adobe.com/content/help/it-IT/analytics/landing/home.html#General_Account_Settings</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Globale </td> 
   <td colname="col2"> Un cliente può impostare la variabile “lifetime” del cookie nel codice di misura JavaScript su un valore “none” (nessuno), “session” (sessione) o su un altro valore specificato, espresso in secondi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Europa </td> 
   <td colname="col2"> Adobe ha sviluppato una nuova impostazione “privacy by design” che ora può essere abilitata dalle versioni 14.9 e 15.4 di Adobe ClientCare per Adobe Analytics (ex SiteCatalyst). Quando questa nuova impostazione è attivata, l’ultimo ottetto (l’ultima parte) dell’indirizzo IP viene immediatamente sostituito con il valore 0 una volta che l’IP viene raccolto da Adobe. Il processo di anonimizzazione viene eseguito prima dell’elaborazione dell’indirizzo IP, anche prima della geo-lookup e dell’ISP-lookup opzionali dell’indirizzo IP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Germania </td> 
   <td colname="col2"> <p>Se i clienti non dispongono già di un accordo di elaborazione dati per Adobe Analytics stipulato con Adobe, devono contattare il proprio Adobe Account Manager o Customer Success Manager, che collaborerà con l’ufficio legale di Adobe per stipulare l’accordo. </p> <p>Adobe ha preparato un accordo sull’elaborazione dei dati (Vertrag fuer Auftragsdatenverarbeitung - ADV) per Analytics che è stato rivisto e approvato dall’Autorità bavarese per la protezione dei dati (Bayerisches Landesamt fuer Datenschutzaufsicht - BayLDA). L’ADV è disponibile in tedesco e in inglese. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Posizioni dei centri dati dell’area EMEA {#section_3DD2329B983849D3B8C24AEF7CD8DFB3}

I seguenti centri dati nell’area EMEA ospitano attualmente i dati di Adobe Analytics:

<table id="table_65794B3790FD4B519EE89CF4F4B88314"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome Adobe </th> 
   <th colname="col2" class="entry"> Indirizzo </th> 
   <th colname="col3" class="entry"> Tipo di impianto (operatore) </th> 
   <th colname="col4" class="entry"> Componenti della soluzione supportati </th> 
   <th colname="col5" class="entry"> Certificazioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AMS1 </td> 
   <td colname="col2"> <p>Luttenbergweg 4 </p> <p>Amsterdam 1101 EC </p> <p>Paesi Bassi </p> </td> 
   <td colname="col3"> <p>Impianto di collocazione </p> <p>(Equinix) </p> </td> 
   <td colname="col4"> <p>Analisi multicanale, </p> <p>analisi digitale </p> </td> 
   <td colname="col5"> <p>ISO9001:2008 </p> <p>ISO14001:2004 </p> <p>OHSAS18001:2007 </p> <p>ISO27001:2005 </p> <p>ISO50001:2011 </p> <p>PCI-DSS </p> <p> <a href="https://www.equinix.it/solutions/by-services/colocation/standards-and-compliance/iso-certified-data-centers/#table"  > Equinix </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LON5 </td> 
   <td colname="col2"> <p>3 Centro </p> <p>Boundary Way </p> <p>Hemel Hempstead HP2 7SU </p> <p>Regno Unito </p> </td> 
   <td colname="col3"> <p>Impianto di collocazione </p> <p>(Gyron) </p> </td> 
   <td colname="col4"> <p>Analisi multicanale, </p> <p>analisi digitale </p> </td> 
   <td colname="col5"> SSAE 16 </td> 
  </tr> 
 </tbody> 
</table>
