---
description: Con il generatore Calculated Metric, chiunque può creare una metrica di partecipazione.
seo-description: Con il generatore Calculated Metric, chiunque può creare una metrica di partecipazione.
seo-title: Metrica di partecipazione
title: Metrica di partecipazione
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Metrica di partecipazione

Esempio di utilizzo semplice: Il proprietario del contenuto e l'utente desidera vedere quali pagine hanno contribuito (ad es., hanno partecipato) alle visite che contenevano un ordine. effettuando le seguenti operazioni:

> [!NOTE] Una volta dovevi farlo tramite Strumenti di amministrazione. Puoi comunque abilitare le metriche di partecipazione in Strumenti di amministrazione, ma solo per gli eventi personalizzati 1 - 100.

Di seguito sono riportati alcuni casi d’uso semplici: Il proprietario del contenuto e l'utente desidera vedere le pagine a cui ha contribuito (ha partecipato) le visite che contenevano una registrazione tramite e-mail. effettuando le seguenti operazioni:

1. Crea una nuova metrica nel Generatore di metrica calcolata.
1. Trascinate l’evento di successo "Ordini" nell’area di lavoro Definizione.
1. Modificate il modello [di](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) attribuzione dell’evento in **[!UICONTROL Participation]** corrispondenza della **[!UICONTROL Settings]** marcia. Selezionate **[!UICONTROL Visit]** lookback. La definizione deve essere simile a quella riportata di seguito:

   ![](assets/participation.png)

1. Salva la metrica.
1. Usa la metrica calcolata in un **[!UICONTROL Pages]** report.

   ![](assets/participation-pages.png)

1. (Facoltativo) Condividi la metrica con altri utenti nell’organizzazione.

