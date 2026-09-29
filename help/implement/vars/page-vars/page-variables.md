---
title: Variabili di pagina
description: Imposta i valori su una singola pagina.
feature: Appmeasurement Implementation
exl-id: 321d0db2-61a3-478e-ab51-8e06c7b2bb7b
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/mWfMumcPTklFPKUiGIOatDbC0WKW5RDYH56rXTFk3ZY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 2%
---
# Panoramica delle variabili di pagina

Le variabili di pagina determinano i valori per le dimensioni e le metriche nel reporting.

Di seguito sono elencate le variabili utilizzate di frequente nelle implementazioni:

* [`pageName`](pagename.md): nome della pagina.
* [`campaign`](campaign.md): impostare questa variabile su un parametro stringa query per il tracciamento della campagna.
* [`events`](events/events-overview.md): popolare le metriche da utilizzare nel reporting.
* [`products`](products.md): se disponi di un sito eCommerce, imposta questa variabile quando un visitatore visualizza o acquista un prodotto.

## Variabili di pagina ritirate

Le seguenti variabili di pagina vengono ritirate. Sono documentati qui come riferimento se si trovano in un’implementazione legacy.

* **`hier`**: implementate variabili gerarchiche (`hier1`-`hier5`) per acquisire la struttura di un sito per il reporting. È stata ritirata e non è una dimensione disponibile in Analysis Workspace. Utilizza invece [eVar](evar.md) e classificazioni.
* **`state`**: ha acquisito lo stato degli Stati Uniti in cui un visitatore è entrato, in genere tramite un modulo di spedizione o di fatturazione. Utilizza invece la dimensione [[!UICONTROL US States]](/help/components/dimensions/us-states.md), che Adobe compila automaticamente dalla posizione geografica del visitatore.
