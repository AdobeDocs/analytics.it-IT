---
description: Invia un progetto di Analysis Workspace via e-mail o programmane la consegna.
keywords: Analysis Workspace
title: Programmare progetti
feature: Curate and Share
role: User, Admin
exl-id: 2d6854f7-8954-4d55-b2be-25981cfb348b
source-git-commit: 74d4127ccb9ff2837ab5b17c8237aa4604378485
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 73%

---

# Programmare progetti

Dal **menu Share** di Workspace, puoi inviare progetti Analysis Workspace tramite e-mail a destinatari selezionati. I file possono essere inviati in formato CSV o PDF.

## Invia subito file

Per inviare immediatamente un file ai destinatari tramite e-mail:

1. Fai clic su **[!UICONTROL Share]>[!UICONTROL Send File Now]**.
1. Specifica il tipo di file (CSV o PDF).
1. (Facoltativo) Aggiungi una descrizione del file che verrà inclusa nell’e-mail.
1. Aggiungi destinatari o gruppi. È inoltre possibile inserire gli indirizzi e-mail.
1. Fai clic su **[!UICONTROL Send Now]** (Usa modello di attribuzione non predefinito).
1. (Facoltativo) Fai clic su **[!UICONTROL Show scheduling options]** per specificare una pianificazione di consegna.

![Invia subito file](assets/send-file-now.png)

## Invia file secondo programma

Per inviare un file tramite e-mail secondo una pianificazione periodica:

1. Fai clic su **[!UICONTROL Share]>[!UICONTROL Send File on Schedule]**.
1. Specifica il tipo di file (CSV o PDF).
1. (Facoltativo) Aggiungi una descrizione del file che verrà inclusa nell’e-mail.
1. Aggiungi destinatari o gruppi. È inoltre possibile inserire gli indirizzi e-mail.
1. Specifica l’intervallo per il quale la pianificazione deve essere consegnata modificando l’opzione Inizia e Termina negli input. La data di fine deve essere compresa entro un anno dal giorno in cui la pianificazione viene creata o modificata.
1. Specifica la frequenza di consegna. Ogni frequenza consente diverse personalizzazioni.
1. Fai clic su **[!UICONTROL Send on schedule]** (Usa modello di attribuzione non predefinito).

![](assets/send-on-schedule.png)

## Gestione progetti programmati

I progetti programmati di Analysis Workspace possono essere gestiti in **Analytics > Componenti > Progetti programmati**.

In Gestione progetti programmati, puoi modificare ed eliminare pianificazioni ricorrenti di progetti. Cerca una pianificazione nella barra di ricerca o utilizzando le opzioni filtro nella barra a sinistra. Puoi filtrare per tag, pianificazioni approvate, proprietari e altro ancora.

![](assets/scheduled-project-manager2.png)

| Campo | Descrizione |
| --- | --- |
| [!UICONTROL Favorites] | Selezionando l’icona a forma di stella, questa pianificazione diventa la preferita. |
| [!UICONTROL Schedule ID] | Questo ID viene utilizzato principalmente a scopo di debug. |
| [!UICONTROL Title and Description] | Titolo e descrizione del progetto. |
| [!UICONTROL Owner] | Persona che ha creato e gestisce il progetto. |
| [!UICONTROL Tags] | (facoltativo) Assegnare tag è un modo efficace per organizzare i progetti. Tutti gli utenti possono creare tag e applicarne uno o più a un progetto. Tuttavia, puoi visualizzare solo i tag dei progetti di tua proprietà o che sono stati condivisi con te. |
| [!UICONTROL Delivered To] | Destinatari del progetto pianificato. |
| [!UICONTROL Expiration Date] | Per qualsiasi frequenza di progetto pianificata, puoi impostare la data di scadenza fino a un anno nel futuro. |
| [!UICONTROL Frequency] | Con quale frequenza desideri che questo progetto di pianificazione venga inviato ai destinatari. |
| [!UICONTROL Execution Time] | A che ora del giorno viene inviato questo progetto pianificato. |
| [!UICONTROL Number of Queries] | Numero di query per questo progetto. |

## Azioni comuni

Di seguito sono riportate le azioni comuni di Gestione progetti programmati:

| Azione | Descrizione |
|---|---|
| **[!UICONTROL Edit schedule]** | Fai clic sul titolo della pianificazione per aggiornare le impostazioni di consegna. |
| **[!UICONTROL Delete schedule]** | Seleziona il progetto programmato nell’elenco, quindi fai clic su Elimina dal menu. In questo modo verrà eliminata la pianificazione selezionata per il progetto, mentre il progetto stesso non verrà eliminato. |
| **[!UICONTROL Add tags]** | Seleziona il progetto programmato nell’elenco, quindi scegli “Assegna tag” o “Approva” per organizzare le pianificazioni e semplificarne la ricerca. |
| **[!UICONTROL View failed schedules]** | Passa alla barra a sinistra > Altri filtri > Non riuscite per visualizzare le pianificazioni non riuscite. |
| **[!UICONTROL View expired schedules]** | Passa alla barra a sinistra > Altri filtri > Scadute per visualizzare le pianificazioni scadute. Fai clic sul titolo della pianificazione per impostare una nuova pianificazione di consegna. |
| **[!UICONTROL View schedule ID]** | Passa alle opzioni della colonna in alto a destra e aggiungi la colonna ID pianificazione alla tabella. L’ID pianificazione è spesso utile per il debug. |

Lo strumento di gestione dei progetti programmati mostra gli elementi creati da uno specifico utente. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte. La proprietà del progetto programmato può essere **trasferita** a un nuovo utente in **Amministratore > Utenti e risorse di Analytics > Trasferisci risorse**.
