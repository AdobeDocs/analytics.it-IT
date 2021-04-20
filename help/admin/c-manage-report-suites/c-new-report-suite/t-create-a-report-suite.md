---
description: Creare un contenitore di base per la raccolta di dati in Adobe Analytics
title: Creare una suite di rapporti
feature: Admin Tools
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 5%

---

# Creare una suite di rapporti

Una suite di rapporti è un silos di dati utilizzati da Adobe Analytics per richiamare rapporti. Un’organizzazione può avere molte suite di rapporti, ciascuna contenente set di dati diversi. Anche se in passato le suite di rapporti separate erano importanti, avere una singola suite di rapporti è diventato più vantaggioso. L’introduzione di [suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites) e l’elaborazione dei tempi di report consente agli amministratori di creare sottoinsiemi di dati personalizzati, consentendo la flessibilità di ottenere sia dati globali che specifici per il sito.

Questo articolo è progettato per gli amministratori a livello di sistema o per gli amministratori di analytics in preparazione alla raccolta dei dati.

## Prerequisiti

[Prima guida](/help/admin/admin-console/first-admin-guide.md) dell’amministratore di Adobe Analytics: Assicurati che un amministratore a livello di sistema ti abbia concesso l’accesso ad Adobe Analytics tramite l’Admin Console di Experience Cloud.

## Creare una suite di rapporti {#create-report-suite}

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Fai clic su **[!UICONTROL Create New]** > **[!UICONTROL Report Suite]**.
1. Per copiare le impostazioni di una suite di rapporti, nell&#39;elenco dei modelli selezionare un modello predefinito o una suite di rapporti esistente da utilizzare come modello [.](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)

   >[!NOTE]
   >
   >È possibile copiare solo le impostazioni, non i dati. Se l&#39;Assistenza clienti sta copiando le impostazioni, dovrai fornire una conferma scritta alla liberatoria fornita dall&#39;Assistenza clienti sui rischi implicati. Per ulteriori informazioni, consulta [Impostazioni non copiate da una suite di rapporti di origine](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md) .

1. Compila i campi descritti in [Nuova suite di rapporti.](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
1. Fai clic su **[!UICONTROL Create Report Suite]**.

Un ID suite di rapporti ha una lunghezza massima di 40 byte. Un nome descrittivo della suite di rapporti ha una lunghezza massima di 255 byte.

## Risoluzione dei problemi

**Dopo aver effettuato l’accesso all’Experience Cloud, l’icona Analytics è disattivata.**

Ciò significa che al tuo account non sono state concesse le autorizzazioni corrette per Analytics. Lavora con un amministratore a livello di sistema nella tua organizzazione per assicurarti di appartenere a un profilo con autorizzazioni adeguate per accedere ad Adobe Analytics.

**Dopo aver effettuato l’accesso ad Adobe Analytics, manca il menu a comparsa e il menu a discesa &quot;Benvenuti in Adobe Analytics&quot;.**

Assicurati di aver effettuato l’accesso tramite l’Experience Cloud e non tramite my.omniture.com. L’utente che accede tramite my.omniture.com non dispone della procedura guidata di configurazione della suite di rapporti.

## Passaggi successivi

[Crea e configura una proprietà per Adobe Analytics in Launch](/help/implement/launch/create-analytics-property.md): Creare un’area per gestire l’implementazione di Analytics
