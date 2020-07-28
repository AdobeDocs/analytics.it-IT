---
description: 'null'
title: Abilita suite di rapporti per Advertising Analytics
uuid: 934f0e02-b5d7-4eca-93d8-92f95bd7014a
translation-type: tm+mt
source-git-commit: a492de4ccbcd6f3f8ca81c9fecbcca4780e0f589
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 18%

---


# Abilita suite di rapporti per Advertising Analytics

Per visualizzare  dati di ricerca Advertising Analytics in  Analytics, è necessario configurare ogni  suite di rapporti con mappatura Experience Cloud per  rapporti Advertising Analytics.

1. [Mappa la suite di rapporti su un&#39;organizzazione](https://docs.adobe.com/content/help/it-IT/core-services/interface/about-core-services/report-suite-mapping.html).
1. Passa a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Seleziona la suite di rapporti mappata all&#39;organizzazione  Experience Cloud.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**.

   ![Generazione di rapporti](assets/aa_reporting.png)

   >[!IMPORTANT] L’ID AMO si riferisce alla variabile Adobe Advertising Cloud in cui verranno inseriti i dati di ricerca.

1. Impostate l’allocazione e la scadenza della variabile che desiderate utilizzare per l’ID AMO. Le variabili di conversione (eVar) consentono  Adobe Analytics di attribuire eventi di successo a valori variabili specifici. Talvolta, le variabili rilevano più di un valore prima di colpire un evento di successo. In questi casi, l&#39;allocazione determina il valore della variabile che riceve credito per l&#39;evento.

   | Impostazione | Definizione |
   |--- |--- |
   | Valore originale (Primo) | Il primo valore visualizzato ottiene un credito di allocazione completo, indipendentemente dai valori successivi per quella variabile. |
   | Più recente (ultimo) | L&#39;ultimo valore visualizzato ottiene il credito di allocazione completo per l&#39;evento di successo, indipendentemente dalle variabili che sono state attivate prima di esso. |
   | Scade dopo | Consente di specificare un periodo di tempo, o un evento, dopo il quale scade il valore del eVar  (ovvero, non riceve più credito per gli eventi di successo).  Se un evento di successo si verifica dopo la scadenza eVar, il valore None non riceve credito per l’evento (nessun eVar è attivo). |

1. Fate clic **[!UICONTROL Enable Advertising Analytics Reporting]** (prima volta) o **[!UICONTROL Update Advertising Analytics Reporting]** (ora successiva). La suite di rapporti è ora pronta per ricevere  dati di Advertising Analytics Search. Non sei pronto a [creare account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)pubblicitari.

