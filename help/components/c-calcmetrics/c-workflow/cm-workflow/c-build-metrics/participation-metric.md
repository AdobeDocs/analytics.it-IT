---
description: Con il generatore di metriche calcolate, chiunque può creare una metrica di partecipazione.
seo-description: Con il generatore di metriche calcolate, chiunque può creare una metrica di partecipazione.
seo-title: Metrica di partecipazione
title: Metrica di partecipazione
uuid: 7 cb 191 be-bc 4 e -46 ef -8 a 20-ccba 5355 e 253
translation-type: tm+mt
source-git-commit: bc0adf08d2b68c314c38f0484addbff567147e88

---


# Metrica di partecipazione

Esempio di utilizzo semplice: Siete un proprietario del contenuto e desiderate vedere quali pagine hanno contribuito a visitare le visite contenute in un ordine. effettuando le seguenti operazioni:

>[!NOTE]
>
>È stato necessario farlo tramite Strumenti di amministrazione. Puoi comunque abilitare le metriche di partecipazione in Strumenti di amministrazione, ma solo per gli eventi personalizzati da 1 a 100.

Casi d'uso semplici: Siete un proprietario del contenuto e desiderate vedere quali pagine hanno contribuito a partecipare a visite contenenti un'iscrizione e-mail. Ecco come:

1. Crea una nuova metrica nel Generatore di metriche calcolate.
1. Trascinate l'evento di successo "Ordini" nel quadro di definizione.
1. Cambia il [modello di attribuzione](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) di quell'evento sotto **[!UICONTROL Participation]** l' **[!UICONTROL Settings]** ingranaggio. Selezionate **[!UICONTROL Visit]** lookback. La definizione deve essere simile a quella riportata di seguito:

   ![](assets/participation.png)

1. Salva la metrica.
1. Utilizzate la metrica calcolata in un **[!UICONTROL Pages]** report.

   ![](assets/participation-pages.png)

1. (Facoltativo) Condividi la metrica con altri utenti dell'organizzazione.

