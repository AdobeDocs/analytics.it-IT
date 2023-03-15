---
description: Configura un Experience Cloud di suite di rapporti mappata da utilizzare in Advertising Analytics.
title: Abilita suite di rapporti per Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 17%

---

# Abilita suite di rapporti per Advertising Analytics

Per visualizzare i dati di ricerca di Advertising Analytics in Analytics, devi configurare ogni suite di rapporti mappata dall’Experience Cloud per il reporting di Advertising Analytics.

1. Passa a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

1. Seleziona la suite di rapporti mappata sulla tua organizzazione di Experienci Cloud.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**.

   ![Reporting](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID si riferisce alla variabile Adobe Advertising Cloud in cui verranno inseriti i dati di ricerca.

1. Imposta l’allocazione e la scadenza della variabile AMO ID da utilizzare. Le variabili di conversione (eVar) consentono ad Adobe Analytics di attribuire eventi di successo a valori di variabili specifici. A volte, le variabili incontrano più di un valore prima di raggiungere un evento di successo. Per questi casi, l’allocazione determina a quale valore della variabile viene attribuito il merito per l’evento.

   | Impostazione | Definizione |
   |--- |--- |
   | Valore originale (primo) | Il primo valore visualizzato ottiene il credito di allocazione completo, indipendentemente dai valori successivi per tale variabile. |
   | Più recente (ultimo) | L’ultimo valore visualizzato ottiene il merito di allocazione completo per l’evento di successo, indipendentemente dalle variabili attivate prima di esso. |
   | Expire After (Scade dopo) | Consente di specificare un periodo di tempo, o un evento, dopo la scadenza del valore eVar (ad esempio, non riceve più crediti per eventi di successo).  Se un evento di successo si verifica dopo la scadenza dell’eVar, il merito per l’evento viene attribuito al valore None (nessun eVar è attivo).  |

1. Clic **[!UICONTROL Enable Advertising Analytics Reporting]** (la prima volta), oppure **[!UICONTROL Update Advertising Analytics Reporting]** (negli orari successivi). La suite di rapporti è ora pronta per ricevere i dati di Advertising Analytics Search. Non sei pronto a [creare account Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
