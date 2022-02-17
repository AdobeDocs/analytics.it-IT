---
title: Totale secondi trascorsi
description: Numero totale aggregato di secondi trascorsi per l’elemento dimensione.
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# Totale secondi trascorsi

La metrica &quot;Totale secondi trascorsi&quot; mostra il numero aggregato di secondi trascorsi da un visitatore per un dato elemento dimensione. Questa metrica è utile quando desideri la quantità di tempo grezzo trascorso su un dato elemento dimensione e non le medie come le altre offerte di metriche sul tempo trascorso.

Al Report Builder, questa metrica si chiama &quot;Tempo totale trascorso&quot;.

## Calcolo di questa metrica

Questa metrica utilizza i seguenti passaggi per misurare il calcolo:

1. Per un dato hit, osserva la marca temporale.
2. Confronta questo hit con la marca temporale dell’hit successivo nella visita. Conteggio degli hit di tracciamento delle visualizzazioni di pagina e dei collegamenti.
3. La quantità di secondi trascorsi tra i due hit contribuiscono all’elemento della dimensione.

Variabili persistenti, ad esempio [eVar](../dimensions/evar.md), conteggia i secondi totali trascorsi. Variabili del traffico, ad esempio [proprietà](../dimensions/prop.md), includi i secondi trascorsi nelle chiamate di tracciamento dei collegamenti successive.

>[!TIP]
>
>Il tempo trascorso non viene misurato per l’ultimo hit della visita, in quanto non esiste una richiesta di immagine successiva per misurare il tempo trascorso. Questo concetto si applica anche alle visite costituite da un singolo hit (un rimbalzo).

Vedi [Panoramica del tempo trascorso](time-spent.md) informazioni più generali sul tempo trascorso.
