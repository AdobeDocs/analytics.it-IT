---
title: Gestione set di classificazione
description: Gestisci i set di classificazione in Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
source-git-commit: 496b4891d447ed9dd091a6498a792146a2d5aceb
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 7%

---

# Gestione set di classificazione

Gestione set di classificazione consente di creare, modificare o eliminare set di classificazione.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]**

I set di classificazione sono costituiti da **Iscrizioni** (combinazioni di suite di rapporti e dimensioni) e **Nomi di classificazione** (dimensioni contenenti i dati di classificazione). Gli abbonamenti sono configurati in [Impostazioni](settings.md), mentre i nomi delle classificazioni sono configurati in [Schema](schema.md).

## Filtrare i set di classificazione

Il lato sinistro di Gestione set di classificazione fornisce le impostazioni del filtro per individuare il set di classificazione desiderato. Facendo clic sull’icona del filtro si attiva la visibilità delle impostazioni del filtro. Puoi filtrare i set di classificazione per **[!UICONTROL Tags]**, **[!UICONTROL Report suite]**, o **[!UICONTROL Owner]**.

![Filtri per set di classificazione](../../assets/classification-set-filters.png)

## Colonne di Gestione set di classificazione

In Gestione set di classificazione sono disponibili le colonne seguenti:

* **[!UICONTROL Classification set]**: nome del set di classificazione. Fare clic sul nome di un set di classificazione [modifica le impostazioni](settings.md).
* **[!UICONTROL Subscriptions]**: numero di abbonamenti a cui si applica questo set di classificazione.
* **[!UICONTROL Owner]**: proprietario del set di classificazione.
* **[!UICONTROL Classifications]**: numero di dimensioni di classificazione contenute nel set di classificazione.
* **[!UICONTROL Automated]**: determina se il set di classificazione è configurato per importare automaticamente i dati da una posizione cloud. L’automazione può essere configurata nei del set di classificazione [schema](schema.md).
* **[!UICONTROL Last Modified]**: data e ora dell’ultima modifica del set di classificazione.

## Creare o modificare le opzioni

In Gestione set di classificazione sono disponibili i seguenti pulsanti:

* **[!UICONTROL Add]**: [Crea](create.md) un set di classificazione.
* **[!UICONTROL Search by title]**: cerca i set di classificazione per nome.
* **[!UICONTROL Load more]**: gestione set di classificazione visualizza inizialmente fino a 1000 set di classificazione. Questo pulsante carica altri 1000 set di classificazione.
* **Mostra/Nascondi colonne**: attiva/disattiva la visibilità delle colonne oltre [!UICONTROL Classification set].

Seleziona uno o più set di classificazione facendo clic sulla casella di controllo accanto al set di classificazione desiderato. Quando si seleziona un set di classificazione vengono visualizzate le seguenti opzioni:

* **[!UICONTROL Tag]**: aggiungi uno o più tag ai set di classificazione selezionati, per organizzarli o raggrupparli in modo da facilitarne l’individuazione in futuro.
* **[!UICONTROL Delete]**: elimina il set di classificazione. Le dimensioni di classificazione basate su questo set di classificazione non sono più disponibili. I progetti pianificati che utilizzano la serie di classificazioni eliminata continuano a utilizzare dimensioni dipendenti fino a quando non salvi nuovamente il progetto pianificato.
* **[!UICONTROL Consolidate]**: avvia un nuovo [consolidamento](../consolidations/process.md).
* **[!UICONTROL Rename]**: rinomina il set di classificazione selezionato.
