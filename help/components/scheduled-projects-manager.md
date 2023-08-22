---
description: Visualizza e gestisci i rapporti programmati in tutta l’organizzazione.
title: Gestione progetti programmati
feature: Admin Tools
source-git-commit: 8d0cf795b0366b2797fa0574ae9faaffb76b005e
workflow-type: ht
source-wordcount: '381'
ht-degree: 100%

---

# Progetti programmati

I progetti programmati di Analysis Workspace possono essere gestiti in **Analytics > Componenti > Progetti programmati**.

Quando gestisci i progetti programmati, puoi modificare ed eliminare le pianificazioni di progetti ricorrenti. Cerca una pianificazione nella barra di ricerca oppure utilizzando le opzioni filtro nella barra a sinistra. Puoi filtrare per [!UICONTROL Tags], [!UICONTROL Owners], [!UICONTROL Favorites] e altro ancora.

![](assets/scheduled-project-manager2.png)

## Colonne disponibili

| Campo | Descrizione |
| --- | --- |
| [!UICONTROL Favorites] | Selezionando l’icona a forma di stella, questa pianificazione diventa la preferita. |
| [!UICONTROL Schedule ID] | Questo ID viene utilizzato principalmente a scopo di debug. |
| [!UICONTROL Title and description] | Titolo e descrizione di questo progetto. |
| [!UICONTROL Owner] | La persona che ha creato ed è proprietaria del progetto. |
| [!UICONTROL Tags] | (facoltativo) Assegnare tag è un modo efficace per organizzare progetti. Tutti gli utenti possono creare tag e applicarne uno o più a un progetto. Tuttavia, puoi visualizzare solo i tag dei progetti di tua proprietà o che sono stati condivisi con te. |
| [!UICONTROL Delivered to] | Il/i destinatario/i del progetto programmato. |
| [!UICONTROL Expiration date] | Per qualsiasi frequenza di progetto programmato, puoi impostare la data di scadenza fino a un anno successivo. |
| [!UICONTROL Frequency] | Con quale frequenza desideri che questo progetto programmato venga inviato ai destinatari. |
| [!UICONTROL Execution time] | A che ora del giorno viene inviato questo progetto programmato. |
| [!UICONTROL Number of queries] | Il numero di query su questo progetto. |

## Azioni comuni

Di seguito sono riportate le azioni comuni di Gestione progetti programmati:

| Azione | Descrizione |
|---|---|
| **[!UICONTROL Edit]** | Seleziona il titolo della pianificazione per aggiornare le impostazioni di consegna. |
| **[!UICONTROL Delete]** | Seleziona il progetto programmato nell’elenco, quindi fai clic su Elimina dal menu. In questo modo verrà eliminata la pianificazione selezionata per il progetto, mentre il progetto stesso non verrà eliminato. |
| **[!UICONTROL Tag]** | Seleziona il progetto programmato nell’elenco, quindi scegli “Assegna tag” o “Approva” per organizzare le pianificazioni e semplificarne la ricerca. |
| **[!UICONTROL View failed schedules]** | Passa alla barra a sinistra > Altri filtri > Non riuscite per visualizzare le pianificazioni non riuscite. |
| **[!UICONTROL View expired schedules]** | Passa alla barra a sinistra > Altri filtri > Scadute per visualizzare le pianificazioni scadute. Fai clic sul titolo della pianificazione per impostare una nuova programmazione di consegna. |
| **[!UICONTROL View schedule ID]** | Passa alle opzioni della colonna in alto a destra e aggiungi la colonna ID pianificazione alla tabella. L’ID pianificazione è spesso utile per il debug. |

Lo strumento di gestione dei progetti programmati mostra gli elementi creati da uno specifico utente. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte. La proprietà del progetto programmato può essere trasferita a un nuovo utente selezionando **Amministratore** > **Utenti e risorse di Analytics** > **Trasferisci risorse**.