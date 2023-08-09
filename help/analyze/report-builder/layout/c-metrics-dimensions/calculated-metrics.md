---
description: Report Builder 5.2 supporta le metriche calcolate unificate di Adobe Analytics. Tra le altre innovazioni, tutte le metriche calcolate ora dispongono di un ID globale, quindi non sono più limitate a una suite di rapporti.
title: Metriche calcolate
feature: Report Builder
role: User, Admin
exl-id: 462086eb-675f-443c-b3a6-b4fa390254da
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 16%

---

# Metriche calcolate 

Report Builder 5.2 supporta le metriche calcolate unificate di Adobe Analytics. Tra le altre innovazioni, tutte le metriche calcolate ora dispongono di un ID globale, quindi non sono più limitate a una suite di rapporti.

>[!NOTE]
>
>Le cartelle di lavoro esistenti potrebbero puntare a richieste con ID metrici legacy. Quando utilizzi il Report Builder 5.2, questi ID metrica legacy verranno convertiti nel nuovo ID globale. Se condividi questa cartella di lavoro con un utente del Report Builder v5.1 o versioni precedenti, tale utente non sarà in grado di visualizzare le metriche calcolate.

Per ulteriori informazioni su come creare e gestire le metriche calcolate con il nuovo Generatore e Gestore di metriche calcolate, consulta [Metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html) Guida.

Nel passaggio 2 della Creazione guidata richieste, puoi filtrare e applicare le metriche calcolate.

## Filtrare le metriche calcolate {#section_376E986D3E684999A7CDB08E53854159}

**Filtro** metriche calcolate facendo clic sull’icona Filtro:  ![Schermata delle opzioni del filtro che mostra i campi Applicazione, Utente e Progetto.](/help/admin/admin/assets/filter.png)

La finestra di dialogo Filtri avanzati è compilata con metriche standard e calcolate.

I filtri disponibili includono:

![Schermata che mostra le opzioni Advanced Filters descritte nella tabella seguente.](assets/advanced_filters.png)

| Nome filtro | Descrizione |
|---|---|
| Tag | Consente di filtrare le metriche calcolate con tag specifici. I filtri di tag utilizzano l’operatore AND. Se selezioni due tag, nel riquadro a destra vengono visualizzate le metriche a cui sono stati assegnati tag **entrambi** tag. |
| Suite di rapporti | Se si applica &quot;Solo&quot; *nome suite di rapporti* Filtro &quot; nel generatore di metriche calcolate in [!DNL Reports & Analytics], quindi visualizzare il Filtro avanzato in [!DNL Report Builder], il filtro Avanzate visualizza le metriche calcolate solo per la suite di rapporti selezionata. |
| Proprietari | Consente di filtrare le metriche in base al proprietario. I filtri Proprietari utilizzano l’operatore OR. Se selezioni due proprietari, nel riquadro a destra vengono visualizzate le metriche di proprietà di **o** proprietario. |
| Altri filtri > Approvati | Mostra tutte le metriche approvate ufficialmente. |
| Altri filtri > Preferiti | Mostra tutte le metriche contrassegnate come Preferite. |
| Altri filtri > Personali | Mostra tutte le metriche di tua proprietà. |
| Altri filtri > Condivisi con me | Mostra tutte le metriche condivise da altri utenti con te. |

## Applicare le metriche calcolate {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

Dopo aver selezionato i filtri, fai clic su **[!UICONTROL Apply]** per applicarli alla tua richiesta. Le metriche selezionate vengono ora aggiunte al layout del rapporto.

![Schermata che mostra il Passaggio 2 della Creazione guidata richieste: Totali sito che punta alla finestra Filtri avanzati e metriche di rapporto applicate.](assets/filtering_for_metric.png)
