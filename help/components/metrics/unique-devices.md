---
title: Dispositivi univoci
description: Il numero di dispositivi univoci.
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: 16a9c9a2b6692b9b1944cfdb9b5b0411d48db666
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 3%

---

# Dispositivi univoci

La metrica [metric](overview.md) relativa ai &#39;dispositivi univoci&#39; è una metrica di analisi tra dispositivi[ che conta il numero di dispositivi univoci non identificati e di dispositivi virtuali univoci. ](../cda/overview.md) I dispositivi non identificati sono dispositivi che hanno generato hit anonimi. I dispositivi virtuali univoci sono persone distinte identificate per dispositivo.

## Come è calcolata questa metrica

Per ogni dispositivo, somma tutte le persone distinte associate a esso (incluso anonimo se il dispositivo contiene hit non uniti).

Questa metrica non è uguale a [Visitatori univoci](unique-visitors.md) nelle suite di rapporti non CDA. Ad esempio, un dispositivo è condiviso da 3 account diversi. Se tutti e 3 gli account visitano il sito in un intervallo di reporting, il rapporto risultante mostrerà 3 dispositivi univoci in CDA. Gli stessi dati al di fuori di CDA mostrerebbero 1 Visitatore univoco.

## Esempio

1. Sally arriva al tuo sito telefonicamente tramite un annuncio, ma non ha effettuato l’accesso.
1. Sally vuole fare un acquisto, ma preferirebbe farlo sul computer di famiglia perché ha già effettuato l’accesso. Nel computer di famiglia, fa un acquisto.
1. Il giorno dopo, controlla l&#39;ordine al telefono e si autentica lì.
1. La moglie di Bob, Alice, naviga nel tuo sito mentre ha effettuato l&#39;accesso al suo account sul computer di famiglia.
1. Anche il fratello di Bob, Charles, naviga nel tuo sito mentre è connesso al suo account sul computer di famiglia.

![Numero dispositivi univoci](/help/components/metrics/assets/Unique_Devices_Count.png)

La visualizzazione di questi dati in una suite di rapporti virtuale di CDA prima di [Ripetizione](/help/components/cda/replay.md) potenziali unioni di hit non autenticati mostrerebbe:

* **5 dispositivi univoci**: 1 per Bob non autenticato + 2 per Bob + 1 per Alice + 1 per Charles
* **4 [Persone](people.md)**: 1 [Persone non identificate](unidentified-people.md) + 3 [Persone identificate](identified-people.md).
