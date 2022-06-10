---
title: account
description: Utilizza la variabile di account per determinare la suite di rapporti in cui vengono inviati i dati.
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 1%

---

# account

>[!IMPORTANT]
>
>Questa variabile è ritirata. Utilizza la [`s.sa()`](../functions/sa-method.md) funziona se l&#39;implementazione richiede la modifica della destinazione della suite di rapporti.

Nelle versioni precedenti di Adobe Analytics, la `account` ha determinato la suite di rapporti a cui si desidera inviare i dati. Per inviare dati ad Adobe Analytics è necessario un ID suite di rapporti.

* Se utilizzi l’SDK per web, le suite di rapporti si trovano nelle impostazioni del servizio Adobe Analytics all’interno del Datastream a cui l’SDK per web invia i dati.
* Se utilizzi l’estensione Adobe Analytics, le suite di rapporti risiedono in [!UICONTROL Library Management] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.
* Se utilizzi [`s_gi()`](../functions/s-gi.md) funzione per creare un&#39;istanza di un oggetto di tracciamento di Analytics, gli ID suite di rapporti esistono già come argomento obbligatorio nella funzione .
