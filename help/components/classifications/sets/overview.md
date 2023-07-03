---
title: Panoramica sui set di classificazione
description: Utilizza i set di classificazione per gestire i dati di classificazione.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 25%

---

# Panoramica sui set di classificazione

I set di classificazione forniscono un’unica interfaccia per gestire classificazioni e regole. Questo flusso di lavoro combina il concetto di creazione di classificazioni nelle impostazioni della suite di rapporti con il concetto di importazione di classificazioni, per fornire un’interfaccia più intuitiva per la creazione e la gestione dei dati di classificazione.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]**

L’architettura back-end rilasciata con i set di classificazione contiene diversi miglioramenti degni di nota:

* Tempo di elaborazione ridotto (72 ore → 24 ore)
* Possibilità di utilizzare l’interfaccia utente dei set di classificazione
* Opzione per utilizzare in futuro i dati di classificazione in Adobe Experience Platform tramite il [Connettore di origine di Adobe Analytics per i dati di classificazione](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=it)

Anche l’architettura back-end rilasciata con i set di classificazione contiene diverse modifiche di rilievo:

* Quando si utilizza il browser o l’importazione automatizzata, &quot;[!UICONTROL Overwrite on conflict]&#39; è sempre abilitato.
* Quando si utilizza il browser o l’importazione automatica, l’opzione per esportare immediatamente dopo l’importazione non è più supportata. Le esportazioni devono essere avviate separatamente.
* L’endpoint `GetDimensions` dell’API di Analytics 2.0 ora restituisce identificatori stringa per le classificazioni anziché identificatori numerici. È comunque possibile utilizzare gli identificatori numerici, ma Adobe consiglia di utilizzare i nuovi identificatori stringa laddove possibile. Gli identificatori numerici possono essere recuperati utilizzando il parametro `?expansion=hidden` della stringa di query.

>[!IMPORTANT]
>
>Le prestazioni dei set di classificazione dipendono principalmente dal numero di valori chiave univoci che contengono dati. L’Adobe consiglia di prestare attenzione quando si tratta di variabili che contengono un numero elevato di valori univoci. Questa attenzione si applica in particolare quando si combinano variabili provenienti da più suite di rapporti e dimensioni in un singolo set di classificazione.

I set di classificazione sono costituiti da tre aree principali:

* [**[!UICONTROL Classification sets manager]**](manage/set-manager.md): crea, modifica ed elimina i set di classificazione.
* [**[!UICONTROL Classification set jobs manager]**](job-manager.md): per visualizzare lo stato dei processi del set di classificazione e scaricare i file di esportazione.
* [**[!UICONTROL Classification set consolidations]**](consolidations/manage.md): combina più set di classificazione in un singolo set di classificazione.
