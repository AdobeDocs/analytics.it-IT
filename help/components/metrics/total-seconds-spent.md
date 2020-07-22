---
title: Totale secondi trascorsi
description: Il numero totale aggregato di secondi trascorsi per l’elemento della dimensione.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---


# Totale secondi trascorsi

La metrica &#39;Totale secondi trascorsi&#39; mostra il numero aggregato di secondi trascorsi da un visitatore per un dato elemento dimensione. Questa metrica è utile quando vuoi che la quantità di tempo trascorso su un dato elemento dimensione sia ridotta, e non che la media sia simile all’offerta delle altre metriche del tempo trascorso.

Nel Generatore di report, questa metrica è denominata &#39;Tempo totale trascorso&#39;.

## Modalità di calcolo di questa metrica

Questa metrica utilizza i seguenti passaggi per misurare il calcolo:

1. Per un determinato hit, osservate la marca temporale.
2. Confronta questo hit con la marca temporale dell’hit successivo nella visita. Conteggio degli hit di tracciamento delle visualizzazioni delle pagine e dei collegamenti.
3. La quantità di secondi trascorsi tra i due hit contribuiscono all’elemento della dimensione.

Le variabili persistenti, come [eVar](../dimensions/evar.md), vengono conteggiate per i secondi totali spesi. Le variabili di traffico, come [prop](../dimensions/prop.md), includono i secondi trascorsi tra le chiamate di tracciamento dei collegamenti successive.

>[!TIP]
>
>Il tempo trascorso non viene misurato per l’ultimo hit della visita, in quanto non esiste una richiesta immagine successiva per misurare il tempo trascorso. Questo concetto si applica anche alle visite costituite da un singolo hit (un rimbalzo).

Consultate Panoramica sul [tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
