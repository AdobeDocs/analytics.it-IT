---
title: Dimensioni del ciclo di vita mobile
description: Dimensioni basate sui dati raccolti tramite Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%

---

# Dimensioni del ciclo di vita mobile

*Questa pagina contiene dati di riferimento tracciati comunemente tramite Adobe Experience Platform Mobile SDK. Per informazioni sul dispositivo mobile tramite l&#39;agente utente, vedere [Dimensioni di ricerca mobile](mobile-dimensions.md). Per le metriche tracciate con Mobile SDK, vedi [Metriche del ciclo di vita mobile](../metrics/lifecycle-metrics.md).*

| Nome dimensione ciclo di vita | Descrizione | Variabile dati contestuali |
| --- | --- | --- |
| [!UICONTROL First Launch Date] | | |
| [!UICONTROL Device Name (SDK)] | | `a.DeviceName` |
| [!UICONTROL Operating System Version (SDK)] | | `a.OSVersion` |
| [!UICONTROL Resolution (SDK)] | | `a.Resolution` |
| [!UICONTROL Acquisition Source] | | `a.referrer.campaign.source` |
| [!UICONTROL App Id] | | `a.AppID` |
| [!UICONTROL Acquisition Medium] | | `a.referrer.campaign.medium` |
| [!UICONTROL Acquisition Term] | | `a.referrer.campaign.term` |
| [!UICONTROL Acquisition Content] | | `a.refferer.campaign.content` |
| [!UICONTROL Acquisition Name] | | `a.referrer.campaign.name` |
| [!UICONTROL Location (down to 10 km)] | La latitudine e la longitudine del visitatore, precise al primo decimale. Ad esempio, `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Location (down to 100 m)] | La latitudine e la longitudine del visitatore, con precisione alla terza cifra decimale. Ad esempio, `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL Location (down to 1 m)] | La latitudine e la longitudine del visitatore, con precisione al quinto decimale. Ad esempio, `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL Point of Interest Name] | | `a.loc.poi` |
| [!UICONTROL Distance to Point of Interest Center] | | `a.loc.dist` |
| [!UICONTROL Launch Number] | | `a.Launches` |
| [!UICONTROL Days Since First Use] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Action Name] | | |
| [!UICONTROL Lifetime Value (evar)] | | `a.ltv.amount` |
| [!UICONTROL Beacon Major] | | |
| [!UICONTROL Beacon Minor] | | |
| [!UICONTROL Beacon UUID] | | |
| [!UICONTROL Beacon Proximity] | | |
| [!UICONTROL Days Since Last Use] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Hour of Day (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Day of Week (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL Point of Interest ID] | | |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
