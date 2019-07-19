---
title: Differenze di elaborazione e architettura tra le piattaforme Analytics
description: Scopri come vengono raccolti e visualizzati in modo diverso alcuni dati tra piattaforme quali Adobe Analytics e Google Analytics.
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Differenze di elaborazione e architettura tra le piattaforme Analytics

Sebbene Adobe Analytics e Google Analytics siano entrambi strumenti Analytics, il modo in cui i dati vengono raccolti ed elaborati tra le piattaforme è molto diverso. Utilizza questa pagina per comprendere alcune delle differenze chiave in relazione alla raccolta di determinate dimensioni e metriche, e perché possono visualizzare numeri diversi in rapporti simili.

## Bounce Rate

Bounce Rate è un KPI comune utilizzato per misurare l'efficacia e la pertinenza delle pagine di destinazione nella maggior parte degli strumenti di analisi. Questo è comunemente definito come visite che entrano nel sito Web ma non include un click per un'altra pagina.

* In Adobe Analytics, Bounce Rate is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, Bounce Rate is calculated using the formula **Single-page sessions divided by Sessions**.

In entrambe le piattaforme, se più hit vengono inviati nella stessa visita o sessione, non viene considerato un rimbalzo. In Adobe Analytics, i collegamenti personalizzati sono disponibili ed è molto comune, per evitare che una visita venga conteggiata come rimbalzo. Google Analytics in genere non invia più di una richiesta dati sulla stessa pagina.

Per ottenere una migliore parità tra gli strumenti di reporting, usa la metrica Visite pagina singola in Adobe Analytics invece di Bounce come parte di una metrica calcolata. La metrica Visite pagina singola include il numero totale di visite che hanno incluso solo una visualizzazione di una pagina, o visite che entrano nel sito Web, ma non fanno clic su un clic per un'altra pagina.

See the [Bounce Rate](../../components/c-variables/c-metrics/metrics-bounce-rate.md) metric in the Components user guide for more information.

## Visite e sessioni

Le visite (note come sessioni in Google Analytics) sono un gruppo di visualizzazioni di pagina effettuate dallo stesso utente in breve tempo. Le visite su entrambe le piattaforme scadono in genere dopo 30 minuti di inattività. Entrambe le piattaforme consentono la personalizzazione quando termina una visita. Esistono diversi scenari che possono causare differenze su ogni piattaforma.

* **Fine giorno:** Tutte le sessioni in Google Analytics scadono dopo le 11:59 PM in un dato giorno. Se l'utente è ancora attivo sul sito dopo 12 AM, viene creata una nuova sessione. Adobe Analytics continua a visitare il giorno seguente come parte della stessa visita.
* **Campagne diverse:** Una nuova sessione in Google Analytics viene avviata se cambia l'origine della campagna di un utente. Se in Adobe Analytics viene visualizzato un nuovo valore del codice di tracciamento, questo viene considerato come parte della stessa visita.
* **Sostituzione manuale della sessione:** Una nuova sessione in Google Analytics inizia se utilizzate `sessionControl` per avviare o terminare manualmente una sessione. Le visite non possono essere terminate manualmente in Adobe Analytics.
* **Rilevamento delle visite aberranti in Adobe Analytics:** Una nuova visita in Adobe Analytics inizia automaticamente se un utente raggiunge 12 ore di attività continua, 2500 hit o 100 hit entro 100 secondi. Ciascuno di questi criteri di rilevamento viene generalmente attivato da un'attività bot.

See the [Visits](../../components/c-variables/c-metrics/metrics-visit.md) metric in the Components user guide for more information.
