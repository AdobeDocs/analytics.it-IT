---
title: Differenze di elaborazione e architettura tra le piattaforme Analytics
description: Scopri in che modo alcuni dati vengono raccolti e visualizzati in modo diverso tra le piattaforme come Adobe Analytics e Google Analytics.
translation-type: tm+mt
source-git-commit: 6fc8145d9a94427ec942d55776b6029f7dd6f79c
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---


# Differenze di elaborazione e architettura tra le piattaforme Analytics

Sebbene Adobe Analytics e Google Analytics siano entrambi strumenti di Analytics, il modo in cui i dati vengono raccolti ed elaborati tra le piattaforme è molto diverso. Utilizzare questa pagina per comprendere alcune delle differenze chiave nella modalità di raccolta di determinate dimensioni e metriche e per quale motivo potrebbero visualizzare numeri diversi in rapporti simili.

## [!UICONTROL Bounce Rate]

[!UICONTROL Bounce Rate] è un indicatore KPI comune utilizzato per misurare l’efficacia e la pertinenza delle pagine di destinazione nella maggior parte degli strumenti di analisi. Questo è comunemente definito come visite che entrano nel sito Web ma non includono un clic su un&#39;altra pagina.

* In Adobe Analytics, [!UICONTROL Bounce Rate] viene calcolato utilizzando la formula **Bounces divisa per Entrate**.
* In Google Analytics, [!UICONTROL Bounce Rate] viene calcolato utilizzando la formula Sessioni a **pagina singola divise per Sessioni**.

In entrambe le piattaforme, se più hit vengono inviati nella stessa visita o sessione, non viene considerato un rimbalzo. In Adobe Analytics, i collegamenti personalizzati sono disponibili e abbastanza comuni, il che può impedire il conteggio di una visita come rimbalzo. Google Analytics in genere non invia più di una richiesta di dati sulla stessa pagina.

Per ottenere una migliore parità tra gli strumenti di reporting, utilizzate la [!UICONTROL Single Page Visits] metrica in Adobe Analytics invece che [!UICONTROL Bounces] come parte di una metrica calcolata. La [!UICONTROL Single Page Visits] metrica include il numero totale di visite che includevano solo una visualizzazione di pagina, o visite che entrano nel sito Web ma non includono un clic su un&#39;altra pagina.

Per ulteriori informazioni, consulta la metrica [Frequenza](/help/components/metrics/bounce-rate.md) rimbalzi nella guida utente Componenti.

## [!UICONTROL Visits] e sessioni

[!UICONTROL Visits] (note come sessioni in Google Analytics) è un gruppo di visualizzazioni di pagina effettuate dallo stesso utente in poco tempo. [!UICONTROL Visits] in entrambe le piattaforme generalmente scadono dopo 30 minuti di inattività. Entrambe le piattaforme consentono la personalizzazione alla [!UICONTROL Visit] scadenza. Esistono diversi scenari che possono causare differenze su ciascuna piattaforma.

* **Fine giornata:** Tutte le sessioni in Google Analytics scadono dopo le 11:59 di un dato giorno. Se l’utente è ancora attivo sul sito dopo le 12:00, viene creata una nuova sessione. Adobe Analytics continua a visitare il giorno successivo come parte della stessa visita.
* **Campagne diverse:** Una nuova sessione in Google Analytics viene avviata se l&#39;origine della campagna dell&#39;utente cambia. Se un nuovo [!UICONTROL Tracking Code] valore viene visualizzato in Adobe Analytics, viene considerato parte della stessa visita.
* **Ignoramento sessione manuale:** Una nuova sessione in Google Analytics viene avviata se utilizzate `sessionControl` per avviare o terminare manualmente una sessione. [!UICONTROL Visits] non può essere terminata manualmente in Adobe Analytics.
* **Rilevamento di visite in Adobe Analytics:** Una nuova funzione [!UICONTROL Visit] in Adobe Analytics viene avviata automaticamente se un utente raggiunge 12 ore di attività continua, 2500 o 100 hit entro 100 secondi. Ciascuno di questi criteri di rilevamento viene in genere attivato dall&#39;attività bot.

Per ulteriori informazioni, consulta la metrica [Visite](/help/components/metrics/visits.md) nella guida utente Componenti.
