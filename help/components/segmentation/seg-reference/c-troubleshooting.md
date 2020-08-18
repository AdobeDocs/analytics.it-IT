---
description: 'null'
title: Risoluzione dei problemi di segmentazione
uuid: 8476d617-4b44-4ff2-9b3a-02685f666afc
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---


# Risoluzione dei problemi di segmentazione

## Errore: &quot;Elementi non compatibili in questo segmento&quot; {#section_B167EE10A0844E649DD7E14D0BAEDA17}

Questo errore si verifica quando si tenta di salvare un segmento nella cartella di Data Warehouse in cui il segmento contiene elementi non compatibili con la Data Warehouse. Per risolvere questo errore, eseguire una delle due operazioni seguenti:

* Salva il segmento in un’altra cartella
* Rimuovere o modificare le parti incompatibili del segmento.

## Perché il mio segmento non restituisce alcun dato? {#section_999749CBBE984142AEA49A6E68E6730A}

Possibili motivi:

* Inverti nidificazione - ad esempio, nidificazione di un contenitore Visitatore sotto un contenitore Visita.
* Il rapporto non supporta la segmentazione.
* Nessun dato corrispondente ai criteri di segmentazione.

## Perché non riesco a visualizzare il segmento creato in Segment Manager? {#section_BE0A0930A2694A23BB32DA71696D52CE}

Possibili motivi:

* Alcune dimensioni sono disponibili solo nella Data Warehouse e non in Segment Manager.
* Il segmento non è compatibile con Reporting e analisi.
* Il segmento viene controllato solo per una suite di rapporti specifica.
* Un segmento condiviso potrebbe essere stato eliminato da un altro utente.
* Impossibile caricare i segmenti a causa di un problema del centro dati o della cache del browser.
* Il segmento non è stato salvato.
* L&#39;indirizzo IP può essere bloccato alla fine dell&#39;utente.

## Perché i dati pagina visualizzati dopo l’applicazione di un segmento sembrano errati? {#section_B226AF69FE06463A8BC5337FDA8D4949}

Possibili motivi:

* Regole/Operatori non corretti per il risultato richiesto.
* Applicazione errata dei contenitori al segmento.
* Le variabili di traffico utilizzate per segmentare non sono impostate correttamente o sono scadute.

