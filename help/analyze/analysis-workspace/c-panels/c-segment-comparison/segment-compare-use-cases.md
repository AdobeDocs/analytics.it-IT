---
title: Casi di utilizzo del confronto dei segmenti
description: Scopri i casi d’uso reali su come il pannello di confronto dei segmenti può essere utilizzato per acquisire informazioni approfondite sulla strategia di marketing.
keywords: IQ segmento
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Casi d’utilizzo del segmento IQ

Il pannello di confronto dei segmenti è una funzione ampiamente utilizzata in Analysis Workspace. Spesso i clienti scoprono nuovi modi per ottenere informazioni approfondite. Di seguito sono riportati diversi casi di utilizzo riusciti.

## Caso di utilizzo 1: confronto tra implementazioni mobile e desktop

> *“Abbiamo confrontato le hit da un sito all’altro e abbiamo rapidamente riscontrato diverse incongruenze a livello di assegnazione tag. In questo modo abbiamo evitato problemi ai dati prima del rilascio del prodotto”.*

A un responsabile prodotto che gestisce un sito Web per dispositivi mobili e desktop è stato affidato il compito di assicurarsi che i tag fossero coerenti tra dispositivi mobili e desktop. Per assicurarsi di non aver perso nulla di importante, ha utilizzato il pannello di confronto dei segmenti per confrontare gli hit provenienti dal sito mobile con quelli provenienti dal sito desktop. Ha notato che non c'erano eventi di check-out sul sito mobile e ha ottenuto i tag corretti in luogo prima che il sito mobile fosse rilasciato. In questo modo, il responsabile prodotto ha evitato un data disaster causato dalla mancata registrazione delle conversioni da parte del sito Web mobile.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenitore di hit in cui Mobile Device Type è uguale a Mobile Phone o Tablet | Tutti gli altri |

## Caso di utilizzo 2: confrontare i clienti che utilizzano una determinata funzione con quelli che non la utilizzano

> *“Abbiamo scoperto che i clienti che utilizzavano la funzionalità di confronto del nostro prodotto avevano il 10% di possibilità di decidere per l’acquisto. L’abbiamo spostata nella parte superiore della pagina, e gli ordini sono cresciuti del 4%!”*

Un team di ottimizzazione per i siti di vendita al dettaglio voleva capire meglio gli utenti che interagivano con una funzione di confronto dei prodotti che avevano recentemente pubblicato. Hanno utilizzato il pannello di confronto dei segmenti per confrontare gli utenti che hanno utilizzato la funzione di confronto dei prodotti con tutti gli altri partecipanti al sito. Hanno rapidamente identificato diverse importanti differenze, tra cui il fatto che questi utenti avevano il 10% di probabilità in più di acquistare un prodotto. Il team di ottimizzazione sito ha deciso di testare la funzionalità di confronto del prodotto collocandola in maniera più evidente nella parte superiore della pagina.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenitore di visitatori in cui esiste un evento personalizzato (strumento di confronto dei prezzi) | Tutti gli altri |

## Caso di utilizzo 3: confronta i visitatori del sito di notizie con altri visitatori della sezione del sito

> *“Abbiamo scoperto che i visitatori della nostra sezione news avevano una probabilità di due volte superiore di guardare video pubblicitari, per questo abbiamo aggiunto più opzioni video a quella sezione. I video pubblicitari visualizzati sono aumentati del 7%!”*

Una delle principali case editrici di media ha cercato di migliorare il livello di coinvolgimento dei contenuti per i destinatari nella sezione news. Hanno creato un segmento di visitatori che hanno visitato la sezione news del sito per capire meglio il pubblico delle notizie. Hanno immediatamente scoperto che questi utenti avevano una probabilità di due volte superiore di guardare video pubblicitari rispetto ai visitatori di qualsiasi altra sezione del sito. Il team video ha creato una sezione video consigliata sulla barra laterale delle news e ha ottenuto un aumento del 7% degli annunci video visualizzati.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenitore di visitatori per cui Sezione sito è uguale a 'News' | Tutti gli altri |

## Caso di utilizzo 4: confrontare i visitatori dalla ricerca a pagamento con tutti gli altri

> *“I visitatori che accedevano al nostro sito tramite motori di ricerca erano tre volte più propensi all’up-sell rispetto a qualsiasi altro utente. We upped our spend on specific keywords as a result and achieved a 56% increase in up-sells."*

Una grande azienda di servizi B2B desiderava capire il tipo di traffico che le parole chiave paid search portavano al loro sito. La ricerca a pagamento non aveva portato direttamente a molte conversioni, e l'amministratore marketing ha considerato un budget decrescente per esso. Il team marketing ha creato un segmento di visitatori che sono venuti sul sito tramite paid search e li ha confrontati con tutti gli altri visitatori utilizzando il pannello di confronto dei segmenti. Hanno scoperto che anche se questi visitatori non avevano la stessa probabilità di una conversione diretta, avevano 3 volte più probabilità di fare un up-sell su un servizio precedentemente acquistato. Il team marketing ha focalizzato il proprio budget sulle parole chiave correlate all'up-sell e ha visto un aumento del 56% nelle vendite di servizi.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenitore di visitatori in cui Tipo referente è uguale a Ricerca a pagamento | Tutti gli altri |

## Caso di utilizzo 5: confrontare gli acquirenti Fitbit con tutti gli altri

> *"Abbiamo scoperto che le persone che acquistano Fitbit avevano 6 volte più probabilità di ricevere un messaggio "esaurito" rispetto a tutti gli altri, così abbiamo rapidamente ordinato più Fitbit ed evitato di esaurire le scorte!"*

**** Scenario: Un importante rivenditore online era interessato alle vendite di Fitbit, uno dei prodotti più ricercati del periodo delle feste, e a ciò che rendeva unici gli acquirenti di Fitbit tra gli altri. Con un semplice clic con il pulsante destro del mouse sull’elemento di riga “Fitbit” nei rapporti sui prodotti, il team marketing ha potuto eseguire rapidamente un’analisi IQ segmento. Ciò che hanno scoperto è che gli acquirenti Fitbit avevano una probabilità di 6 volte superiore di ricevere il messaggio “esaurito” rispetto a qualsiasi altro cliente. Dopo ulteriori analisi, il team marketing è stato in grado di dirigere i visitatori ai negozi fisici mentre attendevano che il reparto acquisti ordinasse ulteriori Fitbit da spedire. Come risultato, il rivenditore ha evitato ulteriori messaggi di “esaurimento” ed è stato in grado di soddisfare la maggiore domanda del periodo festivo.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contenitore di visitatori in cui esistono ordini e la dimensione personalizzata Brand uguale a FitBit | Tutti gli altri |
