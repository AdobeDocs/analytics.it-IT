---
title: Visite
description: Una sequenza di pagine visualizzate in una sessione.
feature: Metrics
exl-id: 4f78f2b5-f958-44fe-876a-83f07980beec
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 100%

---

# Visite

La [metrica](overview.md) “Visite” mostra il numero di sessioni per chiunque visita il sito.

## Come è calcolata di questa metrica

La visita è associata sempre a un periodo di tempo, pertanto sai se contare una nuova visita qualora la stessa persona ritorni sul tuo sito. La visita inizia quando l’utente arriva sul sito per la prima volta. e termina quando il visitatore soddisfa uno dei seguenti criteri:

* **30 minuti di inattività**: quasi tutte le sessioni terminano in questo modo. Se trascorrono più di 30 minuti tra un hit e l’altro, inizia una nuova visita.
* **12 ore di attività**: se un utente attiva in modo coerente richieste di immagini senza intervalli di 30 minuti per più di 12 ore, viene automaticamente avviata una nuova visita.
* **2500 hit**: se un utente genera un numero elevato di hit senza avviare una nuova sessione, viene conteggiata una nuova visita dopo 2500 richieste di immagini.
* **100 hit in 100 secondi**: se una visita contiene più di 100 hit che si verificano nei primi 100 secondi della visita, la visita termina automaticamente. Questo comportamento indica in genere l’attività di bot e la limitazione viene applicata per contribuire a migliorare le prestazioni dei rapporti.

Una visita non coincide necessariamente con una sessione del browser a causa dei criteri descritti in precedenza. Una delle differenze più comuni è rappresentata dal punto in cui un visitatore accede al sito, lascia la scheda aperta per più di 30 minuti e poi riprende la navigazione. Anche se questa azione fa parte tecnicamente della stessa sessione di navigazione, Adobe la considera come due visite separate.

## Comportamento che influisce sulle visite

Se un visitatore esegue una di queste azioni, inizia una nuova visita:

* cancella la cache a metà sessione e continua a navigare nel sito;
* lascia il sito aperto in una scheda per più di 30 minuti, quindi continua la navigazione;
* apre un browser diverso e passa al sito sullo stesso computer;
* naviga sul sito da dispositivi diversi

Se un visitatore esegue una di queste azioni, una nuova visita **non** inizierà fintanto che tra due hit consecutivi ci sono meno di 30 minuti:

* Chiude il browser, quindi torna al sito;
* riavvia il computer, apre lo stesso browser e torna al sito;
* transita verso una rete diversa, come disconnettersi da una docking station di rete cablata a una rete wireless;
* esplora il sito in più schede. Se un visitatore passa da una scheda all’altra, ogni hit viene considerato come parte della stessa visita.

## Modificare la definizione di visita

Puoi modificare la definizione di visita in un periodo diverso da 30 minuti.

* Per le [Suite di rapporti virtuali](../vrs/vrs-about.md), è possibile modificare il timeout della visita utilizzando l&#39;elenco a discesa [!UICONTROL Visit timeout]. Puoi impostare un timeout della visita su qualsiasi valore ragionevole.
* Per le suite di rapporti standard, contatta l’Assistenza clienti e richiedi che la durata della visita venga ridotta per una determinata suite di rapporti. La durata della visita per suite di rapporti standard non può superare i 30 minuti, quindi puoi solo ridurla.

## Visite che si estendono su un limite di date

Per ogni periodo di tempo interessato, viene considerata una visita. Ad esempio, se un visitatore inizia a navigare sul sito lunedì alle 23:45 e poi invia la sua ultima richiesta di immagine martedì alle 00:10, si vedrà una visita attribuita sia a lunedì che a martedì. Tuttavia, la metrica di visita totale è deduplicata e mostra una singola visita per l’intervallo di date del progetto.

## Visite su una dimensione rispetto alle visite totali

Le visite nel contesto di una dimensione (ad esempio, [canale di marketing](../dimensions/marketing-channel.md)) mostrano il numero di visite che contenevano un particolare elemento dimensionale in qualsiasi momento. Nella stessa visita, esistono spesso più elementi dimensionali su hit diversi. In genere, non ha senso sommare le visite che generano rapporti su elementi dimensionali.

## Visite: tutti i visitatori nel Data Warehouse

Nel Data Warehouse, oltre alla metrica “Visite”, è disponibile la metrica “Visite: tutti i visitatori”. La metrica “Visite: tutti i visitatori” è paragonabile alla metrica “Visite” in altri strumenti di Analytics. La metrica “Visite” nel Data Warehouse esclude i visitatori che non hanno cookie persistenti. Adobe consiglia di utilizzare “Visite: tutti i visitatori” nelle richieste del Data Warehouse, in cui le visite sono desiderate come metrica.
