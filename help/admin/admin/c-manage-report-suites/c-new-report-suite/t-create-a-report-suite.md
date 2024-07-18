---
description: Creare un contenitore di base per la raccolta di dati in Adobe Analytics
title: Creare una suite di rapporti
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 100%

---

# Creare una suite di rapporti

Una suite di rapporti è un silos di dati utilizzati da Adobe Analytics per estrarre i rapporti. Un’organizzazione può avere molte suite di rapporti, ciascuna contenente set di dati diversi. Anche se in passato le suite di rapporti separate erano importanti, avere una singola suite di rapporti è diventato più vantaggioso. L’introduzione di [suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=it#virtual-report-suites) e i tempi di elaborazione del rapporto consentono agli amministratori di creare sottoinsiemi di dati personalizzati, consentendo la flessibilità di ottenere dati globali e specifici per il sito.

Questo articolo è pensato per gli amministratori a livello di sistema o per gli amministratori di Adobe Analytics in preparazione alla raccolta dei dati.

## Prerequisiti

[Guida per il primo amministratore di Adobe Analytics](/help/admin/admin-console/first-admin-guide.md): assicurati che un amministratore a livello di sistema ti abbia concesso l’accesso ad Adobe Analytics tramite l’Admin Console di Experience Cloud.

## Creare una suite di rapporti {#create-report-suite}

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Fai clic su **[!UICONTROL Create New]** > **[!UICONTROL Report Suite]**.
1. Seleziona un modello predefinito o una suite di rapporti esistente da utilizzare come [modello](/help/admin/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md).

   >[!NOTE]
   >
   >È possibile copiare solo le impostazioni, non i dati. Se l&#39;Assistenza clienti sta copiando le impostazioni, dovrai fornire una conferma scritta alla liberatoria fornita dall&#39;Assistenza clienti sui rischi implicati. Consulta [Impostazioni non copiate da una suite di rapporti di origine](/help/admin/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md) per ulteriori informazioni.

1. Compila i campi descritti in [Nuova suite di rapporti.](/help/admin/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
1. Fai clic su **[!UICONTROL Create Report Suite]**.

Un ID suite di rapporti ha una lunghezza massima di 40 byte. Un nome descrittivo della suite di rapporti ha una lunghezza massima di 255 byte.

## Risoluzione dei problemi

**Dopo aver effettuato l’accesso in Experience Cloud, l’icona Analytics è disattivata.**

Ciò significa che al tuo account non sono state concesse le autorizzazioni corrette per Analytics. Lavora con un amministratore a livello di sistema nella tua organizzazione per assicurarti di appartenere a un profilo con autorizzazioni adeguate per accedere ad Adobe Analytics.

## Passaggi successivi

[Crea una proprietà tag Adobe Analytics ](/help/implement/launch/create-analytics-property.md): consente di creare un’area per gestire l’implementazione di Analytics.
