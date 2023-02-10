---
title: Panoramica sui set di classificazione
description: Utilizza i set di classificazione per gestire i dati di classificazione.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: 2ba6ffc7f632975ca16fa02ee79d467d4d53f076
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 43%

---

# Panoramica sui set di classificazione

I set di classificazione forniscono un’unica interfaccia per gestire classificazioni e regole. Questo flusso di lavoro combina il concetto di creazione di classificazioni nelle impostazioni delle suite di rapporti con il concetto di Classification Importer per fornire un’interfaccia più intuitiva per creare e gestire i dati di classificazione.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]**

>[!NOTE]
>
>I set di classificazioni saranno disponibili per tutti i clienti che hanno eseguito la migrazione delle loro suite di rapporti alla nuova architettura Classificazioni. Per ulteriori informazioni, contatta l’Assistenza clienti Adobe o il tuo Account Manager.

L’architettura di back-end rilasciata con i set di classificazione contiene diversi miglioramenti di rilievo:

* Tempi di elaborazione significativamente ridotti (72 ore → 24 ore)
* Possibilità di utilizzare l’interfaccia utente dei set di classificazioni
* L’opzione per utilizzare i dati di classificazione in Adobe Experience Platform in futuro tramite [Connettore sorgente Adobe Analytics per i dati di classificazione](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

L’architettura di back-end rilasciata con i set di classificazione contiene anche diverse modifiche di rilievo:

* Quando utilizzi il browser o l’importazione FTP, &quot;[!UICONTROL Overwrite on conflict]&#39; è sempre abilitato.
* Quando utilizzi il browser o l’importazione FTP, l’opzione per esportare immediatamente dopo l’importazione non è più supportata. Le esportazioni devono essere avviate separatamente.
* API di Analytics 2.0 `GetDimensions` endpoint restituisce ora identificatori stringa per le classificazioni anziché identificatori numerici. È ancora possibile utilizzare gli identificatori numerici, ma in Adobe si consiglia di utilizzare, ove possibile, i nuovi identificatori stringa. Gli identificatori numerici possono essere recuperati utilizzando `?expansion=hidden` parametro della stringa query.


I set di classificazione sono costituiti da due aree principali:

* [**[!UICONTROL Classification Sets Manager]**](set-manager.md): per creare, modificare ed eliminare i set di classificazione.
* [**[!UICONTROL Classification Set Jobs Manager]**](job-manager.md): per visualizzare lo stato dei processi del set di classificazione e scaricare i file di esportazione.
