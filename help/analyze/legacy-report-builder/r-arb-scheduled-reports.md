---
description: Scopri le descrizioni dei campi per Gestione attività pianificata.
title: Informazioni su Gestione attività pianificata
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
TQID: https://experienceleague.adobe.com/bH-sAinp0Hf0X9qesfrJMIUYdDqjrev5Hd7mRpihDLM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 755
ht-degree: 18%

---

# Attività programmate Manager

{{legacy-arb}}

[!UICONTROL Scheduled Task Manager] ti consente di visualizzare un elenco dei rapporti pianificati esistenti, insieme ai relativi destinatari, dettagli sulla pianificazione e formati di file. Consente inoltre di riattivare le cartelle di lavoro pianificate che non sono state eseguite.

## Sospensione delle attività pianificate meno recenti

Il 21 aprile 2022 sono state implementate modifiche alle attività pianificate in Report Builder nell’ambito delle attività di ottimizzazione delle prestazioni e della consegna. Tali modifiche includevano l&#39;eliminazione della possibilità che le consegne programmate “terminassero dopo x eventi”. In risposta a diverse richieste dei clienti che necessitano di più tempo per esplorare e implementare alternative, abbiamo deciso di ripristinare questa opzione in modo limitato fino al **31 gennaio 2023**.

Continuerai a pianificare attività Report Builder orarie e a farle terminare dopo un massimo di 99 occorrenze. Tieni presente che il rollback si applica solo alle attività orarie; l’opzione “termina dopo x eventi” rimarrà non disponibile per tutti gli altri intervalli di consegna (giornalieri, settimanali, mensili e annuali).

Tieni presente che questa opzione viene ritirata dal 31 gennaio 2023.
Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe.

In particolare, questa pausa si applica a **qualsiasi attività creata prima del 31 gennaio 2020**. Non verranno eliminate attività, cartelle di lavoro o dati. Le attività più vecchie di due anni verranno sospese e non verranno inviate altre attività pianificate.

Tutte le attività che desideri riprendere l’invio possono essere riattivate. Accedere a Report Builder e avviare [!UICONTROL Scheduled Task Manager]. Fare clic su **[!UICONTROL Reactivate]** per l&#39;attività pianificata che si desidera riprendere l&#39;invio. Le attività riattivate avranno una scadenza predefinita di 18 mesi, a meno che non venga scelta una data di scadenza più breve.

Inoltre, qualsiasi attività con una data di creazione inferiore a due anni e senza data di scadenza corrente (o con una data di scadenza superiore a due anni) avrà una data di scadenza predefinita di 18 mesi. La nuova data di scadenza sarà il lunedì 15 ottobre 2023. Puoi modificare questa data di scadenza affinché sia inferiore a 18 mesi, ma non superiore. Al momento della scadenza, l’attività verrà sospesa. È tuttavia possibile riattivare l&#39;attività con una nuova data di scadenza di 18 mesi. Non verranno eliminate attività, cartelle di lavoro o dati.

Lo scopo di questa pausa è gestire e gestire in modo efficace il database delle attività pianificate per garantire prestazioni e consegna ottimali per le attività e le cartelle di lavoro necessarie. Ciò servirà come evoluzione della nostra nuova politica di governance. Dopo il 31 gennaio 2023, tutte le attività avranno una scadenza massima di 18 mesi. Dopo 18 mesi, le attività scadute verranno sospese e potranno essere riattivate in base alle esigenze.

## Configurare le attività pianificate

| Campo | Descrizione |
| --- | --- |
| **[!UICONTROL Scheduled Reports tab]** | |
| [!UICONTROL Report Name] | Indica il nome dell&#39;attività pianificata. |
| [!UICONTROL Email/FTP] | L’indirizzo e-mail o FTP del destinatario. **Nota:** se è selezionata l&#39;opzione E-mail, i report di dimensioni superiori a 1 MB vengono automaticamente allegati all&#39;e-mail come file .zip. Questa funzione consente di mantenere le dimensioni del file allegato ridotte e non può essere disabilitata. |
| [!UICONTROL Publishing Options] | In questa colonna verrà elencato Power BI se è selezionata una delle [opzioni di pubblicazione di Power BI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md). |
| [!UICONTROL Schedule] | Tipo di consegna pianificata. |
| [!UICONTROL File Format] | Il formato di consegna del rapporto, ad esempio Excel, PDF, HTML e così via. |
| [!UICONTROL Reactivate] | Quando una cartella di lavoro pianificata non viene eseguita correttamente, Report Builder tenta di eseguirla altre due volte ogni quindici minuti. Dopo tre tentativi falliti, Report Builder disattiva la pianificazione e visualizza il pulsante Riattiva. Quando riattivi una cartella di lavoro, la consegna pianificata viene riavviata dal momento in cui è stata disattivata.<p>Ad esempio, se una cartella di lavoro pianificata è stata disattivata 14 giorni fa e viene riattivata oggi, viene eseguita per ogni giorno mancante e verrà consegnata 14 volte. Se non si desidera che la cartella di lavoro venga consegnata per i giorni mancanti, è possibile eliminare la cartella di lavoro pianificata e quindi crearne una nuova utilizzando gli stessi parametri di pianificazione.<p>**Nota:** non riattivare una cartella di lavoro se non si conosce il motivo per cui è stata disattivata dal sistema. Per risolvere i problemi, scaricare una cartella di lavoro disattivata e aggiornarla sul lato client. Se non vengono visualizzati errori, dovrebbe essere possibile riattivarli. |
| [!UICONTROL Last sent] | La data e l’ora dell’ultimo invio del rapporto. |
| **Scheda Destinatario** | |
| [!UICONTROL Recipient email] | Il destinatario e-mail del rapporto. |
| [!UICONTROL Reports] | I rapporti inviati a ciascun destinatario. |
| **Scheda Cronologia report** | |
| [!UICONTROL File Name] | Indica il nome dell&#39;attività pianificata. |
| [!UICONTROL Date] | La data e l’ora dell’ultimo invio del rapporto. |
| [!UICONTROL Status] | Lo stato indica se il report è stato inviato o meno. |
| [!UICONTROL Email/FTP] | L’indirizzo e-mail o FTP del destinatario del rapporto. |
| [!UICONTROL File Format] | Il formato di consegna del rapporto, ad esempio Excel, PDF, HTML e così via. |
