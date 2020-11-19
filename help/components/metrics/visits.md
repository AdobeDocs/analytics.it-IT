---
title: Visite
description: Una sequenza di pagine visualizzate in una sessione.
translation-type: tm+mt
source-git-commit: ee9868b53b93c1ffabdd48e83e38d3cafc9a4c2a
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 1%

---


# Visite

La metrica &quot;Visite&quot; mostra il numero di sessioni tra tutti i visitatori del sito.

## Modalità di calcolo di questa metrica

Una visita è sempre legata a un periodo di tempo, quindi sai se contare una nuova visita se la stessa persona torna sul tuo sito. Una visita inizia quando l&#39;utente arriva sul sito per la prima volta. Una visita termina quando soddisfano uno dei seguenti criteri:

* **30 minuti di inattività**: Quasi tutte le sessioni terminano in questo modo. Se tra gli hit mancano più di 30 minuti, inizia una nuova visita.
* **12 ore di attività**: Se un utente attiva in modo coerente le richieste di immagini senza spazi vuoti di 30 minuti per più di 12 ore, viene automaticamente avviata una nuova visita.
* **2500 hit**: Se un utente genera un numero elevato di hit senza avviare una nuova sessione, viene conteggiata una nuova visita dopo 2500 richieste di immagini.
* **100 hit in 100 secondi**: Se una visita è composta da più di 100 hit che si verificano in meno di 100 secondi, la visita termina automaticamente. Questo comportamento indica in genere l&#39;attività dei bot, e questa limitazione viene applicata per migliorare le prestazioni dei report.

Una visita non coincide necessariamente con una sessione del browser a causa dei criteri di cui sopra. Una delle differenze più comuni è la posizione in cui un visitatore accede al sito, lascia la scheda aperta per più di 30 minuti, quindi riprende la navigazione. Sebbene tale azione faccia tecnicamente parte della stessa sessione di navigazione,  Adobe considera tale azione due visite separate.

## Comportamento che influisce sulle visite

Se un visitatore esegue una di queste azioni, inizia una nuova visita:

* Elimina la cache durante la sessione di mid-session e continua a navigare nel sito
* Lascia il tuo sito aperto in una scheda per più di 30 minuti, quindi continua la navigazione
* Apre un altro browser e accede al sito sullo stesso computer
* La stessa persona che naviga sul sito su diversi dispositivi

Se un visitatore esegue una di queste azioni, una nuova visita **non** inizia a condizione che vi siano meno di 30 minuti tra gli hit consecutivi:

* Chiude il browser, quindi accede di nuovo al sito
* Riavvia il computer, apre lo stesso browser e torna al sito
* Transizioni verso una rete diversa, ad esempio la disconnessione da una stazione di collegamento di rete cablata a una rete wireless
* Consente di navigare nel sito in più schede. Se un visitatore passa da una scheda all’altra, ogni hit viene conteggiato come parte della stessa visita.

## Modificare la definizione di una visita

Puoi cambiare la definizione di visita in un&#39;ora diversa da 30 minuti.

* Per le suite [di rapporti](../vrs/vrs-about.md)virtuali, puoi modificare il timeout della visita utilizzando il [!UICONTROL Visit timeout] menu a discesa. Puoi impostare il timeout della visita su qualsiasi valore ragionevole.
* Per le suite di rapporti standard, contatta l’Assistenza clienti per richiedere che la lunghezza della visita sia ridotta per una determinata suite di rapporti. La lunghezza delle visite per le suite di rapporti standard non può superare i 30 minuti, pertanto puoi solo abbreviarla.

## Visite che si estendono su un limite di date

Una visita viene conteggiata per ogni periodo di tempo. Ad esempio, se un visitatore inizia la navigazione sul sito il lunedì alle 11:45, quindi invia la sua ultima richiesta immagine martedì alle 12:10, verrà attribuita una visita sia al lunedì che al martedì. Tuttavia, la metrica visita totale è deduplicata e mostra una singola visita per l’intervallo di date del progetto.

## Visite su una dimensione rispetto alle visite totali

Le visite nel contesto di una dimensione (ad esempio, [Canale](../dimensions/marketing-channel.md)marketing) mostrano il numero di visite che contenevano un particolare elemento dimensione in qualsiasi momento. Nella stessa visita esistono spesso più elementi dimensionali con diversi hit. Il tentativo di sommare le visite che segnalano gli elementi dimensionali in genere non ha senso.

## Visita tutti i visitatori nella Data Warehouse

La metrica &quot;Visite - Tutti i visitatori&quot; è disponibile in Data Warehouse oltre alla metrica &quot;Visite&quot;. La metrica &quot;Visite - Tutti i visitatori&quot; è paragonabile alla metrica &quot;Visite&quot; in altri strumenti Analytics. La metrica &quot;Visite&quot; nella Data Warehouse esclude i visitatori che non dispongono di cookie persistenti.  Adobe consiglia di utilizzare &#39;Visite - Tutti i visitatori&#39; nelle richieste di Data Warehouse in cui le visite sono desiderate come metrica.
