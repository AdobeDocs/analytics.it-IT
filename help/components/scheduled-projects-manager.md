---
description: Visualizza e gestisci i rapporti pianificati in tutta l’organizzazione.
title: Gestione progetti programmati
feature: Admin Tools
source-git-commit: 8d0cf795b0366b2797fa0574ae9faaffb76b005e
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 44%

---

# Progetti programmati

I progetti programmati di Analysis Workspace possono essere gestiti in **Analytics > Componenti > Progetti programmati**.

Durante la gestione dei progetti programmati, è possibile modificare ed eliminare pianificazioni ricorrenti dei progetti. Cerca una pianificazione nella barra di ricerca o utilizzando le opzioni filtro nella barra a sinistra. Puoi filtrare per [!UICONTROL Tags], [!UICONTROL Owners], [!UICONTROL Favorites], e altro ancora.

![](assets/scheduled-project-manager2.png)

## Colonne disponibili

| Campo | Descrizione |
| --- | --- |
| [!UICONTROL Favorites] | Selezionando l’icona a forma di stella, questa pianificazione diventa la preferita. |
| [!UICONTROL Schedule ID] | Questo ID viene utilizzato principalmente a scopo di debug. |
| [!UICONTROL Title and description] | Titolo e descrizione del progetto. |
| [!UICONTROL Owner] | Persona che ha creato e gestisce il progetto. |
| [!UICONTROL Tags] | (facoltativo) Assegnare tag è un modo efficace per organizzare i progetti. Tutti gli utenti possono creare tag e applicarne uno o più a un progetto. Tuttavia, puoi visualizzare solo i tag dei progetti di tua proprietà o che sono stati condivisi con te. |
| [!UICONTROL Delivered to] | Destinatari del progetto pianificato. |
| [!UICONTROL Expiration date] | Per qualsiasi frequenza di progetto pianificata, puoi impostare la data di scadenza fino a un anno nel futuro. |
| [!UICONTROL Frequency] | Con quale frequenza desideri che questo progetto di pianificazione venga inviato ai destinatari. |
| [!UICONTROL Execution time] | A che ora del giorno viene inviato questo progetto pianificato. |
| [!UICONTROL Number of queries] | Numero di query per questo progetto. |

## Azioni comuni

Di seguito sono riportate le azioni comuni di Gestione progetti programmati:

| Azione | Descrizione |
|---|---|
| **[!UICONTROL Edit]** | Seleziona il titolo della pianificazione per aggiornarne le impostazioni di consegna. |
| **[!UICONTROL Delete]** | Seleziona il progetto programmato nell’elenco, quindi fai clic su Elimina dal menu. In questo modo verrà eliminata la pianificazione selezionata per il progetto, mentre il progetto stesso non verrà eliminato. |
| **[!UICONTROL Tag]** | Seleziona il progetto programmato nell’elenco, quindi scegli “Assegna tag” o “Approva” per organizzare le pianificazioni e semplificarne la ricerca. |
| **[!UICONTROL View failed schedules]** | Passa alla barra a sinistra > Altri filtri > Non riuscite per visualizzare le pianificazioni non riuscite. |
| **[!UICONTROL View expired schedules]** | Passa alla barra a sinistra > Altri filtri > Scadute per visualizzare le pianificazioni scadute. Fai clic sul titolo della pianificazione per impostare una nuova pianificazione di consegna. |
| **[!UICONTROL View schedule ID]** | Passa alle opzioni della colonna in alto a destra e aggiungi la colonna ID pianificazione alla tabella. L’ID pianificazione è spesso utile per il debug. |

Il manager Progetti programmati mostra gli elementi creati da un utente specifico. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte. La proprietà del progetto programmato può essere trasferita a un nuovo utente in **Amministratore** > **Utenti e risorse di Analytics** > **Trasferisci risorse**.