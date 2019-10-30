---
description: nulle
seo-description: nulle
seo-title: Abilita suite di rapporti per Advertising Analytics
title: Abilita suite di rapporti per Advertising Analytics
uuid: 934f0e02-b5d7-4eca-93d8-92f95bd7014a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Abilita suite di rapporti per Advertising Analytics

Per visualizzare i dati di ricerca Analisi della pubblicità in Analytics, devi configurare ogni suite di rapporti mappata di Experience Cloud per i report Analisi della pubblicità.

1. [Mappa la suite di rapporti su un'organizzazione](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html).
1. Passa a **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.

1. Seleziona la suite di rapporti [mappata alla tua organizzazione](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html)Experience Cloud.
1. Fai clic su **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Advertising Analytics Configuration]**.

   ![](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >L’ID AMO si riferisce alla variabile Adobe Advertising Cloud in cui verranno inseriti i dati di ricerca.

1. Impostate l’allocazione e la scadenza della variabile che desiderate utilizzare per l’ID AMO. Le variabili di conversione (eVar) consentono ad Adobe Analytics di attribuire eventi di successo a valori di variabili specifici. Talvolta, le variabili incontrano più valori prima di colpire un evento di successo. In questi casi, l'allocazione determina il valore della variabile che riceve credito per l'evento.

   | Impostazione | Definizione |
   |--- |--- |
   | Valore originale (Primo) | Il primo valore visualizzato ottiene un credito di allocazione completo, indipendentemente dai valori successivi per quella variabile. |
   | Più recente (ultimo) | L'ultimo valore visualizzato ottiene il credito di allocazione completo per l'evento di successo, indipendentemente dalle variabili attivate prima di esso. |
   | Scade dopo | Consente di specificare un periodo di tempo, o un evento, dopo il quale scade il valore eVar (ovvero, non riceve più credito per gli eventi di successo).  Se un evento di successo si verifica dopo la scadenza eVar, il valore None non riceve credito per l’evento (nessun eVar è attivo). |

1. Fate clic **[!UICONTROL Enable Advertising Analytics Reporting]** (prima volta) o **[!UICONTROL Update Advertising Analytics Reporting]** (ora successiva). La tua suite di rapporti è ora pronta per ricevere i dati di ricerca di Analisi della pubblicità. Non sei pronto a [creare account](../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md#concept_1958E8C15C334E8B9DC510EC8D5DCA7C)pubblicitari.

