---
title: Supporto dei componenti in Data Warehouse
description: Scopri quali dimensioni e metriche sono disponibili quando generi una richiesta Data Warehouse, quali non sono disponibili e quali si comportano in modo diverso.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
TQID: https://experienceleague.adobe.com/NhSEyPN3093B9M0SngJluJdZScI2lXvRyHkXQd8gg-4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 283
ht-degree: 0%

---

# Supporto dei componenti in Data Warehouse

Questa pagina descrive le dimensioni e le metriche che puoi utilizzare per creare una richiesta Data Warehouse. Le sezioni includono quali componenti sono disponibili, quali non sono disponibili e quali si comportano in modo diverso rispetto ad altri strumenti di Adobe Analytics.

## Dimensioni esclusive per Data Warehouse

Le dimensioni seguenti possono essere utilizzate in Data Warehouse ma non sono disponibili in altre funzionalità di Adobe Analytics.

* [[!UICONTROL Experience Cloud Visitor ID]](/help/components/dimensions/experience-cloud-visitor-id.md)
* [[!UICONTROL IP Address]](/help/components/dimensions/ip-address.md)
* [[!UICONTROL Page URL]](/help/components/dimensions/page-url.md)
* [[!UICONTROL Purchase ID]](/help/components/dimensions/purchase-id.md)
* [[!UICONTROL Visitor ID]](/help/components/dimensions/visitor-id.md)

## Dimensioni non supportate

Le dimensioni seguenti non sono disponibili nei rapporti o nei segmenti di Data Warehouse:

* [[!UICONTROL AM/PM]](/help/components/dimensions/am-pm.md)
* Tutte le dimensioni di ingresso, tranne [[!UICONTROL Entry Page]](/help/components/dimensions/entry-dimensions.md) e [[!UICONTROL Entry page original]](/help/components/dimensions/entry-dimensions.md) che sono consentite
* Tutte le dimensioni di uscita, tranne [[!UICONTROL Exit Page]](/help/components/dimensions/exit-dimensions.md) e [[!UICONTROL Exit Link]](/help/components/dimensions/exit-link.md) che sono consentite
* [[!UICONTROL Hit Depth]](/help/components/dimensions/hit-depth.md)
* [[!UICONTROL Return Frequency]](/help/components/dimensions/return-frequency.md)
* [[!UICONTROL Time Prior to Event]](/help/components/dimensions/time-prior-to-event.md)
* [[!UICONTROL Time Spent on Page - Bucketed]](/help/components/dimensions/time-spent-on-page.md)
* [[!UICONTROL Time Spent per Visit - Bucketed]](/help/components/dimensions/time-spent-per-visit.md)
* [[!UICONTROL All Search Page Rank]](/help/components/dimensions/all-search-page-rank.md)
* [[!UICONTROL Hierarchy]](/help/components/dimensions/overview.md#retired-dimensions) variabili
* [[!UICONTROL Hit Type]](/help/components/dimensions/hit-type.md)
* [[!UICONTROL Paid Search]](/help/components/dimensions/paid-search.md)
* [[!UICONTROL Single Page Visits]](/help/components/dimensions/single-page-visits.md)
* [[!UICONTROL Tracking Opt-out Reason]](/help/components/dimensions/tracking-opt-out-reason.md)
* [[!UICONTROL US States]](/help/components/dimensions/us-states.md)

Alcune dimensioni sono disponibili in una richiesta Data Warehouse ma non possono essere utilizzate all’interno di un segmento. Per ulteriori informazioni, consulta [Compatibilità del segmento di Data Warehouse](segment-compatibility.md).

## Dimensioni con formattazione della data non standard

Le seguenti dimensioni basate sul tempo sono supportate nei rapporti di Data Warehouse, ma il loro output utilizza un formato non standard:

* [[!UICONTROL Year]](/help/components/dimensions/year.md)
* [[!UICONTROL Quarter]](/help/components/dimensions/quarter.md)
* [[!UICONTROL Month]](/help/components/dimensions/month.md)
* [[!UICONTROL Week]](/help/components/dimensions/week.md)
* [[!UICONTROL Day]](/help/components/dimensions/day.md)
* [[!UICONTROL Hour]](/help/components/dimensions/hour.md)
* [[!UICONTROL Minute]](/help/components/dimensions/minute.md)

I valori di data vengono generati nel formato `1YYMMDDHHMM`:

* **Anno (AA)**: offset di 1900. Aggiungi `1900` alle prime tre cifre. Ad esempio, `125` = anno **2025**.
* **Mese**: basato su zero. Gennaio = `00`, Febbraio = `01`, ..., Dicembre = `11`.

Ad esempio, se il campo Settimana intervallo di date mostra `1260901`, l&#39;anno è 1900 + 126 = **2026** e il mese è 09 = **Ottobre**.

## Metriche definite in modo diverso in Data Warehouse

* **[[!UICONTROL Visits]](/help/components/metrics/visits.md)**: esclude le visite dei cookie non persistenti, a differenza della metrica Visite in altri strumenti di Adobe Analytics.
* **[[!UICONTROL Visits - All Visitors]](/help/components/metrics/visits.md)**: conta tutti i visitatori, inclusi quelli con cookie non persistenti, rendendolo più simile alla metrica [!UICONTROL Visits] standard utilizzata altrove in Adobe Analytics.

## Metriche non supportate

Le metriche seguenti non sono disponibili in Data Warehouse:

* [[!UICONTROL Bounces]](/help/components/metrics/bounces.md)
* [[!UICONTROL Entries]](/help/components/metrics/entries.md)
* [[!UICONTROL Exits]](/help/components/metrics/exits.md)
* [[!UICONTROL Reloads]](/help/components/metrics/reloads.md)
* [[!UICONTROL Single Access]](/help/components/metrics/single-access.md)
* Qualsiasi metrica [[!UICONTROL Time Spent]](/help/components/metrics/time-spent.md)
* Qualsiasi metrica che utilizza un modello di attribuzione [partecipazione](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md)
