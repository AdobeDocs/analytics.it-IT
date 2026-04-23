---
description: Configura una suite di rapporti mappata da Experience Cloud da utilizzare in Advertising Analytics.
title: Abilitare suite di rapporti per Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 7%

---

# Abilitare suite di rapporti per Advertising Analytics

Per visualizzare i dati di ricerca di Advertising Analytics in Analytics, devi configurare ogni suite di rapporti mappata da Experience Cloud per il reporting di Advertising Analytics.

1. Passa a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Seleziona la suite di rapporti mappata sulla tua organizzazione Experience Cloud.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**.

   ![Generazione rapporti](assets/aa-reporting.png)

1. Selezionare **[!UICONTROL Unfamiliar with Advertising Analytics? Click here to learn more]** per ulteriori informazioni su Advertising Analytics.

1. Imposta l’allocazione e la scadenza della variabile AMO ID da utilizzare. Le variabili di conversione (eVar) consentono ad Adobe Analytics di attribuire eventi di successo a valori di variabili specifici. A volte, le variabili incontrano più di un valore prima di raggiungere un evento di successo. Per questi casi, l’allocazione determina a quale valore della variabile viene attribuito il merito per l’evento.

   | Impostazione | Definizione |
   |--- |--- |
   | **[!UICONTROL Allocation]** | Seleziona tra:<br/> **[!UICONTROL Original Value (First)]**: il primo valore visualizzato ottiene il credito di allocazione completo, indipendentemente dai valori successivi per tale variabile. <br/>**[!UICONTROL Most Recent (Last)]**: l&#39;ultimo valore visualizzato ottiene il credito di allocazione completo per l&#39;evento di successo, indipendentemente dalle variabili attivate prima di esso. |
   | **[!UICONTROL Expire After]** | Consente di specificare un periodo di tempo, o un evento, dopo la scadenza del valore eVar (ovvero, non riceve più crediti per eventi di successo).  Se un evento di successo si verifica dopo la scadenza di eVar, il merito per l’evento viene attribuito al valore None (nessun eVar era attivo). |

1. Fare clic su **[!UICONTROL Enable Advertising Analytics Reporting]** (prima volta) o su **[!UICONTROL Update Advertising Analytics Reporting]** (volte successive). La suite di rapporti è ora pronta per ricevere i dati di Advertising Analytics Search. Ora puoi [creare account Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
