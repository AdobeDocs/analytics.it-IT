---
title: Differenze di elaborazione e architettura tra le piattaforme Analytics
description: Scopri come alcuni dati vengono raccolti e visualizzati in modo diverso tra piattaforme come Adobe Analytics e Google Analytics.
feature: Third-party Integration
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Differenze di elaborazione e architettura tra le piattaforme Analytics

Sebbene Adobe Analytics e Google Analytics siano entrambi strumenti di Analytics, il modo in cui i dati vengono raccolti ed elaborati tra le piattaforme è molto diverso. Usa questa pagina per comprendere alcune delle differenze chiave nella raccolta di determinate dimensioni e metriche e per quale motivo potrebbero visualizzare numeri diversi in rapporti simili.

## [!UICONTROL Bounce Rate]

[!UICONTROL Bounce Rate] è un KPI comune utilizzato per misurare l’efficacia e la pertinenza delle pagine di destinazione nella maggior parte degli strumenti di analisi. Questa è comunemente definita come visite che entrano nel sito web ma non includono un clic su un’altra pagina.

* In Adobe Analytics, [!UICONTROL Bounce Rate] è calcolato utilizzando la formula **Rimbalzi divisi per voci**.
* In Google Analytics, [!UICONTROL Bounce Rate] è calcolato utilizzando la formula **Sessioni a pagina singola divise per sessioni**.

Su entrambe le piattaforme, se più hit vengono inviati nella stessa visita o sessione, non viene considerato un messaggio non recapitato. In Adobe Analytics, i collegamenti personalizzati sono disponibili e abbastanza comuni per impedire il conteggio di una visita come rimbalzo. Google Analytics in genere non invia più di una richiesta di dati sulla stessa pagina.

Per ottenere una migliore parità tra gli strumenti di reporting, utilizza [!UICONTROL Single Page Visits] in Adobe Analytics anziché [!UICONTROL Bounces] come parte di una metrica calcolata. La [!UICONTROL Single Page Visits] Questa metrica include il numero totale di visite che includevano solo una visualizzazione di pagina o visite che accedono al sito web ma non includono un clic su un’altra pagina.

Consulta la sezione [Frequenza di rimbalzo](/help/components/metrics/bounce-rate.md) nella guida utente Componenti per ulteriori informazioni.

## [!UICONTROL Visits] e sessioni

[!UICONTROL Visits] (dette sessioni in Google Analytics) sono un gruppo di visualizzazioni di pagina effettuate dallo stesso utente in un breve periodo di tempo. [!UICONTROL Visits] in entrambe le piattaforme generalmente scadono dopo 30 minuti di inattività. Entrambe le piattaforme consentono la personalizzazione quando un [!UICONTROL Visit] scade. Esistono diversi scenari che possono causare differenze su ciascuna piattaforma.

* **Fine del giorno:** Tutte le sessioni nelle Google Analytics scadono dopo le 23:59 di un giorno determinato. Se l’utente è ancora attivo sul sito dopo le 12, viene creata una nuova sessione. Adobe Analytics continua le visite al giorno successivo come parte della stessa visita.
* **Campagne diverse:** Viene avviata una nuova sessione in Google Analytics se l’origine di una campagna dell’utente cambia. Se una nuova [!UICONTROL Tracking Code] viene visualizzato in Adobe Analytics, viene considerato parte della stessa visita.
* **Sostituzione manuale della sessione:** Viene avviata una nuova sessione in Google Analytics se utilizzi `sessionControl` per avviare o terminare manualmente una sessione. [!UICONTROL Visits] non può essere terminato manualmente in Adobe Analytics.
* **Rilevamento di visite in precedenza in Adobe Analytics:** Nuovo [!UICONTROL Visit] in Adobe Analytics viene avviato automaticamente se un utente raggiunge 12 ore di attività continua, 2500 hit o 100 hit in 100 secondi. Ognuno di questi criteri di rilevamento viene in genere attivato dall’attività bot.

Consulta la sezione [Visite](/help/components/metrics/visits.md) nella guida utente Componenti per ulteriori informazioni.
