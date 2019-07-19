---
description: Le suite di rapporti rollup aggregano dati da suite di rapporti secondarie e li mostrano in un set di dati riepilogativo.
seo-description: Le suite di rapporti rollup aggregano dati da suite di rapporti secondarie e li mostrano in un set di dati riepilogativo.
seo-title: Suite di rapporti rollup e globali
solution: Analytics
title: Suite di rapporti rollup e globali
topic: Strumenti di amministrazione
uuid: c 90 b 8 e 38-2 c 95-4318-8165-a 362106 b 6142
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Suite di rapporti rollup e globali

Le suite di rapporti rollup aggregano dati da suite di rapporti secondarie e li mostrano in un set di dati riepilogativo.

Per non sbagliare con le suite di rapporti globali, i rollup offrono una comoda posizione per visualizzare totali sommati come visualizzazioni pagina, entrate o metriche tecnologiche. I rollup vengono utilizzati spesso perché non richiedono implementazione aggiuntiva.

## Definitions of Report Suite Types {#section_E51E03E3917040278600A7E9638A91C7}

**Suite di rapporti globale**: L'implementazione viene modificata per inviare richieste di immagini tra domini diversi in una singola suite di rapporti globale, oltre a singole suite di rapporti.

**Suite di rapporti Rollup**: Creato in Strumenti di amministrazione. Considera la somma di ogni metrica alla fine di ogni giorno.

* Gli rollup sono gratuiti e non incrementano le chiamate server.
* I rollup forniscono dati totali, ma non segnalano i singoli valori nei report. Ad esempio, i valori evar 1 non sono inclusi, ma il relativo totale complessivo può essere.
* I dati non vengono duplicati quando si combinano dati nelle suite di rapporti. Un singolo utente può toccare tre suite di rapporti diverse in un unico giorno e apparirà come tre visitatori unici giornalieri nel rollup.
* L'aggregazione rollup avviene in modo notturno.
* Quando si aggiunge una suite di rapporti a un rollup esistente, non viene incluso nel rollup.
* Le suite di rapporti di rollup dispongono di funzionalità di reporting limitate. Ad esempio, i conteggi unici dei visitatori vengono aggiunti nelle suite di rapporti. Se la stessa persona accede a due suite di rapporti separate, un rollup riporta la persona come due visitatori, mentre una suite di rapporti globale indica un visitatore.
* Affinché un rollup funzioni, tutte le suite di rapporti secondarie devono disporre di dati. Se le nuove suite di rapporti sono incluse in un rollup, assicurati di inviare almeno una visualizzazione di pagina a tali suite di rapporti.
* Le suite di rapporti di rollup sono limitate a un massimo di 40 suite di rapporti secondari.
* Le suite di rapporti di rollup sono limitate a un massimo di 100 eventi.
* I dati contenuti nelle suite di rapporti di Rollup non supportano le sottorelazioni, i segmenti o qualsiasi metrica introdotta nei rapporti di marketing.
* Il rapporto Pagine non è disponibile nelle suite di rapporti di rollup. Viene sostituito dal report Most Popular Sites (Siti più popolari), che segnala le metriche a livello di suite figlia.

## Rollup vs. Global Report Suites {#section_7B3703DC7ABF4B9EA9DF02A54592CAD0}

**Chiamate server**: Le suite di rapporti globali incrementano le chiamate al server secondarie, mentre rollup non effettuano chiamate server.

**Modifiche implementazione**: Rollups non richiede alcuna modifica di implementazione, mentre le suite di rapporti globali richiedono che un ulteriore ID suite di rapporti venga inserito nel file s_ code. js.

**Duplicazione**: Le suite di rapporti globali deduplicano i visitatori univoci, mentre rollup non lo sono. Ad esempio, se un utente visita tre dei domini nello stesso giorno, rollup conta tre visitatori giornalieri univoci. Suite di rapporti globali registrare un visitatore univoco.

**Intervallo di tempo**: I rollup vengono elaborati solo a mezzanotte ogni giorno, mentre le suite di rapporti globali dei rapporti presentano dati con latenza standard.

**Breadth**: Suite di rapporti globali possono attribuire il credito alle variabili di conversione tra suite di rapporti, nonché fornire percorsi nelle suite di rapporti. Rollups non è in grado di comunicare tra suite di rapporti.

**Dati cronologici**: I rollup possono aggregare dati storici, mentre le suite di rapporti globali segnalano solo i dati dal punto in cui sono stati implementati.

**Rapporti**: Le suite di rapporti globali forniscono informazioni aggiuntive sui report ALL implementati; rollup fornisce dati aggregati su solo rapporti di alto livello.

**Prodotti supportati**: Rollup non sono supportati in data warehouse o analisi ad hoc. I rapporti di marketing sono limitati a 40 suite di rapporti secondarie. Le suite di rapporti globali possono essere utilizzate in tutti i prodotti e possono avere un numero illimitato di suite di rapporti secondarie.

## Which Report Suite Type Do I Want to Implement? {#section_868066B9604B49BABBF84074BA5E9C71}

Quando scegliete se utilizzare le suite di rapporti globali o globali, considerate quanto segue:

* Il numero di chiamate server è critico per la mia organizzazione? Se le chiamate al server limitate sono limitate, prendete in considerazione l'utilizzo di rollup. Suite di rapporti globali quasi due volte il numero di chiamate server effettuate.
* La segnalazione di un traffico di alto livello in tutte le suite è sufficiente? Se i visitatori deduplicati sono un requisito, prendete in considerazione l'implementazione di una suite di rapporti globale.
* Sono importanti i percorsi e gli eventi di conversione/successo tra domini diversi? Se le campagne cross-site vengono utilizzate in modo esteso, provate a implementare una suite di rapporti globale.
* Visualizza il totale dei dati sui siti Web? Le singole suite di rapporti continuano a essere comunicate in tempo reale. Se la visualizzazione dei totali della suite di rapporti è adeguata, vengono consigliati rollup.
* È disponibile un'ampia quantità di dati storici fruibili? Le suite di rapporti globali non possono riportare in modo retroattivo: i rollup sono consigliati se sono importanti i dati della cronologia.
* Il data warehouse e l'analisi ad hoc sono essenziali per aggiungere rapporti? In tal caso, si consiglia di utilizzare una suite di rapporti globale.

Nessuna scelta interessa le singole suite di rapporti. Valutate attentamente i professionisti e i s prima di determinare quale organizzazione preferisce.
