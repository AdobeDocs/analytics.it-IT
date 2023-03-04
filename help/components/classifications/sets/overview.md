---
title: Panoramica sui set di classificazione
description: Utilizza i set di classificazione per gestire i dati di classificazione.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 32%

---

# Panoramica sui set di classificazione

I set di classificazione forniscono un’unica interfaccia per gestire classificazioni e regole. Questo flusso di lavoro combina il concetto di creazione di classificazioni nelle impostazioni delle suite di rapporti con il concetto di Classification Importer per fornire un’interfaccia più intuitiva per creare e gestire i dati di classificazione.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]**

>[!NOTE]
>
>Questa funzione è disponibile per tutti i clienti nell’architettura del set di classificazioni. Per ulteriori informazioni, contatta l’Assistenza clienti Adobe o il team del tuo account Adobe.

L’architettura back-end rilasciata con i set di classificazione contiene diversi miglioramenti degni di nota:

* Tempo di elaborazione notevolmente ridotto (72 ore → 24 ore)
* Possibilità di utilizzare l’interfaccia utente dei set di classificazione
* L’opzione per utilizzare in futuro i dati di classificazione in Adobe Experience Platform tramite [Connettore di origine di Adobe Analytics per i dati di classificazione](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

Anche l’architettura back-end rilasciata con i set di classificazione contiene diverse modifiche di rilievo:

* Quando si utilizza il browser o l’importazione FTP, &quot;[!UICONTROL Overwrite on conflict]&#39; è sempre abilitato.
* Quando si utilizza il browser o l’importazione FTP, l’opzione per esportare immediatamente dopo l’importazione non è più supportata. Le esportazioni devono essere avviate separatamente.
* API di Analytics 2.0 `GetDimensions` l’endpoint ora restituisce identificatori stringa per le classificazioni anziché identificatori numerici. È comunque possibile utilizzare gli identificatori numerici, ma Adobe consiglia di utilizzare i nuovi identificatori stringa laddove possibile. Gli identificatori numerici possono essere recuperati utilizzando `?expansion=hidden` parametro stringa query.


I set di classificazione sono costituiti da due aree principali:

* [**[!UICONTROL Classification Sets Manager]**](set-manager.md): per creare, modificare ed eliminare i set di classificazione.
* [**[!UICONTROL Classification Set Jobs Manager]**](job-manager.md): per visualizzare lo stato dei processi del set di classificazione e scaricare i file di esportazione.
