---
title: Dispositivi univoci
description: Numero di dispositivi univoci.
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: 407111f6016fe8595f1d5c3464e36dfd4d314630
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 2%

---

# Dispositivi univoci

La metrica &quot;Dispositivi unici&quot; è una metrica [Analisi multidispositivo](../cda/overview.md) che conta il numero di dispositivi univoci non identificati e di dispositivi virtuali univoci. I dispositivi non identificati sono dispositivi che hanno generato hit anonimi. I dispositivi virtuali univoci sono persone distinte identificate per dispositivo.

## Calcolo di questa metrica

Per ciascun dispositivo, somma tutte le persone distinte associate (incluso anonimo se il dispositivo contiene hit non uniti).

Tieni presente che questa metrica non è uguale a [Visitatori unici](unique-visitors.md) nelle suite di rapporti non CDA. Ad esempio, un dispositivo è condiviso da 3 account diversi. Se tutti e 3 gli account visitano il tuo sito in un intervallo di reporting, il rapporto risultante mostrerà 3 Dispositivi univoci in CDA. Gli stessi dati al di fuori di CDA mostrerebbero 1 Visitatore univoco.

## Esempio

1. Bob arriva al tuo sito sul suo telefono tramite un annuncio, ma non è connesso.
1. Bob vuole fare un acquisto, ma preferirebbe farlo sul computer di famiglia perché è già connesso lì. Sul computer di famiglia fa un acquisto.
1. Il giorno dopo controlla il suo ordine sul suo telefono e vi si autentica.
1. La moglie di Bob, Alice, naviga sul tuo sito mentre accedi al suo account sul computer della famiglia.
1. Anche il fratello di Bob, Charles, naviga sul tuo sito durante l&#39;accesso al suo account sul computer della famiglia.

![Conteggio dispositivi univoci](/help/components/metrics/assets/Unique_Devices_Count.png)

La visualizzazione di questi dati in una suite di rapporti virtuali CDA prima di [Riproduci](/help/components/cda/replay.md) mostrerebbe:

* **5 dispositivi** univoci: 1 per Bob non autenticato + 2 per Bob + 1 per Alice + 1 per Charles
* **4  [Persone](people.md)**: 1  [Persone](unidentified-people.md)  Non Identificate + 3 Persone  [Identificate](identified-people.md).

