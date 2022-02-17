---
description: Configura un Experience Cloud di suite di rapporti mappata da utilizzare in Advertising Analytics.
title: Abilita suite di rapporti per Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 15%

---

# Abilita suite di rapporti per Advertising Analytics

Per visualizzare qualsiasi dato di ricerca Advertising Analytics in Analytics, devi configurare ogni suite di rapporti mappata su Experience Cloud per il reporting di Advertising Analytics.

1. Passa a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Seleziona la suite di rapporti mappata nell’organizzazione Experience Cloud.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**.

   ![Generazione di rapporti](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID si riferisce alla variabile Adobe Advertising Cloud in cui verranno inseriti i dati di ricerca.

1. Imposta l’allocazione e la scadenza della variabile che desideri utilizzare la variabile AMO ID. Le variabili di conversione (eVar) consentono ad Adobe Analytics di attribuire gli eventi di successo a valori variabili specifici. A volte, le variabili incontrano più di un valore prima di colpire un evento di successo. In questi casi, l&#39;allocazione determina il valore della variabile che ottiene il credito per l&#39;evento.

   | Impostazione | Definizione |
   |--- |--- |
   | Valore originale (primo) | Il primo valore visualizzato ottiene il credito di allocazione completo, indipendentemente dai valori successivi per quella variabile. |
   | Più recente (ultimo) | L&#39;ultimo valore visto ottiene il pieno credito di allocazione per l&#39;evento di successo, indipendentemente dalle variabili che sono state attivate prima di esso. |
   | Scade dopo | Consente di specificare un periodo di tempo, o un evento, dopo la scadenza del valore eVar (ovvero, non riceve più crediti per eventi di successo).  Se un evento di successo si verifica dopo la scadenza eVar, il valore None non riceve credito per l’evento (nessun eVar è attivo). |

1. Fai clic su **[!UICONTROL Enable Advertising Analytics Reporting]** (prima volta), oppure **[!UICONTROL Update Advertising Analytics Reporting]** (ore successive). La suite di rapporti è ora pronta per ricevere i dati di Advertising Analytics Search. Non sei pronto a [creare account pubblicitari](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
