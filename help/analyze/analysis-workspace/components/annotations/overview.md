---
title: Panoramica sulle annotazioni
description: Scopri come utilizzare le annotazioni in Analysis Workspace.
role: User, Admin
solution: Analytics
feature: Annotations
exl-id: 722d7636-f619-479a-97f1-3da23e8f7f83
TQID: https://experienceleague.adobe.com/kVm6VfN3c-u3V2GHMz59QuB2uGi4DEozs1i-h4pJZOg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 57%

---

# Panoramica sulle annotazioni

Le annotazioni consentono di comunicare in modo efficace dettagli contestuali sui dati agli altri stakeholder nella propria organizzazione. Le annotazioni consentono di collegare gli eventi calendario a dimensioni o metriche specifiche. È possibile annotare una data o un intervallo di date con problemi di dati noti, festività pubbliche, avvii di campagne, ecc. Puoi quindi visualizzare graficamente gli eventi e vedere se campagne o altri eventi hanno influenzato il traffico del tuo sito, l’utilizzo delle app mobili, i ricavi o qualsiasi altra metrica.

Ad esempio, supponiamo che tu condivida dei progetti con la tua organizzazione. Se si è verificato un calo significativo dei visitatori univoci, è possibile creare un&#39;annotazione **Visitatori che diminuisce** e applicarla all&#39;intera suite di rapporti. Quando gli utenti visualizzano una suite di rapporti che include tale data, vedono l’annotazione all’interno dei loro progetti, insieme ai relativi dati.

![Grafico a linee con annotazione evidenziata.](assets/annotation-example.png)

Le annotazioni possono essere applicate a:

* Una singola data o un intervallo di date.

* L’intero set di dati o metriche, dimensioni o segmenti specifici personali.

* Il progetto in cui vengono create le annotazioni (impostazione predefinita) o tutti i progetti.

* La suite di rapporti in cui vengono create le annotazioni (impostazione predefinita) o tutte le suite di rapporti.

Per le varie opzioni disponibili per la creazione di annotazioni, consulta [Creare annotazioni](create-annotations.md). Le annotazioni verranno quindi compilate, modificate e salvate nel [generatore di annotazioni](create-annotations.md#annotation-builder).

Utilizza [Gestione annotazioni](manage-annotations.md) per gestire le annotazioni.

## Attivare o disattivare le annotazioni

Le annotazioni possono essere attivate o disattivate a diversi livelli:

| Livello | Procedura |
|---|---|
| **Visualizzazione** | Abilita o disabilita ![Impostazione](/help/assets/icons/Setting.svg) > **[!UICONTROL Settings]** > **[!UICONTROL Show annotations]**.<br/>![Abilita disabilitazione delle annotazioni per una visualizzazione](assets/annotations-visualization.png) |
| **Progetto** | Dal menu di un progetto di Workspace, selezionare **[!UICONTROL Project]** > **[!UICONTROL Project info & settings]** e abilitare o disabilitare **[!UICONTROL Show annotations]**.<br/>![Abilitare le annotazioni disabilitate per un progetto](assets/annotations-project.png) |
| **Utente** | Dalla scheda **[!UICONTROL Components]**, seleziona **[!UICONTROL Preferences]** oppure dal menu di un progetto Workspace, seleziona **[!UICONTROL Project]** > **[!UICONTROL User preferences]**. <br/>In **[!UICONTROL Preferences]**, seleziona **[!UICONTROL Projects & Analysis]**. Dalla barra della scheda a sinistra, seleziona **[!UICONTROL Data]**. In basso, abilita o disabilita **[!UICONTROL Show annotations]** sotto l’intestazione **[!UICONTROL Freeform table]**.<br/>![Abilitare o disabilitare annotazioni per un utente](assets/annotations-user.png) |

<!--
# Annotations overview

Annotations in Workspace enable you to effectively communicate contextual data nuances and insights to your organization. They let you tie calendar events to specific dimensions/metrics. You can annotate a date or date range with known data issues, public holidays, campaign launches, etc. You can then graphically display events and see whether campaigns or other events have affected your site traffic, revenue, or any other metric.

For example, let's say you are sharing projects with your organization. If you had a major spike in traffic due to a marketing campaign, you could create a "Campaign launch date" annotation and scope it for your whole report suite. When your users view any data sets that included that date, they see the annotation within their projects, alongside their data.

![Annotation example](assets/annotation-example.png)

Keep this in mind:

* Annotations can be tied to a single date or to a date range.

* They can apply to your entire data set or to specified metrics, dimensions, or segments.

* They can apply to the project in which they were created (default) or to all projects.

* They can apply to the report suite in which they were created (default) or to all report suites.

## Permissions {#permissions}

By default, only Admins can create annotations. Users have rights to view annotations like they do with other other Analytics components (such as segments, calculated metrics, etc.).

However, Admins can give the [!UICONTROL Annotation Creation] permission (Analytics Tools) to users via the [Adobe Admin Console](/help/admin/admin-console/permissions/analytics-tools.md).

## Turn annotations on or off {#annotations-on-off}

Annotations can be turned on or off at several levels:

* At the Visualization level: [!UICONTROL Visualization] settings > [!UICONTROL Show annotations]

* At the Project level: [!UICONTROL Project info & settings] > [!UICONTROL Show annotations]

* At the User level: [!UICONTROL Components] > [!UICONTROL User preferences] > [!UICONTROL Data] > [!UICONTROL Show annotations]

![](assets/show-ann.png)

![](assets/show-ann2.png)
-->