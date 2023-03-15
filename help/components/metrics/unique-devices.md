---
title: Dispositivi univoci
description: Il numero di dispositivi univoci.
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Dispositivi univoci

La metrica &quot;Dispositivi univoci&quot; è una [Analisi cross-device](../cda/overview.md) metrica che conta il numero di dispositivi non identificati univoci e di dispositivi virtuali univoci. I dispositivi non identificati sono dispositivi che hanno generato hit anonimi. I dispositivi virtuali univoci sono persone distinte identificate per dispositivo.

## Modalità di calcolo di questa metrica

Per ogni dispositivo, somma tutte le persone distinte associate a esso (incluso anonimo se il dispositivo contiene hit non uniti).

Tieni presente che questa metrica non è uguale a [Visitatori univoci](unique-visitors.md) nelle suite di rapporti non CDA. Ad esempio, un dispositivo è condiviso da 3 account diversi. Se tutti e 3 gli account visitano il sito in un intervallo di reporting, il rapporto risultante mostrerà 3 dispositivi univoci in CDA. Gli stessi dati al di fuori di CDA mostrerebbero 1 Visitatore univoco.

## Esempio

1. Sally arriva al tuo sito sul suo telefono tramite un annuncio, ma non ha effettuato l’accesso.
1. Sally vuole fare un acquisto, ma preferirebbe farlo sul computer di famiglia perché ha già effettuato l’accesso. Nel computer di famiglia, fa un acquisto.
1. Il giorno dopo, controlla l&#39;ordine al suo telefono e si autentica lì.
1. La moglie di Bob, Alice, naviga nel tuo sito mentre ha effettuato l&#39;accesso al suo account sul computer di famiglia.
1. Anche il fratello di Bob, Charles, naviga nel tuo sito mentre è connesso al suo account sul computer di famiglia.

![Numero di dispositivi univoci](/help/components/metrics/assets/Unique_Devices_Count.png)

Visualizzazione di questi dati in una suite di rapporti virtuali CDA prima [Riproduci](/help/components/cda/replay.md) potenzialmente gli hit non autenticati possono mostrare:

* **5 dispositivi univoci**: 1 per Bob + 2 non autenticato per Bob + 1 per Alice + 1 per Charles
* **4 [Persone](people.md)**: 1 [Persone non identificate](unidentified-people.md) + 3 [Persone identificate](identified-people.md).
