---
description: Generatore di report 5.2 supporta le metriche calcolate unificate di Adobe  Analytics. Tra le altre innovazioni, tutte le metriche calcolate ora dispongono di un ID globale, quindi non sono più limitate a una suite di rapporti.
title: Metriche calcolate
uuid: c9814894-cda6-40ff-8ec4-3ab2c1908ebc
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 15%

---


# Metriche calcolate

Generatore di report 5.2 supporta le metriche calcolate unificate di Adobe  Analytics. Tra le altre innovazioni, tutte le metriche calcolate ora dispongono di un ID globale, quindi non sono più limitate a una suite di rapporti.

>[!NOTE]
>
>Le cartelle di lavoro esistenti potrebbero puntare a richieste con ID di metriche precedenti. Quando si utilizza Generatore di report 5.2, questi ID di metriche precedenti verranno convertiti nel nuovo ID globale. Se condividete la cartella di lavoro con un utente di Generatore di report v5.1 o versioni precedenti, tale utente non sarà in grado di visualizzare le metriche calcolate.

Per ulteriori informazioni su come creare e gestire le metriche calcolate con il nuovo Generatore e Manager metriche calcolate, consulta la Guida alle metriche [](https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/cm-overview.html) calcolate.

Nel passaggio 2 della Richiesta guidata, puoi filtrare e applicare le metriche calcolate.

## Filtra metriche calcolate {#section_376E986D3E684999A7CDB08E53854159}

**Filtrare** le metriche calcolate facendo clic sull&#39;icona Filtro:  ![](assets/segment_filter.png)

. La finestra di dialogo Filtri avanzati viene compilata con metriche standard e calcolate.

I filtri disponibili includono:

![](assets/advanced_filters.png)

| Nome filtro | Descrizione |
|---|---|
| Tag | Consente di filtrare le metriche calcolate con tag specifici. I filtri tag utilizzano l&#39;operatore AND. Se si verificano due tag, nel riquadro a destra sono visualizzate le metriche a cui sono stati assegnati **entrambi** i tag. |
| Suite di rapporti | Se applicate il filtro &quot;Only *report suite name*&quot; nel Generatore di metriche calcolate in [!DNL Reports & Analytics], e quindi visualizzate il Filtro avanzato in [!DNL Report Builder], il filtro Avanzate visualizzerà le metriche calcolate solo per la suite di rapporti selezionata. |
| Proprietari | Consente di filtrare le metriche in base al proprietario. I filtri Proprietari utilizzano l&#39;operatore OR. Se si selezionano due proprietari, nel riquadro a destra sono visualizzate le metriche di proprietà di **entrambi** i proprietari. |
| Altri filtri > Approvati | Mostra tutte le metriche approvate ufficialmente. |
| Altri filtri > Preferiti | Mostra tutte le metriche contrassegnate come Preferiti. |
| Altri filtri > Mine | Mostra tutte le metriche di proprietà. |
| Altri filtri > Condivisi con me | Mostra tutte le metriche condivise con altri utenti. |

## Applica metriche calcolate {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

Dopo aver selezionato i filtri, fate clic **[!UICONTROL Apply]** per applicarli alla richiesta. Le metriche selezionate vengono ora aggiunte al layout del report.

![](assets/filtering_for_metric.png)

