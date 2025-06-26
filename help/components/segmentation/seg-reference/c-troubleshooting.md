---
description: Risolvere i problemi relativi ai segmenti.
title: Risoluzione dei problemi di segmentazione
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 0%

---

# Risoluzione dei problemi di segmentazione

<!-- Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.

-->

## Perché il segmento non restituisce alcun dato? {#no-data}

Possibili motivi:

* Annidamento inverso: ad esempio, nidificando un contenitore ![Utente](/help/assets/icons/User.svg) **[!UICONTROL Visitor]** in un contenitore ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Visit]**.
* Il rapporto non supporta la segmentazione.
* Non ci sono dati corrispondenti ai criteri di segmentazione.

## Perché non riesco a visualizzare il segmento creato nel Gestore segmenti? {#invisible}

Possibili motivi:

* Alcune dimensioni sono disponibili solo in Data Warehouse e non nel Gestore segmenti.
* Il segmento viene controllato solo per una suite di rapporti specifica.
* Un segmento condiviso potrebbe essere stato eliminato da un altro utente.
* Impossibile caricare i segmenti a causa di un problema del centro dati o della cache del browser.
* Segmento non salvato.
* L&#39;indirizzo IP potrebbe essere bloccato alla fine dell&#39;utente.

## Perché i dati visualizzati dopo l’applicazione di un segmento sembrano errati? {#page-data}

Possibili motivi:

* Le regole o gli operatori non sono corretti per il risultato richiesto.
* Utilizzo errato dei contenitori nel segmento.
* Le variabili di traffico utilizzate per segmentare non sono impostate correttamente o sono scadute.
