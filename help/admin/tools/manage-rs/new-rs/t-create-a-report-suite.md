---
description: Creare un contenitore di base per la raccolta di dati in Adobe Analytics
title: Creare una suite di rapporti
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
TQID: https://experienceleague.adobe.com/ZmPcYHvXOhaXXnqsSVUh1bpvignxomS3d4S76iMCAa4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 302
ht-degree: 88%

---

# Creare una suite di rapporti

Una suite di rapporti è un silos di dati utilizzati da Adobe Analytics per estrarre i rapporti. Un’organizzazione può avere molte suite di rapporti, ciascuna contenente set di dati diversi. Anche se in passato le suite di rapporti separate erano importanti, avere una singola suite di rapporti è diventato più vantaggioso. L’introduzione di [suite di rapporti virtuali](/help/components/vrs/vrs-about.md#virtual-report-suites) e i tempi di elaborazione del rapporto consentono agli amministratori di creare sottoinsiemi di dati personalizzati, consentendo la flessibilità di ottenere dati globali e specifici per il sito.

Questo articolo è pensato per gli amministratori a livello di sistema o per gli amministratori di Adobe Analytics in preparazione alla raccolta dei dati.

## Prerequisiti

[Guida per il primo amministratore di Adobe Analytics](/help/admin/admin-console/first-admin-guide.md): verificare che un amministratore a livello di sistema ti abbia concesso l&#39;accesso ad Adobe Analytics tramite CX Enterprise Admin Console.

## Creare una suite di rapporti {#create-report-suite}

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Fai clic su **[!UICONTROL Add Report Suite]**.
1. Seleziona un modello predefinito o una suite di rapporti esistente da utilizzare come [modello](/help/admin/tools/manage-rs/rs-templates/report-suite-templates.md).

   >[!NOTE]
   >
   >È possibile copiare solo le impostazioni, non i dati. Se l&#39;Assistenza clienti sta copiando le impostazioni, dovrai fornire una conferma scritta alla liberatoria fornita dall&#39;Assistenza clienti sui rischi implicati. Consulta [Impostazioni non copiate da una suite di rapporti di origine](/help/admin/tools/manage-rs/new-rs/settings-not-copied-from-rs.md) per ulteriori informazioni.

1. Compila i campi descritti in [Nuova suite di rapporti.](/help/admin/tools/manage-rs/new-rs/new-report-suite.md)
1. Fai clic su **[!UICONTROL Create Report Suite]**.

Un ID suite di rapporti ha una lunghezza massima di 40 byte. Un nome descrittivo della suite di rapporti ha una lunghezza massima di 255 byte.

## Risoluzione dei problemi

**Dopo aver effettuato l&#39;accesso a CX Enterprise, l&#39;icona Analytics è disattivata.**

Ciò significa che al tuo account non sono state concesse le autorizzazioni corrette per Analytics. Lavora con un amministratore a livello di sistema nella tua organizzazione per assicurarti di appartenere a un profilo con autorizzazioni adeguate per accedere ad Adobe Analytics.

## Passaggi successivi

[Crea una proprietà tag Adobe Analytics ](/help/implement/launch/create-analytics-property.md): consente di creare un’area per gestire l’implementazione di Analytics.
