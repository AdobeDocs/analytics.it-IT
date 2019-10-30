---
description: Una sequenza di pagine visualizzate in una sessione. La metrica visite viene comunemente utilizzata nei rapporti che presentano il numero di sessioni utente nel corso del periodo di tempo selezionato.
keywords: visit
seo-description: Una sequenza di pagine visualizzate in una sessione. La metrica visite viene comunemente utilizzata nei rapporti che presentano il numero di sessioni utente nel corso del periodo di tempo selezionato.
seo-title: Visita
solution: Analytics
title: Visita
topic: Metriche
uuid: 91317487-f116-4546-8cd2-421418c49a7a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Visita

Una sequenza di pagine visualizzate in una sessione. La metrica visite viene comunemente utilizzata nei rapporti che presentano il numero di sessioni utente nel corso del periodo di tempo selezionato.

> [!NOTE] Per informazioni sul modo in cui vengono calcolate le visite e gli avvii delle app mobili, vedi [Confronta visite e avvii](https://helpx.adobe.com/analytics/kb/compare-visits-and-mobile-app-launches.html) delle app mobili nella Knowledge Base.

La metrica visite è sempre associata a un periodo di tempo, quindi sai se contare una nuova visita se lo stesso visitatore ritorna al tuo sito. Una sessione inizia quando l’utente arriva sul sito per la prima volta e termina in uno dei seguenti scenari:

* **** 30 minuti di inattività: Quasi tutte le sessioni terminano in questo modo. Se sono trascorsi più di 30 minuti tra le richieste di immagini, inizia una nuova visita.
* **** 12 ore di attività coerente: Se un utente attiva richieste di immagini senza un intervallo di oltre 30 minuti per 12 ore, viene automaticamente avviata una nuova visita.
* **** 2500 hit: Se un utente genera un numero elevato di hit senza avviare una nuova sessione, viene conteggiata una nuova visita dopo 2500 richieste di immagini.
* **100 hit in 100 secondi**: Se una visita è composta da più di 100 hit che si verificano in meno di 100 secondi, la visita termina automaticamente. Questo comportamento indica in genere l'attività dei bot e questa limitazione viene applicata per evitare che queste visite ad alta intensità di elaborazione aumentino la latenza e aumentino il tempo necessario per generare i report.

> [!NOTE] La definizione di visita può essere ridotta per una suite di rapporti, se espressamente richiesta, ma non può essere allungata. Chiedi a uno degli utenti supportati della tua organizzazione di contattare l'Assistenza clienti per richiedere la modifica.

Gli scenari seguenti non avviano una nuova visita:

* L'utente chiude la scheda, la riapre e torna al sito entro 30 minuti. L'utente può anche chiudere il browser o riavviare il computer e continuare a essere conteggiato come una singola visita (dato che il visitatore torna sul sito entro 30 minuti).
* Gli utenti che navigano nel sito in più schede. Anche se la navigazione con più schede non incrementa visite o visitatori, l'utilizzo di un browser separato non comporta alcun incremento. Questo perché le diverse schede fanno riferimento agli stessi cookie, mentre i browser separati no.

Una visita non coincide necessariamente con una sessione del browser. Ad esempio, se un visitatore chiude il browser, riapre il browser e accede al sito cinque minuti dopo, viene riconosciuto come continuazione della stessa visita. Questo significa anche che se un visitatore rimane su una pagina per 35 minuti, la visita sarà chiusa ed elaborata e una nuova visita inizierà se fa clic su un'altra pagina.

Al termine di una visita, tutte le variabili con scadenza visita sono scadute e non persistono più. La metrica del numero di visita verrà incrementata alla visita successiva per il visitatore.

> [!NOTE] Se utilizzi Analytics come origine di reporting per Adobe Target, fai riferimento a [Minimizing Inflated Visit and Visitor Counts in A4T (Riduzione dei conteggi delle visite e dei visitatori in A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) ) nella [!DNL Target] documentazione.

Per ulteriori informazioni, consulta [Identificazione di visitatori](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_overview.html) univoci nella guida all’implementazione di Adobe Analytics.

**Periodi di tempo**

Una visita viene segnalata in ogni periodo di tempo in cui si è verificata l'attività. Ad esempio, supponiamo che una visita inizi alle 11:45 il 1 dicembre e prosegua fino alle 12:30 il 2 dicembre. La visita è conteggiata il 1° e il 2 dicembre. Questa segnalazione si applica ad altri periodi di tempo, tra cui settimanale, mensile, trimestrale e annuale.
