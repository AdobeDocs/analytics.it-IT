---
title: Visite
description: Una sequenza di pagine visualizzate in una sessione.
feature: Metrics
exl-id: 4f78f2b5-f958-44fe-876a-83f07980beec
source-git-commit: ceee6f27581abc288ff08134218ae7f6b93e9201
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 1%

---

# Visite

La metrica &quot;Visite&quot; mostra il numero di sessioni in tutti i visitatori del sito.

## Calcolo di questa metrica

Una visita collega sempre a un periodo di tempo, quindi sai se contare una nuova visita se la stessa persona ritorna al tuo sito. Una visita inizia quando l’utente arriva per la prima volta sul sito. Una visita termina quando soddisfano uno dei seguenti criteri:

* **30 minuti di inattività**: Quasi tutte le sessioni terminano in questo modo. Se trascorrono più di 30 minuti tra un’occorrenza e l’altra, inizia una nuova visita.
* **12 ore di attività**: Se un utente attiva in modo coerente le richieste di immagini senza spazi di 30 minuti per più di 12 ore, viene avviata automaticamente una nuova visita.
* **2500 hit**: Se un utente genera un numero elevato di hit senza avviare una nuova sessione, una nuova visita viene conteggiata dopo 2500 richieste di immagini.
* **100 hit in 100 secondi**: Se una visita ha più di 100 hit che si verificano nei primi 100 secondi della visita, la visita termina automaticamente. Questo comportamento indica tipicamente l’attività bot e questa limitazione viene applicata per migliorare le prestazioni dei report.

Una visita non coincide necessariamente con una sessione del browser a causa dei criteri impostati. Una delle differenze più comuni è la posizione in cui un visitatore accede al sito, lascia aperta la scheda per più di 30 minuti, quindi riprende la navigazione. Anche se questa azione fa tecnicamente parte della stessa sessione di navigazione, l’Adobe considera questa azione due visite separate.

## Comportamento che influisce sulle visite

Se un visitatore esegue una di queste azioni, inizia una nuova visita:

* Cancella la loro cache a metà sessione e continua a navigare nel sito
* Lascia il tuo sito aperto in una scheda per più di 30 minuti, quindi continua la navigazione
* Apre un browser diverso e passa al sito nello stesso computer
* Stessa persona che naviga sul tuo sito su diversi dispositivi

Se un visitatore esegue una di queste azioni, una nuova visita **not** inizia se ci sono meno di 30 minuti tra hit consecutivi:

* Chiude il browser, quindi torna al sito
* Riavvia il computer, apre lo stesso browser e torna al sito
* Transizione verso una rete diversa, ad esempio la disconnessione da una docking station di rete cablata a una rete wireless
* Sfoglia il sito in più schede. Se un visitatore passa da una scheda all’altra, ogni hit viene conteggiato come parte della stessa visita.

## Modificare la definizione di visita

Puoi modificare la definizione di visita in un’ora diversa da 30 minuti.

* Per [Suite di rapporti virtuali](../vrs/vrs-about.md), puoi modificare il timeout della visita utilizzando [!UICONTROL Visit timeout] a discesa. Puoi modificare il timeout della visita a qualsiasi valore ragionevole.
* Per le suite di rapporti standard, contatta l’Assistenza clienti per richiedere che la lunghezza della visita sia ridotta per una determinata suite di rapporti. La lunghezza delle visite per le suite di rapporti standard non può superare i 30 minuti, quindi puoi solo accorciarla.

## Visite che si estendono su un limite di data

Una visita viene conteggiata per ogni periodo di tempo. Ad esempio, se un visitatore inizia a navigare sul tuo sito lunedì alle 11:45, e poi invia la sua ultima richiesta di immagine martedì alle 12:10, vedrai una visita attribuita sia a lunedì che a martedì. Tuttavia, la metrica di visita totale viene deduplicata, mostrando una singola visita per l’intervallo di date del progetto.

## Visite su una dimensione rispetto alle visite totali

Visite nel contesto di una dimensione (ad esempio, [Canale di marketing](../dimensions/marketing-channel.md)) mostra il numero di visite che contenevano un particolare elemento dimensionale in qualsiasi momento. Nella stessa visita sono spesso presenti più elementi dimensionali su hit diversi. Il tentativo di sommare le visite che generano rapporti su elementi dimensionali di solito non ha senso.

## Visita tutti i visitatori nella Data Warehouse

La metrica &quot;Visite - Tutti i visitatori&quot; è disponibile in Data Warehouse oltre alla metrica &quot;Visite&quot;. La metrica &quot;Visite - Tutti i visitatori&quot; è paragonabile alla metrica &quot;Visite&quot; in altri strumenti di Analytics. La metrica &quot;Visite&quot; nella Data Warehouse esclude i visitatori che non hanno cookie persistenti. Adobe consiglia di utilizzare &quot;Visite - Tutti i visitatori&quot; nelle richieste di Data Warehouse in cui le visite sono desiderate come metrica.
