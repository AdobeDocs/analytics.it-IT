---
title: Implementare Adobe Analytics con Adobe Experience Platform Edge
description: Panoramica dell’utilizzo di dati XDM da Experience Platform in Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: a515927313fdc6025fb3ff8eaedf0b3742bede70
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 16%

---

# Implementare Adobe Analytics con la rete Edge di Adobe Experience Platform

La rete Edge di Adobe Experience Platform consente di inviare dati destinati a più prodotti a una posizione centralizzata. La rete Edge inoltra le informazioni appropriate ai prodotti desiderati. Questo concetto consente di consolidare le attività di implementazione, in particolare per quanto riguarda più soluzioni di dati. Adobe Analytics è uno dei prodotti a cui puoi inviare dati utilizzando Edge Network.

## Gestione dei dati della rete Edge in Adobe Analytics

I dati inviati all&#39;Edge Network di Adobe Experience Platform possono seguire tre formati: **Oggetto XDM**, **Oggetto dati** e **Dati contestuali**. Quando un flusso di dati inoltra i dati ad Adobe Analytics, questi vengono tradotti in un formato che Adobe Analytics può gestire.

## `xdm` oggetto

Conformarsi agli schemi creati in base a [XDM](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home.html?lang=it) (Experience Data Model). XDM offre flessibilità nei campi definiti come parte degli eventi. Se desideri utilizzare uno schema predefinito specifico per Adobe Analytics, puoi aggiungere il [gruppo di campi dello schema Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) allo schema. Una volta aggiunto, è possibile popolare questo schema utilizzando l&#39;oggetto `xdm` nel Web SDK per inviare dati a una suite di rapporti. Quando i dati arrivano all’Edge Network, traducono l’oggetto XDM in un formato comprensibile da Adobe Analytics.

Per un riferimento completo ai campi XDM e al modo in cui vengono mappati alle variabili Analytics, vedi [Mappatura delle variabili oggetto XDM su Adobe Analytics](xdm-var-mapping.md).

>[!TIP]
>
>Se prevedi di passare in futuro a [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing), Adobe consiglia di non utilizzare il gruppo di campi dello schema di Adobe Analytics. Al contrario, Adobe consiglia di [creare uno schema personalizzato](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect) e utilizzare la mappatura dello stream di dati per popolare le variabili Analytics desiderate. Questa strategia non ti blocca in uno schema di proprietà ed eVar quando sei pronto per passare a Customer Journey Analytics.

## `data` oggetto

In alternativa all&#39;utilizzo dell&#39;oggetto `xdm`, è possibile utilizzare l&#39;oggetto `data`. L’oggetto dati è orientato alle implementazioni che attualmente utilizzano AppMeasurement, rendendo molto più semplice l’aggiornamento a Web SDK. Edge Network rileva la presenza di campi specifici di Adobe Analytics senza la necessità di conformarsi a uno schema.

Per un riferimento completo ai campi dell&#39;oggetto dati e alla modalità di mapping con le variabili di Analytics, vedi [Mappatura delle variabili dell&#39;oggetto dati in Adobe Analytics](data-var-mapping.md).

## Variabili di dati di contesto

Invia dati ad Edge Network in qualsiasi formato. Tutti i campi che non vengono mappati automaticamente ai campi oggetto `xdm` o `data` vengono inclusi come [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) quando inoltrati ad Adobe Analytics. Devi quindi utilizzare [Regole di elaborazione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) per mappare i campi desiderati alle rispettive variabili di Analytics.

Ad esempio, se lo schema XDM era personalizzato come il seguente:

```json
{
  "xdm": {
    "key": "value",
    "animal": {
      "species": "Raven",
      "size": "13 inches"
    },
    "array": [
      "v0",
      "v1",
      "v2"
    ],
    "objectArray":[{
      "ad1": "300x200",
      "ad2": "60x240",
      "ad3": "600x50"
    }]
  }
}
```

Questi campi sarebbero quindi le chiavi di dati contestuali disponibili nell’interfaccia Regole di elaborazione:

```javascript
a.x.key // value
a.x.animal.species // Raven
a.x.animal.size // 13 inches
a.x.array.0 // v0
a.x.array.1 // v1
a.x.array.2 // v2
a.x.objectarray.0.ad1 // 300x200
a.x.objectarray.1.ad2 // 60x240
a.x.objectarray.2.ad3 // 600x50
```
