---
title: Carica file origini dati in Adobe
description: Il processo di caricamento di un file di origini dati in Adobe Analytics per l’acquisizione.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Carica file origini dati in Adobe

L&#39;invio di un file origini dati ad Adobe comporta un tipico flusso di lavoro FTP autenticato. Puoi utilizzare Esplora risorse, Finder o un client FTP dedicato per caricare i file desiderati nella posizione FTP di Adobe.

Individua le credenziali FTP in [Gestione origini dati](manage.md). Ogni origine dati ha un collegamento alla relativa **[!UICONTROL FTP Info]**. Ogni posizione FTP è dedicata a tale origine dati specifica; non puoi utilizzare la stessa posizione FTP per più origini dati.

Per motivi di sicurezza, le posizioni FTP prive di attività per più di 30 giorni sono disabilitate.

## La `.fin` file

Una parte fondamentale del successo dell’acquisizione di un file origini dati è l’inclusione di un `.fin` file. Questo file indica ad Adobe che il file di dati è pronto per l’elaborazione. Se carichi un file origini dati senza che sia necessario `.fin` file, Adobe non elabora mai tali dati.

La `.fin` il file ha le seguenti proprietà:

* Il file ha un `.fin` estensione. Assicurati che il tuo sistema operativo ti consenta di vedere e modificare i tipi di file.
* Il file è vuoto. Non archiviare dati all&#39;interno del `.fin` file.
* Il file ha esattamente lo stesso nome del file origini dati. Ad esempio, se carichi un file origini dati denominato `example.txt`, `.fin` file **deve** essere denominato `example.fin`. Se non hanno un nome identico, Adobe non elabora mai il file origini dati.

Una volta che il file di origine dati e `.fin` vengono caricati sul sito FTP, Adobe elabora il file. Non caricare la `.fin` fino al caricamento completo del file delle origini dati. Se la `.fin` Il file viene caricato in modo prematuro. Adobe recupera e acquisisce il file parzialmente caricato, generando possibili errori.

## Ordine di elaborazione

Se carichi più file contemporaneamente sul sito FTP, Adobe li inserisce in ordine alfanumerico. Se l’organizzazione richiede l’acquisizione di file in un ordine specifico, accertati che i nomi dei file siano alfanumerici.

## Tempo di elaborazione

Per garantire l’elaborazione più rapida dei file, l’Adobe consiglia di aggregare i dati delle metriche in una singola riga per data. Ad esempio, questo file di origini dati, pur essendo valido, risulterebbe più lento:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` |  |  |
| `07/24/YYYY` | `red` | `1` |  |  |
| `07/24/YYYY` | `red` |  | `1` |  |
| `07/24/YYYY` | `red` |  |  | `1` |

Questo file verrebbe elaborato più velocemente, contenente gli stessi dati:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
