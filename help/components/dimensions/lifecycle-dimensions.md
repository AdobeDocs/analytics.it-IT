---
title: Dimensioni del ciclo di vita mobile
description: Dimension basati sui dati raccolti tramite l’SDK di Mobile.
feature: Dimensions
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 10%

---

# Dimensioni del ciclo di vita mobile

*Questi dati di riferimento di pagina sono comunemente tracciati tramite l’SDK di Adobe Experience Platform Mobile. Per informazioni sui dispositivi mobili tramite l’agente utente, consulta [Dimensioni di ricerca mobile](mobile-dimensions.md). Per le metriche tracciate con l’SDK di Mobile, vedi [Metriche del ciclo di vita mobile](../metrics/lifecycle-metrics.md).*

| Nome dimensione ciclo di vita | Descrizione | Variabile di dati contestuali |
| --- | --- | --- |
| [!UICONTROL First Launch Date] | | TBD (è la data di installazione?) |
| [!UICONTROL Device Name (SDK)] | | `a.DeviceName` |
| [!UICONTROL Operating System Version (SDK)] | | `a.OSVersion` |
| [!UICONTROL Resolution (SDK)] | | `a.Resolution` |
| [!UICONTROL Acquisition Source] | | `a.referrer.campaign.source` |
| [!UICONTROL App Id] | | `a.AppID` |
| [!UICONTROL Acquisition Medium] | | `a.referrer.campaign.medium` |
| [!UICONTROL Acquisition Term] | | `a.referrer.campaign.term` |
| [!UICONTROL Acquisition Content] | | `a.refferer.campaign.content` |
| [!UICONTROL Acquisition Name] | | `a.referrer.campaign.name` |
| [!UICONTROL Location (down to 10 km)] | | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Location (down to 100 m)] | | `a.loc.lat.b` + `a.loc.lon.b` |
| [!UICONTROL Location (down to 1 m)] | | `a.loc.lat.c` + `a.loc.lon.c` |
| [!UICONTROL Point of Interest Name] | | `a.loc.poi` |
| [!UICONTROL Distance to Point of Interest Center] | | `a.loc.dist` |
| [!UICONTROL Launch Number] | | `a.Launches` |
| [!UICONTROL Days Since First Use] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Action Name] | | Da definire |
| [!UICONTROL Lifetime Value (evar)] | | `a.ltv.amount` |
| [!UICONTROL Beacon Major] | | Da definire |
| [!UICONTROL Beacon Minor] | | Da definire |
| [!UICONTROL Beacon UUID] | | Da definire |
| [!UICONTROL Beacon Proximity] | | Da definire |
| [!UICONTROL Days Since Last Use] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Hour of Day (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Day of Week (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL Point of Interest ID] | | Da definire |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
