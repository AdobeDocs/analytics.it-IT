---
description: 'null'
title: Abilita suite di rapporti per Advertising Analytics
uuid: 934f0e02-b5d7-4eca-93d8-92f95bd7014a
translation-type: tm+mt
source-git-commit: 2bebccbcd7435458ca29782802fa56ca09a6d4a2

---


# Abilita suite di rapporti per Advertising Analytics

Per visualizzare i dati di ricerca Analisi della pubblicità in Analytics, devi configurare ogni suite di rapporti mappata di Experience Cloud per i report Analisi della pubblicità.

1. [Mappa la suite di rapporti su un&#39;organizzazione](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).
1. Passa a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Seleziona la suite di rapporti mappata alla tua organizzazione Experience Cloud.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**.

   ![Generazione di rapporti](assets/aa_reporting.png)

   > [!IMPORTANT] L’ID AMO si riferisce alla variabile Adobe Advertising Cloud in cui verranno inseriti i dati di ricerca.

1. Impostate l’allocazione e la scadenza della variabile che desiderate utilizzare per l’ID AMO. Le variabili di conversione (eVar) consentono ad Adobe Analytics di attribuire eventi di successo a valori di variabili specifici. Talvolta, le variabili incontrano più valori prima di colpire un evento di successo. In questi casi, l&#39;allocazione determina il valore della variabile che riceve credito per l&#39;evento.

   | Impostazione | Definizione |
   |--- |--- |
   | Valore originale (Primo) | Il primo valore visualizzato ottiene un credito di allocazione completo, indipendentemente dai valori successivi per quella variabile. |
   |  Più recente (ultimo) | L&#39;ultimo valore visualizzato ottiene il credito di allocazione completo per l&#39;evento di successo, indipendentemente dalle variabili attivate prima di esso. |
   |  Scade dopo | Consente di specificare un periodo di tempo, o un evento, dopo il quale scade il valore eVar (ovvero, non riceve più credito per gli eventi di successo).  Se un evento di successo si verifica dopo la scadenza eVar, il valore None non riceve credito per l’evento (nessun eVar è attivo). |

1. Fate clic **[!UICONTROL Enable Advertising Analytics Reporting]** (prima volta) o **[!UICONTROL Update Advertising Analytics Reporting]** (ora successiva). La tua suite di rapporti è ora pronta per ricevere i dati di ricerca di Analisi della pubblicità. Non sei pronto a [creare account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)pubblicitari.

