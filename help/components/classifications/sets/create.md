---
title: Creare un set di classificazione
description: Campi e descrizioni disponibili durante la creazione di un set di classificazione.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 100%

---

# Creare un set di classificazione

Puoi utilizzare Gestione set di classificazione per creare un set di classificazione.

>[!NOTE]
>
>Questa funzione sarà disponibile per tutti i clienti che hanno eseguito la migrazione delle suite di rapporti alla nuova architettura Classificazioni. Per ulteriori informazioni, contatta l’Assistenza clienti Adobe o il tuo Account Manager.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

Quando crei un set di classificazione, sono disponibili i campi seguenti.

* **[!UICONTROL Name]**: campo di testo utilizzato per identificare il set di classificazione. Questo campo non può essere modificato al momento della creazione, ma può essere rinominato in un secondo momento.
* **[!UICONTROL Column Name]**: nome della dimensione di classificazione da creare. Questo campo è il nome della dimensione utilizzato in Analysis Workspace e il nome della colonna durante l’esportazione dei dati di classificazione.
* **[!UICONTROL Type]**: pulsanti di scelta che indicano il tipo di classificazione. Normalmente vengono utilizzate le classificazioni principali; le classificazioni di ricerca rappresentano [Sottoclassificazioni](../c-sub-classifications.md).
* **[!UICONTROL Subscriptions]**: suite di rapporti e dimensione a cui si applica questo set di classificazione. È pianificato il supporto per più suite di rapporti.

![Creare un set di classificazione](../assets/classification-set-create.png)

Se esiste un set di classificazione per una determinata suite di rapporti + variabile, la classificazione viene aggiunta allo schema.
