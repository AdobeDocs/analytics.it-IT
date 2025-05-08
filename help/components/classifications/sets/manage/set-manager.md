---
title: Gestione set di classificazione
description: Gestisci i set di classificazione in Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 9%

---

# Gestione set di classificazione

Gestione set di classificazione consente di creare, modificare o eliminare set di classificazione.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]**

I set di classificazione sono costituiti da **Sottoscrizioni** (suite di rapporti e combinazioni di dimensioni) e **Nomi di classificazione** (dimensioni contenenti dati di classificazione). Le sottoscrizioni sono configurate in [Impostazioni](settings.md), mentre i nomi delle classificazioni sono configurati in [Schema](schema.md).

## Filtrare i set di classificazione

Il lato sinistro di Gestione set di classificazione fornisce le impostazioni del filtro per individuare il set di classificazione desiderato. Facendo clic sull’icona del filtro si attiva la visibilità delle impostazioni del filtro. È possibile filtrare i set di classificazione per **[!UICONTROL Tags]** o **[!UICONTROL Report suite]**.

![Filtri per set di classificazione](../../assets/classification-set-filters.png)

Tieni presente che vengono precaricati 1.000 set di classificazione alla volta. I filtri mostrati nella barra a sinistra riflettono le opzioni per i set precaricati.

## Colonne di Gestione set di classificazione

In Gestione set di classificazione sono disponibili le colonne seguenti:

* **[!UICONTROL Classification set]**: nome del set di classificazione. Facendo clic sul nome di un set di classificazione, vengono modificate le [impostazioni](settings.md).
* **[!UICONTROL Subscriptions]**: numero di sottoscrizioni a cui si applica questo set di classificazione.
* **[!UICONTROL Classifications]**: numero di dimensioni di classificazione contenute nel set di classificazione.
* **[!UICONTROL Automated]**: determina se il set di classificazione è configurato per importare automaticamente i dati da una posizione cloud. L&#39;automazione può essere configurata nello [schema](schema.md) del set di classificazione.
* **[!UICONTROL Last Modified]**: data e ora dell&#39;ultima modifica del set di classificazione.

## Creare o modificare le opzioni

In Gestione set di classificazione sono disponibili i seguenti pulsanti:

* **[!UICONTROL Add]**: [Creare](create.md) un set di classificazione.
* **[!UICONTROL Search by title]**: cerca i set di classificazione per nome.
* **[!UICONTROL Load more]**: Gestione set di classificazione visualizza inizialmente fino a 1000 set di classificazione. Questo pulsante carica altri 1000 set di classificazione.
* **Mostra/Nascondi colonne**: attiva/disattiva la visibilità delle colonne oltre [!UICONTROL Classification set].

Seleziona uno o più set di classificazione facendo clic sulla casella di controllo accanto al set di classificazione desiderato. Quando si seleziona un set di classificazione vengono visualizzate le seguenti opzioni:

* **[!UICONTROL Tag]**: aggiungi uno o più tag ai set di classificazione selezionati, per organizzarli o raggrupparli in modo da facilitarne l&#39;individuazione in futuro.
* **[!UICONTROL Delete]**: elimina il set di classificazione. Le dimensioni di classificazione basate su questo set di classificazione non sono più disponibili. I progetti pianificati che utilizzano la serie di classificazioni eliminata continuano a utilizzare dimensioni dipendenti fino a quando non salvi nuovamente il progetto pianificato.
* **[!UICONTROL Consolidate]**: Avvia un nuovo [consolidamento](../consolidations/process.md).
* **[!UICONTROL Rename]**: rinomina il set di classificazione selezionato.
