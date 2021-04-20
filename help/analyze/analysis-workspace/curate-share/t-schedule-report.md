---
description: Invia un progetto di Analysis Workspace via e-mail o programmane la consegna.
keywords: Analysis Workspace
title: Programmare progetti
feature: Curate and Share
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 98%

---


# Programmare progetti

Dal **menu Share** di Workspace, puoi inviare progetti Analysis Workspace tramite e-mail a destinatari selezionati. I file possono essere inviati in formato CSV o PDF.

## Invia subito file

Per inviare immediatamente un file ai destinatari tramite e-mail:

1. Fai clic su **Condividi > Invia subito file**.
1. Specifica il tipo di file (CSV o PDF).
1. (Facoltativo) Aggiungi una descrizione del file che verrà inclusa nell’e-mail.
1. Aggiungi destinatari o gruppi. È inoltre possibile inserire gli indirizzi e-mail.
1. Fai clic su **Invia subito**.
1. (Facoltativo) Fai clic su **Mostra opzioni di pianificazione** per specificare la pianificazione della consegna.

![Invia subito file](assets/send-file-now.png)

## Invia file secondo programma

Per inviare un file tramite e-mail secondo una pianificazione periodica:

1. Fai clic su **Condividi > Invia file secondo programma**.
1. Specifica il tipo di file (CSV o PDF).
1. (Facoltativo) Aggiungi una descrizione del file che verrà inclusa nell’e-mail.
1. Aggiungi destinatari o gruppi. È inoltre possibile inserire gli indirizzi e-mail.
1. Specifica l’intervallo per il quale la pianificazione deve essere consegnata modificando l’opzione Inizia e Termina negli input. La data di fine deve essere compresa entro un anno dal giorno in cui la pianificazione viene creata o modificata.
1. Specifica la frequenza di consegna. Ogni frequenza consente diverse personalizzazioni.
1. Fai clic su **Invia secondo programma**.

![](assets/send-on-schedule.png)

## Gestione progetti programmati

I progetti programmati di Analysis Workspace possono essere gestiti in **Analytics > Componenti > Progetti programmati**.

In Gestione progetti programmati, puoi modificare ed eliminare pianificazioni ricorrenti di progetti. Cerca una pianificazione nella barra di ricerca o utilizzando le opzioni filtro nella barra a sinistra. Puoi filtrare per tag, pianificazioni approvate, proprietari e altro ancora.

![](assets/scheduled-project-manager.png)

Di seguito sono riportate le azioni comuni di Gestione progetti programmati:

| Azione | Descrizione |
|---|---|
| **Modifica pianificazione** | Fai clic sul titolo della pianificazione per aggiornare le impostazioni di consegna. |
| **Elimina pianificazione** | Seleziona il progetto programmato nell’elenco, quindi fai clic su Elimina dal menu. In questo modo verrà eliminata la pianificazione selezionata per il progetto, mentre il progetto stesso non verrà eliminato. |
| **Aggiungi tag** | Seleziona il progetto programmato nell’elenco, quindi scegli “Assegna tag” o “Approva” per organizzare le pianificazioni e semplificarne la ricerca. |
| **Visualizza pianificazioni non riuscite** | Passa alla barra a sinistra > Altri filtri > Non riuscite per visualizzare le pianificazioni non riuscite. |
| **Visualizza pianificazioni scadute** | Passa alla barra a sinistra > Altri filtri > Scadute per visualizzare le pianificazioni scadute. Fai clic sul titolo della pianificazione per impostare una nuova pianificazione di consegna. |
| **Visualizza ID pianificazione** | Passa alle opzioni della colonna in alto a destra e aggiungi la colonna ID pianificazione alla tabella. L’ID pianificazione è spesso utile per il debug. |

Lo strumento di gestione dei progetti programmati mostra gli elementi creati da uno specifico utente. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte. La proprietà del progetto programmato può essere **trasferita** a un nuovo utente in **Amministratore > Utenti e risorse di Analytics > Trasferisci risorse**.
