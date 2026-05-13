---
title: Differenze di elaborazione e architettura tra le piattaforme Analytics
description: Scopri come alcuni dati vengono raccolti e visualizzati in modo diverso tra piattaforme quali Adobe Analytics e Google Analytics.
feature: Third-party Integration
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
TQID: https://experienceleague.adobe.com/pL36oKany2sKuJrEn4-oIja3O91PZ47YQGoNvhdt6y8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 480
ht-degree: 0%

---

# Differenze di elaborazione e architettura tra le piattaforme Analytics

Anche se Adobe Analytics e Google Analytics sono entrambi strumenti di Analytics, il modo in cui i dati vengono raccolti ed elaborati tra le piattaforme è molto diverso. Utilizzare questa pagina per comprendere alcune delle differenze chiave nella raccolta di determinate dimensioni e metriche e il motivo per cui potrebbero visualizzare numeri diversi in rapporti simili.

## [!UICONTROL Bounce Rate]

[!UICONTROL Bounce Rate] è un KPI comune utilizzato per aiutare a misurare l&#39;efficacia e la rilevanza delle pagine di destinazione nella maggior parte degli strumenti di analisi. Questo viene comunemente definito come visite che accedono al sito web ma non includono un clic su un’altra pagina.

* In Adobe Analytics, [!UICONTROL Bounce Rate] viene calcolato utilizzando la formula **Rimbalzi divisi per Voci**.
* In Google Analytics, [!UICONTROL Bounce Rate] viene calcolato utilizzando la formula **Sessioni a pagina singola divise per Sessioni**.

Su entrambe le piattaforme, se più hit vengono inviati nella stessa visita o sessione, non viene considerato un mancato recapito. In Adobe Analytics, i collegamenti personalizzati sono disponibili e abbastanza comuni, il che può impedire che una visita venga considerata un mancato recapito. In genere, Google Analytics non invia più di una richiesta di dati sulla stessa pagina.

Per ottenere una migliore parità tra gli strumenti di reporting, utilizza la metrica [!UICONTROL Single Page Visits] in Adobe Analytics invece di [!UICONTROL Bounces] come parte di una metrica calcolata. La metrica [!UICONTROL Single Page Visits] include il numero totale di visite che includono solo la visualizzazione di una pagina o le visite che entrano nel sito Web ma non includono un clic su un&#39;altra pagina.

Per ulteriori informazioni, consulta la metrica [Percentuale non recapitate](/help/components/metrics/bounce-rate.md) nella guida utente dei Componenti.

## [!UICONTROL Visits] e sessioni

[!UICONTROL Visits] (note come sessioni in Google Analytics) sono un gruppo di visualizzazioni di pagina effettuate dallo stesso utente in un breve periodo di tempo. [!UICONTROL Visits] su entrambe le piattaforme in genere scadono dopo 30 minuti di inattività. Entrambe le piattaforme consentono la personalizzazione alla scadenza di [!UICONTROL Visit]. Esistono diversi scenari che possono causare differenze su ogni piattaforma.

* **Fine del giorno:** Tutte le sessioni in Google Analytics scadono dopo le 23:00:59 di un determinato giorno. Se l’utente è ancora attivo sul sito dopo le 00:00, viene creata una nuova sessione. Adobe Analytics continua le visite al giorno successivo come parte della stessa visita.
* **Campagne diverse:** Se l&#39;origine della campagna di un utente cambia, viene avviata una nuova sessione in Google Analytics. Se un nuovo valore [!UICONTROL Tracking Code] viene visualizzato in Adobe Analytics, viene considerato parte della stessa visita.
* **Sostituzione manuale della sessione:** Se si utilizza `sessionControl` per avviare o terminare manualmente una sessione, verrà avviata una nuova sessione in Google Analytics. Impossibile terminare manualmente [!UICONTROL Visits] in Adobe Analytics.
* **Rilevamento di visite in modo anomalo in Adobe Analytics:** Un nuovo [!UICONTROL Visit] in Adobe Analytics si avvia automaticamente se un utente raggiunge 12 ore di attività continua, 2500 o 100 hit entro 100 secondi. Ognuno di questi criteri di rilevamento viene in genere attivato dall’attività bot.

Per ulteriori informazioni, consulta la metrica [Visite](/help/components/metrics/visits.md) nella guida utente dei Componenti.
