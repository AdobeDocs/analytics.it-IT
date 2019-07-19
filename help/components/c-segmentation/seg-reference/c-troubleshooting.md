---
description: nulle
seo-description: nulle
seo-title: Risoluzione dei problemi di segmentazione
title: Risoluzione dei problemi di segmentazione
uuid: 8476 d 617-4 b 44-4 ff 2-9 b 3 a -02685 f 666 afc
translation-type: tm+mt
source-git-commit: 50069fe860d58f04df7ffe63714afeef9d3d7a28

---


# Risoluzione dei problemi di segmentazione

## Error: "Incompatible elements in this segment" {#section_B167EE10A0844E649DD7E14D0BAEDA17}

Questo errore si verifica quando si tenta di salvare un segmento nella cartella Data Warehouse in cui il segmento contiene elementi non compatibili con Data Warehouse. Per risolvere questo errore, effettuare una delle seguenti operazioni:

* Salvare il segmento in un'altra cartella
* Rimuovere o modificare le porzioni incompatibili del segmento.

## Why does my segment return no data at all? {#section_999749CBBE984142AEA49A6E68E6730A}

Motivi possibili:

* Nidificazione inversa: ad esempio, nidificazione di un contenitore Visitatore sotto un contenitore Visita.
* Il rapporto non supporta la segmentazione.
* Non sono disponibili dati che corrispondono ai criteri di segmentazione.

## Why can't I see the segment I created in the Segment Manager? {#section_BE0A0930A2694A23BB32DA71696D52CE}

Motivi possibili:

* Alcune dimensioni sono disponibili solo in Data Warehouse e non in Gestione segmenti.
* Il segmento non è compatibile con Reporting e analisi.
* Il segmento viene controllato solo per una suite di rapporti specifica.
* Un segmento condiviso potrebbe essere stato eliminato da un altro utente.
* I segmenti non potevano essere caricati a causa di un centro dati o di un problema Cache browser.
* Il segmento non è stato salvato.
* L'indirizzo IP può essere bloccato a fine utente.

## Why does the Page Data shown after applying a segment seem incorrect? {#section_B226AF69FE06463A8BC5337FDA8D4949}

Motivi possibili:

* Regole/operatori non sono corretti per il risultato richiesto.
* Applicazione di contenitori non corretta al segmento.
* Le variabili di traffico utilizzate per segmento non vengono impostate correttamente o sono scadute.

