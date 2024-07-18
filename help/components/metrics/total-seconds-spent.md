---
title: Totale secondi trascorsi
description: Numero totale aggregato di secondi trascorsi sull’elemento dimensione.
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 5%

---

# Totale secondi trascorsi

La [metrica](overview.md) &quot;Totale secondi trascorsi&quot; mostra il numero aggregato di secondi trascorsi da un visitatore su un dato elemento della dimensione. Questa metrica è utile quando si desidera la quantità di tempo trascorso su un dato elemento dimensionale e non si desidera calcolare la media come fanno altre metriche tempo trascorso.

In Report Builder, questa metrica è denominata &quot;Tempo totale trascorso&quot;.

## Come è calcolata questa metrica

Questa metrica utilizza i seguenti passaggi per misurare il calcolo:

1. Per un dato hit, controlla la marca temporale.
2. Confronta questo hit con la marca temporale dell’hit successivo nella visita. Sono conteggiati sia gli hit di visualizzazione pagina che quelli di tracciamento dei collegamenti.
3. La quantità di secondi trascorsi tra i due hit contribuisce all’elemento dimensionale.

Le variabili persistenti, ad esempio [eVar](../dimensions/evar.md), vengono conteggiate in base al totale dei secondi trascorsi. Le variabili di traffico, ad esempio [props](../dimensions/prop.md), includono i secondi trascorsi nelle successive chiamate di tracciamento dei collegamenti.

>[!TIP]
>
>Il tempo trascorso non viene misurato per l’ultimo hit della visita, in quanto non esiste una successiva richiesta di immagine per misurare il tempo trascorso. Questo concetto si applica anche alle visite consistenti in un singolo hit (un mancato recapito).

Consulta [Panoramica sul tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
