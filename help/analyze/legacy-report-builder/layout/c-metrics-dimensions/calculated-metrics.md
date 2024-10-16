---
description: Report Builder 5.2 supporta le metriche calcolate unificate di Adobe Analytics. Tra le altre innovazioni, tutte le metriche calcolate ora dispongono di un ID globale, quindi non sono più limitate a una suite di rapporti.
title: Metriche calcolate
feature: Report Builder
role: User, Admin
exl-id: 462086eb-675f-443c-b3a6-b4fa390254da
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 17%

---

# Metriche calcolate

Report Builder 5.2 supporta le metriche calcolate unificate di Adobe Analytics. Tra le altre innovazioni, tutte le metriche calcolate ora dispongono di un ID globale, quindi non sono più limitate a una suite di rapporti.

>[!NOTE]
>
>Le cartelle di lavoro esistenti potrebbero puntare a richieste con ID metrici legacy. Quando utilizzi il Report Builder 5.2, questi ID metrica legacy verranno convertiti nel nuovo ID globale. Se condividi questa cartella di lavoro con un utente del Report Builder v5.1 o versioni precedenti, tale utente non sarà in grado di visualizzare le metriche calcolate.

Per ulteriori informazioni su come creare e gestire le metriche calcolate con il nuovo Generatore di metriche calcolate e Manager, consulta la [Guida alle metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=it).

Nel passaggio 2 della Creazione guidata richieste, puoi filtrare e applicare le metriche calcolate.

## Filtrare le metriche calcolate {#section_376E986D3E684999A7CDB08E53854159}

**Filtrare** le metriche calcolate facendo clic sull&#39;icona Filtro: ![Schermata delle opzioni di Filtro che mostra i campi Applicazione, Utente, Progetto.](/help/admin/admin/assets/filter.png)

La finestra di dialogo Filtri avanzati è compilata con metriche standard e calcolate.

I filtri disponibili includono:

![Schermata che mostra le opzioni Filtri avanzati descritte nella tabella seguente.](assets/advanced_filters.png)

| Nome filtro | Descrizione |
|---|---|
| Tag | Consente di filtrare le metriche calcolate con tag specifici. I filtri di tag utilizzano l’operatore AND. Se selezioni due tag, nel riquadro a destra vengono visualizzate le metriche a cui sono stati assegnati tag **entrambi**. |
| Suite di rapporti | Se si applica il filtro &quot;Solo *nome suite di rapporti*&quot; nel generatore di metriche calcolate in [!DNL Adobe Analytics] e quindi si visualizza il filtro avanzato in [!DNL Report Builder], il filtro Avanzate visualizzerà le metriche calcolate solo per la suite di rapporti selezionata. |
| Proprietari | Consente di filtrare le metriche in base al proprietario. I filtri Proprietari utilizzano l’operatore OR. Se selezioni due proprietari, nel riquadro a destra vengono visualizzate le metriche di proprietà del proprietario **uno**. |
| Altri filtri > Approvati | Mostra tutte le metriche approvate ufficialmente. |
| Altri filtri > Preferiti | Mostra tutte le metriche contrassegnate come Preferite. |
| Altri filtri > Personali | Mostra tutte le metriche di tua proprietà. |
| Altri filtri > Condivisi con me | Mostra tutte le metriche condivise da altri utenti con te. |

## Applicare le metriche calcolate {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

Dopo aver selezionato i filtri, fare clic su **[!UICONTROL Apply]** per applicarli alla richiesta. Le metriche selezionate vengono ora aggiunte al layout del rapporto.

![Schermata che mostra il passaggio 2 della Creazione guidata richieste: i totali del sito puntano alla finestra Filtri avanzati e le metriche del report applicate.](assets/filtering_for_metric.png)
