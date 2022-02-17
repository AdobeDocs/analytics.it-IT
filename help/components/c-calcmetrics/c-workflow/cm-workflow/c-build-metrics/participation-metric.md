---
description: Con il generatore di metriche calcolate, chiunque può creare una metrica di partecipazione.
title: Metrica di partecipazione
feature: Calculated Metrics
exl-id: bef185d6-72c0-4068-80f8-57261369573f
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 5%

---

# Metrica di partecipazione

Ecco un caso d’uso semplice: Sei un proprietario di contenuto e vuoi vedere quali pagine hanno contribuito (ovvero, partecipato) alle visite che contenevano un ordine. effettuando le seguenti operazioni:

>[!NOTE]
>
>Questa operazione era necessaria tramite gli Strumenti di amministrazione. Puoi comunque abilitare le metriche di partecipazione negli Strumenti di amministrazione, ma solo per gli eventi personalizzati da 1 a 100.

Di seguito sono riportati alcuni casi d’uso semplici: Sei un proprietario di contenuto e desideri vedere quali pagine hanno contribuito (partecipato) alle visite che contenevano un&#39;iscrizione e-mail. effettuando le seguenti operazioni:

1. Crea una nuova metrica nel Generatore di metrica calcolata.
1. Trascina l’evento di successo &quot;Ordini&quot; nell’area di lavoro Definizione.
1. Modificare la [modello di attribuzione](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) di tale evento **[!UICONTROL Participation]** in **[!UICONTROL Settings]** ingranaggio. Seleziona **[!UICONTROL Visit]** lookback. La definizione dovrebbe essere simile alla seguente:

   ![](assets/participation.png)

1. Salva la metrica.
1. Utilizza la metrica calcolata in un **[!UICONTROL Pages]** rapporto.

   ![](assets/participation-pages.png)

1. (Facoltativo) Condividi la metrica con altri utenti dell’organizzazione.
