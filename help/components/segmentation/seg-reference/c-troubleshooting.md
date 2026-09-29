---
description: Scopri come risolvere i problemi relativi ai segmenti.
title: Risoluzione dei problemi
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
TQID: 'https://experienceleague.adobe.com/-9XPy2cFezGBFnygKW4gbHG2zuNBfn5Z29InEDF58ZM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: c47a19a5-f47b-4e53-afe0-e230da195ebe
    internal-label: Segmentation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 1%
---
# Risoluzione dei problemi

In questo articolo sono elencati alcuni problemi comuni relativi ai segmenti e come risolverli.

<!--
Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.
-->

## Perché il segmento non restituisce alcun dato? {#no-data}

Possibili motivi:

* Annidamento inverso: ad esempio, nidificando un contenitore ![Utente](/help/assets/icons/User.svg) **[!UICONTROL Visitor]** in un contenitore ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Visit]**.
* Il rapporto non supporta la segmentazione.
* Non ci sono dati corrispondenti ai criteri di segmentazione.

## Perché non riesco a visualizzare il segmento creato nel Gestore segmenti? {#invisible}

Possibili motivi:

* Alcune dimensioni sono disponibili solo in Data Warehouse e non nel Gestore segmenti.
* Il segmento viene controllato solo per una suite di rapporti specifica.
* Un segmento condiviso potrebbe essere stato eliminato da un altro utente.
* Impossibile caricare i segmenti a causa di un problema del centro dati o della cache del browser.
* Segmento non salvato.
* L&#39;indirizzo IP potrebbe essere bloccato alla fine dell&#39;utente.

## Perché i dati visualizzati dopo l’applicazione di un segmento sembrano errati? {#page-data}

Possibili motivi:

* Le regole o gli operatori non sono corretti per il risultato richiesto.
* Utilizzo errato dei contenitori nel segmento.
* Le variabili di traffico utilizzate per segmentare non sono impostate correttamente o sono scadute.
