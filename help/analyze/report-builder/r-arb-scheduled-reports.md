---
description: Descrizioni dei campi per Gestione attività pianificata.
title: Attività programmate Manager
uuid: dec259f0-2a04-4c94-abbc-5008cf2f1cb8
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 5%

---

# Attività programmate Manager

Gestione attività pianificata consente di visualizzare un elenco dei rapporti pianificati esistenti, nonché dei relativi destinatari, dettagli della pianificazione e formati di file. Consente inoltre di riattivare le cartelle di lavoro pianificate non eseguite.

| Campo | Descrizione |
| --- | --- |
| **Scheda Rapporti pianificati** |  |
| Nome del rapporto | Indica il nome dell&#39;attività pianificata. |
| E-mail/FTP | Indirizzo e-mail o FTP del destinatario. **Nota:** se è selezionata l’opzione e-mail, i rapporti di dimensioni superiori a 1 MB vengono automaticamente allegati all’e-mail come file .zip. Questa funzione consente di mantenere le dimensioni ridotte del file allegato e non può essere disabilitata. |
| Opzioni di pubblicazione | Questa colonna elenca i Power BI se è selezionata una delle [opzioni di pubblicazione Power BI](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html). |
| Pianificazione | Tipo di consegna pianificata. |
| Formato file | Il formato di consegna del rapporto, ad esempio Excel, PDF, HTML e così via. |
| Riattiva | Quando una cartella di lavoro pianificata non viene eseguita, il Report Builder tenta di eseguire la cartella di lavoro due volte ogni quindici minuti. Dopo tre tentativi non riusciti, il Report Builder disattiva la pianificazione e visualizza il pulsante Riattiva . Quando si riattiva una cartella di lavoro, la consegna pianificata viene riavviata dal momento in cui è stata disattivata.  Ad esempio, se una cartella di lavoro pianificata è stata disattivata 14 giorni fa e la riattiva oggi, viene eseguita per ogni giorno mancante e verrà consegnata 14 volte. Se non si desidera che la cartella di lavoro venga consegnata per i giorni mancanti, è possibile eliminare la cartella di lavoro pianificata e quindi creare una nuova cartella di lavoro pianificata utilizzando gli stessi parametri di pianificazione.   Nota:  È consigliabile non riattivare una cartella di lavoro a meno che non si conosca il motivo per cui è stata disattivata dal sistema. Una soluzione per la risoluzione dei problemi consiste nel scaricare una cartella di lavoro disattivata e aggiornarla sul lato client. Se non viene visualizzato alcun errore, è necessario essere in grado di riattivarlo. |
| Ultimo invio | Data e ora dell’ultimo invio del rapporto. |
| **Scheda Destinatario** |  |
| Indirizzo e-mail del destinatario | Il destinatario e-mail del rapporto. |
| Rapporti | Report/i inviati a ciascun destinatario. |
| **Scheda Cronologia rapporti** |  |
| Nome file | Indica il nome dell&#39;attività pianificata. |
| Data | Data e ora dell’ultimo invio del rapporto. |
| Stato | Lo stato indica se il rapporto è stato inviato o meno. |
| E-mail/FTP | Indirizzo e-mail o FTP del destinatario del rapporto. |
| Formato file | Il formato di consegna del rapporto, ad esempio Excel, PDF, HTML e così via. |
