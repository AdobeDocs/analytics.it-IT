---
title: Carica file origini dati in Adobe
description: Processo per caricare un file di origini dati in Adobe Analytics per l’acquisizione.
exl-id: 64e3cd70-b511-4c4e-abd0-94eb36bc3519
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Carica file origini dati in Adobe

L’invio di un file di origini dati a Adobe comporta un tipico flusso di lavoro FTP autenticato. È possibile utilizzare Esplora risorse, Finder o un client FTP dedicato per caricare i file desiderati nel percorso FTP di Adobe.

Individua le credenziali FTP in [Gestione origini dati](manage.md). Ogni origine dati ha un collegamento al relativo **[!UICONTROL FTP Info]**. Ogni posizione FTP è dedicata a quella specifica origine dati; non è possibile utilizzare la stessa posizione FTP per più origini dati.

Per motivi di sicurezza, le posizioni FTP prive di attività per più di 30 giorni sono disabilitate.

## Il `.fin` file

Una parte fondamentale per la corretta acquisizione di un file di origini dati è l’inclusione di un `.fin` file. Questo file indica ad Adobe che il file di dati è pronto per l’elaborazione. Se carichi un file di origini dati senza un corrispondente `.fin` file, Adobe non elabora mai tali dati.

Il `.fin` il file ha le seguenti proprietà:

* Il file ha un `.fin` estensione. Verificare che il sistema operativo in uso consenta di visualizzare e modificare i tipi di file.
* File vuoto. Non memorizzare dati all&#39;interno del `.fin` file.
* Il file ha lo stesso nome del file delle origini dati. Ad esempio, se carichi un file di origini dati denominato `example.txt`, il `.fin` file **deve** essere denominato `example.fin`. Se non sono denominati in modo identico, Adobe non elabora mai il file delle origini dati.

Una volta che sia il file di origine dati che `.fin` vengono caricati sul sito FTP, Adobe elabora il file. Non caricare `.fin` fino al completamento del caricamento del file origini dati. Se il `.fin` il file viene caricato in modo prematuro, Adobe recupera e acquisisce il file parzialmente caricato, generando possibili errori.

## Ordine di elaborazione

Se carichi più file contemporaneamente sul sito FTP, Adobe li acquisisce in ordine alfanumerico. Se l’organizzazione richiede l’acquisizione dei file in un ordine specifico, assicurati che i nomi dei file siano denominati in modo alfanumerico.

## Tempo di elaborazione

Per garantire l’elaborazione più rapida dei file, l’Adobe consiglia di aggregare i dati delle metriche in una singola riga per data. Ad esempio, questo file di origini dati, anche se valido, verrebbe elaborato più lentamente:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | | `1` | |
| `07/24/YYYY` | `red` | | | `1` |

Questo file verrebbe elaborato più velocemente, e contiene gli stessi dati:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
