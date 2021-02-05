---
description: Creare un contenitore di base per la raccolta dei dati in  Adobe Analytics
title: Creare una suite di rapporti
topic: Admin tools
translation-type: tm+mt
source-git-commit: 8ddd49ad894547d888efc513983e615d138ed13c
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---


# Creare una suite di rapporti

Una suite di rapporti è un silo di dati che  Adobe Analytics utilizza per estrarre i rapporti. Un&#39;organizzazione può disporre di numerose suite di rapporti, ciascuna delle quali contiene set di dati diversi. Sebbene in passato fossero importanti suite di rapporti separate, avere una singola suite di rapporti è diventato più vantaggioso. L&#39;introduzione di [suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites) e l&#39;elaborazione del tempo di rapporto consente agli amministratori di creare sottoinsiemi di dati personali, consentendo la flessibilità di ottenere sia dati globali che specifici per il sito.

Questo articolo è progettato per amministratori di sistema o amministratori di analisi per prepararsi alla raccolta dei dati.

## Prerequisiti

[ Adobe Analytics First Admin Guide](/help/admin/admin-console/first-admin-guide.md): Assicurati che un amministratore a livello di sistema ti abbia concesso l’accesso a  Adobe Analytics tramite il Experience Cloud   Admin Console.

## Creare una suite di rapporti {#create-report-suite}

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Fai clic su **[!UICONTROL Create New]** > **[!UICONTROL Report Suite]**.
1. Per copiare le impostazioni di una suite di rapporti, nell&#39;elenco dei modelli selezionare un modello predefinito o una suite di rapporti esistente da utilizzare come modello [.](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)

   >[!NOTE]
   >
   >È possibile copiare solo le impostazioni, non i dati. Se l&#39;Assistenza clienti sta copiando le impostazioni, dovrai fornire una conferma scritta alla dichiarazione di non responsabilità fornita dall&#39;Assistenza clienti sui rischi implicati. Per ulteriori informazioni, vedere [Impostazioni non copiate da una suite di rapporti di origine](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md).

1. Compila i campi descritti in [Nuova suite di rapporti.](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
1. Fai clic su **[!UICONTROL Create Report Suite]**.

Un ID suite di rapporti ha una lunghezza massima di 40 byte. Un nome descrittivo per le suite di rapporti ha una lunghezza massima di 255 byte.

## Risoluzione dei problemi

**Dopo aver effettuato l&#39;accesso al Experience Cloud , l&#39;icona Analytics è disattivata.**

Ciò significa che al tuo account non sono state concesse le autorizzazioni corrette per Analytics. Consultate un amministratore a livello di sistema nella vostra organizzazione per assicurarvi di appartenere a un profilo con autorizzazioni adeguate per accedere  Adobe Analytics.

**Dopo aver effettuato l&#39;accesso a  Adobe Analytics, il menu a comparsa e il menu a discesa &#39;Benvenuti  Adobe Analytics&#39; risulta mancante.**

Assicurati di aver effettuato l’accesso tramite l’Experience Cloud  e non tramite my.omniture.com. L&#39;utente che accede tramite my.omniture.com non dispone della procedura guidata di configurazione della suite di rapporti.

## Passaggi successivi

[Crea e configura una proprietà per  Adobe Analytics in Launch](/help/implement/launch/create-analytics-property.md): Creare un&#39;area per gestire l&#39;implementazione di Analytics