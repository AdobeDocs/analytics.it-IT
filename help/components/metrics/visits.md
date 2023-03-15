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

La metrica &quot;Visite&quot; mostra il numero di sessioni per tutti i visitatori sul sito.

## Modalità di calcolo di questa metrica

Una visita è sempre associata a un periodo di tempo, pertanto sai se contare una nuova visita se la stessa persona ritorna sul tuo sito. Una visita inizia quando l’utente arriva sul sito per la prima volta. Una visita termina quando il visitatore soddisfa uno dei seguenti criteri:

* **30 minuti di inattività**: quasi tutte le sessioni terminano in questo modo. Se trascorrono più di 30 minuti tra un hit e l’altro, inizia una nuova visita.
* **12 ore di attività**: se un utente genera in modo coerente richieste di immagini senza intervalli di 30 minuti per più di 12 ore, viene automaticamente avviata una nuova visita.
* **2500 hit**: se un utente genera un numero elevato di hit senza avviare una nuova sessione, viene conteggiata una nuova visita dopo 2500 richieste di immagini.
* **100 hit in 100 secondi**: se una visita contiene più di 100 hit che si verificano nei primi 100 secondi della visita, la visita termina automaticamente. Questo comportamento indica in genere l’attività di bot e questa limitazione viene applicata per contribuire a migliorare le prestazioni dei rapporti.

Una visita non coincide necessariamente con una sessione del browser a causa dei criteri di cui sopra. Una delle differenze più comuni è rappresentata dal punto in cui un visitatore accede al sito, lascia la scheda aperta per più di 30 minuti e riprende la navigazione. Anche se questa azione fa tecnicamente parte della stessa sessione di navigazione, l’Adobe considera questa azione come due visite separate.

## Comportamento che influisce sulle visite

Se un visitatore esegue una di queste azioni, inizia una nuova visita:

* Cancella la cache a metà sessione e continua a navigare nel sito
* Lascia il sito aperto in una scheda per più di 30 minuti, quindi continua la navigazione
* Apre un browser diverso e passa al sito sullo stesso computer
* La stessa persona che naviga nel sito su dispositivi diversi

Se un visitatore esegue una di queste azioni, si verifica una nuova visita **non** inizia finché mancano meno di 30 minuti tra due hit consecutivi:

* Chiude il browser, quindi torna al sito
* Riavvia il computer, apre lo stesso browser e torna al sito
* Transizioni a una rete diversa, ad esempio la disconnessione da un alloggiamento di espansione di rete cablata a una rete wireless
* Esplora il sito in più schede. Se un visitatore passa da una scheda all’altra, ogni hit conta come parte della stessa visita.

## Modificare la definizione di visita

Puoi modificare la definizione di visita in un orario diverso da 30 minuti.

* Per [Suite di rapporti virtuali](../vrs/vrs-about.md), è possibile modificare il timeout della visita utilizzando [!UICONTROL Visit timeout] a discesa. Puoi impostare un timeout visita su qualsiasi valore ragionevole.
* Per le suite di rapporti standard, contatta l’Assistenza clienti per richiedere che la durata della visita sia ridotta per una determinata suite di rapporti. La durata della visita per le suite di rapporti standard non può superare i 30 minuti, quindi puoi solo abbreviarla.

## Visite che si estendono su un limite di date

Una visita conta per ogni periodo di tempo interessato. Ad esempio, se un visitatore inizia a navigare nel sito lunedì alle 23:45 e poi invia la sua ultima richiesta di immagine martedì alle 00:10, vedrai una visita attribuita sia a lunedì che a martedì. Tuttavia, la metrica di visita totale è deduplicata e mostra una singola visita per l’intervallo di date del progetto.

## Visite su una dimensione rispetto a visite totali

Visite nel contesto di una dimensione (ad esempio, [Canale di marketing](../dimensions/marketing-channel.md)) mostra in qualsiasi momento il numero di visite che contenevano un particolare elemento dimensionale. Esistono spesso più elementi dimensionali su hit diversi nella stessa visita. In genere, non ha senso sommare le visite che generano rapporti sugli elementi dimensionali.

## Visita tutti i visitatori in Data Warehouse

La metrica &quot;Visite - Tutti i visitatori&quot; è disponibile in Data Warehouse oltre alla metrica &quot;Visite&quot;. La metrica &quot;Visite - Tutti i visitatori&quot; è paragonabile alla metrica &quot;Visite&quot; in altri strumenti di Analytics. La metrica &quot;Visite&quot; nella Data Warehouse esclude i visitatori che non hanno cookie persistenti. L’Adobe consiglia di utilizzare &quot;Visite - Tutti i visitatori&quot; nelle richieste Data Warehouse in cui le visite sono desiderate come metrica.
