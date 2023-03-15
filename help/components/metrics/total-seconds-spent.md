---
title: Totale secondi trascorsi
description: Numero totale aggregato di secondi trascorsi sull’elemento dimensione.
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# Totale secondi trascorsi

La metrica &quot;Totale secondi trascorsi&quot; mostra il numero aggregato di secondi trascorsi da un visitatore su un dato elemento dimensione. Questa metrica è utile quando si desidera la quantità di tempo trascorso su un dato elemento dimensionale e non si desidera calcolare la media come fanno altre metriche tempo trascorso.

In Report Builder, questa metrica è denominata &quot;Tempo totale trascorso&quot;.

## Modalità di calcolo di questa metrica

Questa metrica utilizza i seguenti passaggi per misurare il calcolo:

1. Per un dato hit, controlla la marca temporale.
2. Confronta questo hit con la marca temporale dell’hit successivo nella visita. Sono conteggiati sia gli hit di visualizzazione pagina che quelli di tracciamento dei collegamenti.
3. La quantità di secondi trascorsi tra i due hit contribuisce all’elemento dimensionale.

Variabili persistenti, come [eVar](../dimensions/evar.md), conteggio per il totale di secondi trascorsi. Variabili di traffico, come [prop](../dimensions/prop.md), include i secondi trascorsi nelle chiamate di tracciamento dei collegamenti successive.

>[!TIP]
>
>Il tempo trascorso non viene misurato per l’ultimo hit della visita, in quanto non esiste una successiva richiesta di immagine per misurare il tempo trascorso. Questo concetto si applica anche alle visite consistenti in un singolo hit (un mancato recapito).

Consulta [Panoramica sul tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
