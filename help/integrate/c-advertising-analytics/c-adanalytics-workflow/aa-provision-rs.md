---
description: Configura un Experience Cloud di suite di rapporti mappata da utilizzare in Advertising Analytics.
title: Abilitare suite di rapporti per Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 6%

---

# Abilitare suite di rapporti per Advertising Analytics

Per visualizzare i dati di ricerca di Advertising Analytics in Analytics, devi configurare ogni suite di rapporti mappata dall’Experience Cloud per la generazione di rapporti di Advertising Analytics.

1. Passa a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Seleziona la suite di rapporti mappata sulla tua organizzazione di Experienci Cloud.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**.

   ![Reporting](assets/aa-reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID fa riferimento alla variabile Adobe Advertising Cloud (nota anche come Adobe Media Optimizer) in cui verranno inseriti i dati di ricerca.

1. Seleziona **[!UICONTROL Unfamiliar with Advertising Analytics? Click here to learn more]** per ulteriori informazioni su Advertising Analytics.

1. Imposta l’allocazione e la scadenza della variabile AMO ID da utilizzare. Le variabili di conversione (eVar) consentono ad Adobe Analytics di attribuire eventi di successo a valori di variabili specifici. A volte, le variabili incontrano più di un valore prima di raggiungere un evento di successo. Per questi casi, l’allocazione determina a quale valore della variabile viene attribuito il merito per l’evento.

   | Impostazione | Definizione |
   |--- |--- |
   | **[!UICONTROL Allocation]** | Seleziona tra:<br/> **[!UICONTROL Original Value (First)]**: il primo valore visualizzato ottiene il credito di allocazione completo, indipendentemente dai valori successivi per tale variabile. <br/>**[!UICONTROL Most Recent (Last)]**: all’ultimo valore visualizzato viene assegnato il merito di allocazione completo per l’evento di successo, indipendentemente dalle variabili attivate prima di esso. |
   | **[!UICONTROL Expire After]** | Consente di specificare un periodo di tempo, o un evento, dopo la scadenza del valore eVar (ovvero, non riceve più crediti per eventi di successo).  Se un evento di successo si verifica dopo la scadenza eVar, il merito per l’evento viene attribuito al valore None (nessun eVar è attivo). |

1. Clic **[!UICONTROL Enable Advertising Analytics Reporting]** (la prima volta), oppure **[!UICONTROL Update Advertising Analytics Reporting]** (negli orari successivi). La suite di rapporti è ora pronta per ricevere i dati di Advertising Analytics Search. Ora sei pronto per [creare account Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
