---
title: Dispositivi univoci
description: Numero di dispositivi univoci.
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Dispositivi univoci

La metrica &quot;Dispositivi unici&quot; è un [Analisi multidispositivo](../cda/overview.md) metrica che conta il numero di dispositivi univoci non identificati e di dispositivi virtuali univoci. I dispositivi non identificati sono dispositivi che hanno generato hit anonimi. I dispositivi virtuali univoci sono persone distinte identificate per dispositivo.

## Calcolo di questa metrica

Per ciascun dispositivo, somma tutte le persone distinte associate (incluso anonimo se il dispositivo contiene hit non uniti).

Tieni presente che questa metrica non è uguale a [Visitatori unici](unique-visitors.md) nelle suite di rapporti non CDA. Ad esempio, un dispositivo è condiviso da 3 account diversi. Se tutti e 3 gli account visitano il tuo sito in un intervallo di reporting, il rapporto risultante mostrerà 3 Dispositivi univoci in CDA. Gli stessi dati al di fuori di CDA mostrerebbero 1 Visitatore univoco.

## Esempio

1. Sally arriva al tuo sito sul suo telefono tramite un annuncio pubblicitario, ma non ha effettuato l&#39;accesso.
1. Sally vuole fare un acquisto, ma preferirebbe farlo sul computer della famiglia perché ha già effettuato l&#39;accesso lì. Sul computer di famiglia fa un acquisto.
1. Il giorno successivo, controlla il suo ordine sul suo telefono e si autentica lì.
1. La moglie di Bob, Alice, naviga sul tuo sito mentre accedi al suo account sul computer della famiglia.
1. Anche il fratello di Bob, Charles, naviga sul tuo sito durante l&#39;accesso al suo account sul computer della famiglia.

![Conteggio dispositivi univoci](/help/components/metrics/assets/Unique_Devices_Count.png)

Visualizzazione di questi dati in una suite di rapporti virtuali CDA prima [Riproduci](/help/components/cda/replay.md) gli hit potenzialmente non autenticati potrebbero essere uniti per mostrare:

* **5 dispositivi univoci**: 1 per Bob non autenticato + 2 per Bob + 1 per Alice + 1 per Charles
* **4 [Persone](people.md)**: 1 [Persone non identificate](unidentified-people.md) + 3 [Persone identificate](identified-people.md).
