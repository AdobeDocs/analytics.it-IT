---
description: Panoramica dei dati raccolti da Adobe Analytics e altre considerazioni sulla privacy.
keywords: privacy
title: Panoramica sulla privacy
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 77e50dec593722855f30c517f63141e84f665519
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 96%

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
| Indirizzo IP (utilizzato per approssimare la posizione) | Sì&#42; |
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

&#42;A meno che il cliente Adobe non scelga di rimuovere l’IP.

## Altre considerazioni sulla privacy {#section_60AF6AD6FBD046EEAF9F083A9726EF8A}

| Regione/Paese | Considerazione |
|--- |--- |
| Globale | Adobe consiglia vivamente ai clienti di non trasmettere ad Adobe informazioni personali identificabili (PII), soprattutto in situazioni in cui le PII non sono necessarie per Analytics. |
| Globale | Gli utenti devono essere informati e avere la possibilità di scegliere al momento della profilazione. Ciò è richiesto dalla legge in Canada, Australia, Unione europea (opt-in per alcuni paesi) e in molti paesi dell’America latina e dell’Asia Pacifico. |
| Globale | In caso si faccia uso di cookie di prime parti, la rinuncia ad Analytics è univoca per il cliente. Non è possibile fare affidamento su una rinuncia su Adobe.com. |
| Globale | Le analisi di prime parti non rientrano nell’ambito del programma di autoregolamentazione per la pubblicità comportamentale online (“AdChoices”). |
| Globale | I dati tra dispositivi non devono essere uniti a meno che non siano associati a un identificatore fornito dal cliente (ad esempio il nome utente con hash). |
| Globale | È probabile che il cliente debba sottostare a restrizioni per la combinazione di informazioni ad impression e PII. |
| Europa | La maggior parte dei paesi dell’Unione europea non considera strettamente necessari i cookie di analisi. |
| Europa | Adobe ha attivato l’impostazione IP-Obfuscation (oscuramento dell’IP): abilitato - IP rimosso (x.x.x.x) per impostazione predefinita per tutti i clienti con una suite di rapporti nell’area EMEA. Con questa impostazione, l’indirizzo IP verrà completamente sostituito con il valore (x.x.x.x) dopo la geo-lookup e non sarà più disponibile come punto dati. Con questo metodo di sostituzione di base non è possibile risalire a un indirizzo IP univoco specifico. Né il cliente né Adobe possono accedere all’indirizzo IP, che diventa irreversibilmente anonimo. Per maggiori informazioni sulle altre impostazioni di offuscamento dell’IP, consulta le [Impostazioni account generali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) nella guida utente di Amministrazione. |
| Globale | Un cliente può impostare la variabile “lifetime” del cookie nel codice di misura JavaScript su un valore “none” (nessuno), “session” (sessione) o su un altro valore specificato, espresso in secondi. |
| Europa | Adobe ha sviluppato una nuova impostazione “privacy by design” che ora può essere abilitata dalle versioni 14.9 e 15.4 di Adobe ClientCare per Adobe Analytics (ex SiteCatalyst). Quando questa nuova impostazione è attivata, l’ultimo ottetto (l’ultima parte) dell’indirizzo IP viene immediatamente sostituito con il valore 0 una volta che l’IP viene raccolto da Adobe. Il processo di anonimizzazione viene eseguito prima dell’elaborazione dell’indirizzo IP, anche prima della geo-lookup e dell’ISP-lookup opzionali dell’indirizzo IP. |
| Germania | Se non disponi già di un accordo di elaborazione dati per Adobe Analytics stipulato con Adobe, devi contattare il tuo Adobe Account Manager o Customer Success Manager, che collaborerà con l’ufficio legale di Adobe per stipulare l’accordo. |

## Posizione del centro dati EMEA {#section_3DD2329B983849D3B8C24AEF7CD8DFB3}

Il seguente centro dati EMEA ospita attualmente i dati di Adobe Analytics:

| Nome Adobe | Indirizzo | Tipo di impianto (operatore) | Componenti della soluzione supportati | Certificazioni |
|--- |--- |--- |--- |--- |
| LON5 | 3 Centro  Hemel Hempstead per la via limite HP2 7SU UK | Struttura di localizzazione (Gyron) | Analisi multicanale, analisi digitale | SSAE 16 |