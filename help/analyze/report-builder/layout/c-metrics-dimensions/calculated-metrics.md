---
description: Report Builder 5.2 supporta le metriche calcolate unificate Adobe Analytics. Tra le altre innovazioni, tutte le metriche calcolate ora dispongono di un ID globale, quindi non sono più limitate a una suite di rapporti.
title: Metriche calcolate
feature: Report Builder
role: User, Admin
exl-id: 462086eb-675f-443c-b3a6-b4fa390254da
source-git-commit: e7346b11a7d3eb4c18ec02df6c8a07574e02a2b4
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 18%

---

# Metriche calcolate 

Report Builder 5.2 supporta le metriche calcolate unificate Adobe Analytics. Tra le altre innovazioni, tutte le metriche calcolate ora dispongono di un ID globale, quindi non sono più limitate a una suite di rapporti.

>[!NOTE]
>
>Le cartelle di lavoro esistenti potrebbero indicare richieste con ID di metriche precedenti. Quando utilizzi Report Builder 5.2, questi ID di metriche legacy verranno convertiti nel nuovo ID globale. Se condividi questa cartella di lavoro con un utente del Report Builder v5.1 o precedente, tale utente non sarà in grado di visualizzare le metriche calcolate.

Per ulteriori informazioni su come creare e gestire le metriche calcolate con il nuovo Generatore e Gestore della metrica calcolata, consulta la sezione [Metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html) Guida.

Nel passaggio 2 della Creazione guidata richieste è possibile filtrare e applicare le metriche calcolate.

## Filtrare le metriche calcolate {#section_376E986D3E684999A7CDB08E53854159}

**Filtro** metriche calcolate facendo clic sull’icona Filtro :  ![](/help/admin/admin/assets/filter.png)

. La finestra di dialogo Filtri avanzati viene compilata con metriche standard e calcolate.

I filtri disponibili includono:

![](assets/advanced_filters.png)

| Nome filtro | Descrizione |
|---|---|
| Tag | Consente di filtrare le metriche calcolate con tag specifici. I filtri di tag utilizzano l’operatore AND. Se selezioni due tag, il riquadro a destra mostra le metriche con tag **entrambi** tag. |
| Suite di rapporti | Se si applica &quot;Solo&quot; *nome della suite di rapporti*&quot; nel Generatore della metrica calcolata in [!DNL Reports & Analytics], quindi visualizza il Filtro avanzato in [!DNL Report Builder], il filtro Avanzate visualizza le metriche calcolate solo per la suite di rapporti selezionata. |
| Proprietari | Consente di filtrare le metriche in base al proprietario. I filtri Proprietari utilizzano l’operatore OR. Se selezioni due proprietari, il riquadro a destra mostra le metriche di proprietà di **o** proprietario. |
| Altri filtri > Approvati | Mostra tutte le metriche approvate ufficialmente. |
| Altri filtri > Preferiti | Mostra tutte le metriche contrassegnate come Preferiti. |
| Altri filtri > Personali | Mostra tutte le metriche di tua proprietà. |
| Altri filtri > Condivisi con me | Mostra tutte le metriche condivise da altri utenti con te. |

## Applica metriche calcolate {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

Dopo aver selezionato i filtri, fai clic su **[!UICONTROL Apply]** per applicarli alla tua richiesta. Le metriche selezionate vengono ora aggiunte al layout del rapporto.

![](assets/filtering_for_metric.png)
