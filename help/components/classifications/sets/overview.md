---
title: Panoramica sui set di classificazione
description: Utilizza i set di classificazione per gestire i dati di classificazione.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 85%

---

# Panoramica sui set di classificazione

I set di classificazione forniscono un’unica interfaccia per gestire classificazioni e regole. Questo flusso di lavoro combina il concetto di creazione di classificazioni nelle impostazioni delle suite di rapporti con il concetto di Importazione classificazioni per fornire un’interfaccia più intuitiva per creare e gestire i dati di classificazione.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]**

Per visualizzare questa voce di menu è necessario essere amministratore di prodotto o appartenere a un profilo di prodotto contenente l&#39;elemento di autorizzazione [!UICONTROL Report Suite Tools] > [!UICONTROL Classifications]. Si noti che mentre le precedenti interfacce di gestione delle classificazioni sono nel menu [!UICONTROL Admin], i set di classificazione sono nel menu [!UICONTROL Components].

## Miglioramenti

L’architettura back-end rilasciata con i set di classificazione contiene diversi miglioramenti degni di nota:

* Tempo di elaborazione ridotto (72 ore → 24 ore)
* Un’interfaccia utente riprogettata per gestire le classificazioni
* Opzione per utilizzare in futuro i dati di classificazione in Adobe Experience Platform tramite il [connettore di origine di Adobe Analytics per i dati di classificazione](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/classifications)

Anche l’architettura back-end rilasciata con i set di classificazione contiene diverse modifiche di rilievo:

* Quando si utilizza il browser o l’importazione automatizzata, “[!UICONTROL Overwrite on conflict]” è sempre abilitato.
* Quando si utilizza il browser o l’importazione automatizzata, l’opzione per esportare immediatamente dopo l’importazione non è più supportata. Le esportazioni devono essere avviate separatamente.
* L’endpoint `GetDimensions` dell’API di Analytics 2.0 ora restituisce identificatori stringa per le classificazioni anziché identificatori numerici. È comunque possibile utilizzare gli identificatori numerici, ma Adobe consiglia di utilizzare i nuovi identificatori stringa laddove possibile. Gli identificatori numerici possono essere recuperati utilizzando il parametro `?expansion=hidden` della stringa di query.

>[!IMPORTANT]
>
>Le prestazioni dei set di classificazione dipendono principalmente dal numero di valori chiave univoci che contengono dati. Adobe consiglia di prestare attenzione quando si tratta di variabili che contengono un numero elevato di valori univoci. Ciò vale soprattutto quando si combinano variabili provenienti da più suite di rapporti e dimensioni in un singolo set di classificazione.

I set di classificazione sono costituiti da tre aree principali:

* [**[!UICONTROL Classification sets manager]**](manage/set-manager.md): per creare, modificare ed eliminare i set di classificazione.
* [**[!UICONTROL Classification set jobs manager]**](job-manager.md): per visualizzare lo stato dei processi del set di classificazione e scaricare i file di esportazione.
* [**[!UICONTROL Classification set consolidations]**](consolidations/manage.md): per combinare più set di classificazione in un singolo set di classificazione.
