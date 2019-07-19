---
description: nulle
seo-description: nulle
seo-title: Abilita suite di rapporti per analisi pubblicità
title: Abilita suite di rapporti per analisi pubblicità
uuid: 934 f 0 e 02-b 5 d 7-4 eca -93 d 8-92 f 95 bd 7014 a
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Abilita suite di rapporti per analisi pubblicità

Per visualizzare i dati di ricerca di Analytics pubblicitari in Analytics, devi configurare ogni suite di rapporti mappati Experience Cloud per report Analytics pubblicitari.

1. [Mappate la suite di rapporti su un'organizzazione](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html).
1. Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.

1. Select the report suite that is [mapped to your Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html).
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Advertising Analytics Configuration]**.

   ![](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID fa riferimento alla variabile Adobe Advertising Cloud in cui verranno inseriti i dati di ricerca.

1. Impostate l'allocazione e la scadenza della variabile per utilizzare la variabile AMO ID. Le variabili di conversione (evars) consentono ad Adobe Analytics di attribuire eventi di successo a valori specifici delle variabili. A volte, le variabili hanno più di un valore prima di toccare un evento di successo. Per questi casi, l'allocazione determina quale valore della variabile ottiene credito per l'evento.

   | Impostazione | Definizione |
   |--- |--- |
   | Valore originale (primo) | Il primo valore visualizzato ottiene il credito completo di assegnazione, indipendentemente dal valore successivo di tale variabile. |
   | Più recente (ultimo) | L'ultimo valore visualizzato ottiene il credito totale di allocazione per l'evento success, indipendentemente dalle variabili che sono state attivate prima. |
   | Scade dopo | Consente di specificare un periodo di tempo, o un evento, dopo la scadenza del valore evar (ovvero, non ricevono più credito per eventi di successo). Se un evento di successo si verifica dopo la scadenza evar, il valore None non riceve credito per l'evento (nessuna evar è attiva). |

1. Click **[!UICONTROL Enable Advertising Analytics Reporting]** (first time), or **[!UICONTROL Update Advertising Analytics Reporting]** (subsequent times). La tua suite di rapporti è ora pronta per ricevere i dati di ricerca Analisi annunci. You are no ready to [create Advertising Accounts](../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md#concept_1958E8C15C334E8B9DC510EC8D5DCA7C).

