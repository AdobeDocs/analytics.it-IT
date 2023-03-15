---
description: Risolvere i problemi relativi ai segmenti.
title: Risoluzione dei problemi di segmentazione
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---

# Risoluzione dei problemi di segmentazione

## Errore: &quot;Elementi non compatibili in questo segmento&quot; {#incompatible}

Questo errore si verifica quando si tenta di salvare un segmento nella cartella Date Warehouse in cui il segmento contiene elementi non compatibili con Data Warehouse. Per risolvere l&#39;errore, eseguire una delle operazioni seguenti:

* Salva il segmento in un’altra cartella
* Rimuovi o modifica le parti non compatibili del segmento.

## Perché il segmento non restituisce alcun dato? {#no-data}

Possibili motivi:

* Annidamento inverso: ad esempio, nidificando un contenitore Visitatore sotto un contenitore Visita.
* Il rapporto non supporta la segmentazione.
* Non ci sono dati corrispondenti ai criteri di segmentazione.

## Perché non riesco a visualizzare il segmento creato nel Gestore segmenti? {#invisible}

Possibili motivi:

* Alcune dimensioni sono disponibili solo nella Data Warehouse e non nel Gestore segmenti.
* Il segmento non è compatibile con Reports &amp; Analytics.
* Il segmento viene controllato solo per una suite di rapporti specifica.
* Un segmento condiviso potrebbe essere stato eliminato da un altro utente.
* Impossibile caricare i segmenti a causa di un problema del centro dati o della cache del browser.
* Segmento non salvato.
* L&#39;indirizzo IP potrebbe essere bloccato alla fine dell&#39;utente.

## Perché i dati della pagina visualizzati dopo l’applicazione di un segmento sembrano errati? {#page-data}

Possibili motivi:

* Le regole/operatori non sono corrette per il risultato richiesto.
* Applicazione errata dei contenitori al segmento.
* Le variabili di traffico utilizzate per segmentare non sono impostate correttamente o sono scadute.
