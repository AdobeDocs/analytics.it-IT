---
title: Differenze di elaborazione e architettura tra le piattaforme Analytics
description: Scopri come alcuni dati vengono raccolti e visualizzati in modo diverso tra piattaforme quali Adobe Analytics e Google Analytics.
feature: Third-party Integration
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Differenze di elaborazione e architettura tra le piattaforme Analytics

Anche se Adobe Analytics e Google Analytics sono entrambi strumenti di Analytics, il modo in cui i dati vengono raccolti ed elaborati tra le piattaforme è molto diverso. Utilizzare questa pagina per comprendere alcune delle differenze chiave nella raccolta di determinate dimensioni e metriche e il motivo per cui potrebbero visualizzare numeri diversi in rapporti simili.

## [!UICONTROL Bounce Rate]

[!UICONTROL Bounce Rate] è un KPI comune utilizzato per aiutare a misurare l’efficacia e la rilevanza delle pagine di destinazione nella maggior parte degli strumenti di analisi. Questo viene comunemente definito come visite che accedono al sito web ma non includono un clic su un’altra pagina.

* In Adobe Analytics, [!UICONTROL Bounce Rate] viene calcolato utilizzando la formula **Rimbalzi divisi per voci**.
* Nelle Google Analytics, [!UICONTROL Bounce Rate] viene calcolato utilizzando la formula **Sessioni a pagina singola divise per sessioni**.

Su entrambe le piattaforme, se più hit vengono inviati nella stessa visita o sessione, non viene considerato un mancato recapito. In Adobe Analytics, i collegamenti personalizzati sono disponibili e abbastanza comuni, il che può impedire che una visita venga considerata un mancato recapito. In genere, Google Analytics non invia più di una richiesta di dati sulla stessa pagina.

Per ottenere una migliore parità tra gli strumenti di reporting, utilizza [!UICONTROL Single Page Visits] metrica in Adobe Analytics anziché [!UICONTROL Bounces] come parte di una metrica calcolata. Il [!UICONTROL Single Page Visits] La metrica include il numero totale di visite che includevano solo la visualizzazione di una pagina, o visite che entrano nel sito web ma non includono un clic su un’altra pagina.

Consulta la [Percentuale non recapitate](/help/components/metrics/bounce-rate.md) metrica nella guida utente dei Componenti per ulteriori informazioni.

## [!UICONTROL Visits] e sessioni

[!UICONTROL Visits] (note come sessioni nelle Google Analytics) sono un gruppo di visualizzazioni di pagina effettuate dallo stesso utente in un breve periodo di tempo. [!UICONTROL Visits] su entrambe le piattaforme in genere scadono dopo 30 minuti di inattività. Entrambe le piattaforme consentono la personalizzazione quando [!UICONTROL Visit] scade. Esistono diversi scenari che possono causare differenze su ogni piattaforma.

* **Fine del giorno:** Tutte le sessioni nelle Google Analytics scadono dopo le 23:59 di un determinato giorno. Se l’utente è ancora attivo sul sito dopo le 00:00, viene creata una nuova sessione. Adobe Analytics continua le visite al giorno successivo come parte della stessa visita.
* **Diverse campagne:** Se l’origine della campagna di un utente cambia, viene avviata una nuova sessione nelle Google Analytics. Se un nuovo [!UICONTROL Tracking Code] valore in Adobe Analytics, è considerato parte della stessa visita.
* **Sostituzione manuale della sessione:** Viene avviata una nuova sessione nelle Google Analytics se si utilizza `sessionControl` per avviare o terminare manualmente una sessione. [!UICONTROL Visits] non può essere terminato manualmente in Adobe Analytics.
* **Rilevamento di visite anomale in Adobe Analytics:** Una nuova [!UICONTROL Visit] in Adobe Analytics si avvia automaticamente se un utente raggiunge 12 ore di attività continua, 2500 hit o 100 hit entro 100 secondi. Ognuno di questi criteri di rilevamento viene in genere attivato dall’attività bot.

Consulta la [Visite](/help/components/metrics/visits.md) metrica nella guida utente dei Componenti per ulteriori informazioni.
