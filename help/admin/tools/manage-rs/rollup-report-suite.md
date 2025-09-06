---
description: Descrizioni delle suite di rapporti globali
title: Suite di rapporti globali
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 95%

---

# Suite di rapporti globali

Una suite di rapporti globale raccoglie dati da tutti i domini e le app di proprietà della tua organizzazione. Richiede l’implementazione per inviare tutte le richieste di immagini a un’unica suite di rapporti.

Nella maggior parte dei casi, Adobe consiglia di implementare una suite di rapporti globale. Consulta le [considerazioni sulla suite di rapporti globale](/help/implement/prepare/global-rs.md) per i vantaggi dell’implementazione di una suite di rapporti globale.

Puoi fornire sottoinsiemi dei dati della suite di rapporti globale della tua azienda a utenti finali diversi utilizzando gli approcci *assegnazione di tag multisuite* e *suite di rapporti virtuale*:

* **Assegnazione di tag multisuite**: consente di inviare richieste di immagini non solo a una suite di rapporti globale, ma anche a specifiche suite di rapporti secondarie. I dati del rapporto globale vengono deduplicati in tutte le suite di rapporti.

  Ad esempio, puoi raccogliere tutti i dati in una suite di rapporti globale e impostare suite di rapporti secondarie in base al marchio, all’area geografica o a un altro differenziatore. I diversi team della tua azienda possono quindi concentrarsi sui dati delle suite di rapporti che ritengono pertinenti.

  Per utilizzare l’assegnazione tag multisuite, implementa suite di rapporti secondarie e una suite di rapporti globale che includa tutti i dati provenienti dagli elementi secondari. Il codice di tracciamento per le tue app e pagine web includerà l’ID suite di rapporti (RSID) per la suite di rapporti globale e gli RSID per le suite di rapporti secondarie applicabili.<!-- Wording/be more specific? And include any links? -->

  Viene effettuata una chiamata al server separata a ogni suite di rapporti nella richiesta di immagine. Le chiamate alle suite di rapporti secondarie sono chiamate secondarie.

* **Suite di rapporti virtuali**: una [suite di rapporti virtuale](/help/components/vrs/vrs-about.md) è una query su segmenti specifici raccolti in una suite di rapporti globale, disponibile per gruppi di utenti specifici. Le suite di rapporti virtuali consentono di curare gli elementi dei rapporti per utenti finali diversi senza utilizzare l’assegnazione tag multisuite, evitando in tal modo le chiamate al server secondarie.

  Per utilizzare le suite di rapporti virtuali, implementa una suite di rapporti globale, quindi analizza i dati per creare suite di rapporti virtuali con segmenti specifici applicati e con autorizzazioni di gruppo specifiche. È possibile creare suite di rapporti virtuali in Gestione delle suite di rapporti virtuali ([!UICONTROL Components] > [!UICONTROL Virtual report suites]). Per ulteriori informazioni, consulta la sezione sul [flusso di lavoro per suite di rapporti virtuali](/help/components/vrs/c-workflow-vrs/vrs-workflow.md).

Invece di usare più suite di rapporti con tag, spesso è preferibile utilizzare le suite di rapporti virtuali; tuttavia queste presentano alcune limitazioni. Consulta le [considerazioni sulle suite di rapporti virtuali e sull’assegnazione di tag a più suite](/help/components/vrs/vrs-considerations.md) per capire quale approccio scegliere in base alle tue esigenze di business. Per un confronto approfondito tra suite di rapporti virtuali e la funzionalità di assegnazione tag per più suite, vedi [Suite di rapporti virtuali e assegnazione tag per più suite](/help/components/vrs/vrs-about.md).

<!---## Rollup reports

>[!NOTE]
>
>[!DNL Reports & Analytics] is the only tool that supported rollup reports. Reports & Analytics was end-of-lifed on January 17, 2024.

Limitations of Rollup Reports {#limitations-rollups}

* Rollups provide total data, but they do not report individual values in reports. For example, eVar1 values are not included, but their aggregate total can be.
* Data is not deduplicated when the rollup combines data across report suites.
* Rollups run nightly at midnight.
* When you add a report suite to an existing rollup, historical data is not included in the rollup.
* All child report suites must have data in them for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to each of those report suites.
* Rollup report suites can include a maximum of 40 child report suites.
* Rollup report suites can include a maximum of 100 events.
* Data contained in rollup report suites does not support breakdowns or segments.
* The Pages report is replaced with the Most Popular Sites report, which reports on metrics at the child-suite level.

## Comparison of Global Report Suite and Rollup Report  Features

**Secondary server calls**: Rollups do not incur any additional server calls beyond what a single report suite collects. If your organization uses multi-suite tagging, secondary server calls are made for each additional report suite included in an image request.

>[!TIP]
>
>If you use only a global report suite with [virtual report suites](/help/components/vrs/vrs-considerations.md), no secondary server calls are needed.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require you to include the global report suite ID in your implementation.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Rollups have no way to communicate between report suites. Global report suites can attribute credit to conversion variables between report suites and provide pathing across report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide data on all dimensions; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups could only be used in Reports & Analytics. They are not supported in Analysis Workspace, or Data Warehouse. Global report suites can be used across all products.

**Number of aggregated report suites**: Rollups only support a maximum of 40 child report suites. Global report suites can be implemented on any number of domains or apps that you own.--->
