---
description: I filtri URL interni identificano i referenti considerati interni al sito. Agevolano la compilazione dei dati nei rapporti sulle origini del traffico e aiutano a filtrare il traffico interno.
title: Filtri URL interni
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
TQID: https://experienceleague.adobe.com/J78ImTXRPFm6aMHqrxJXZOUVyG-ETnutipYYo2wrofc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 202
ht-degree: 34%

---

# Filtri URL interni

I filtri URL interni consentono di identificare i referenti considerati interni al sito. Agevolano la compilazione dei dati nei rapporti sulle origini del traffico e aiutano a filtrare il traffico interno.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**

Un referente o pagina di riferimento è in genere la pagina da cui un visitatore è entrato nel sito. Per evitare alterazioni dei dati, puoi filtrare i referenti interni. Le dimensioni che si basano sui filtri URL interni includono [Referrer](/help/components/dimensions/referrer.md), [Dominio di riferimento](/help/components/dimensions/referring-domain.md), [Canali di marketing](/help/components/dimensions/marketing-channel.md) e altre dimensioni dell&#39;origine del traffico.

[Le regole di elaborazione del canale di marketing](../marketing-channels/mc-proc-rules.md) forniscono &quot;[!UICONTROL Matches internal URL filters]&quot; come criteri di regola possibili.

>[!IMPORTANT]
>
>Alcune suite di rapporti hanno un filtro URL interno di un punto (`.`) configurato per impostazione predefinita. Quando questo filtro esiste, tutto il traffico viene classificato come interno. I rapporti del referente non funzionano finché questo filtro non viene rimosso e sostituito con uno o più domini interni desiderati.

* Visualizza tutti i filtri esistenti nella sezione **[!UICONTROL Current Filters]**.
* Aggiungere un filtro utilizzando la casella di testo nella sezione **[!UICONTROL Add Filter]**, quindi fare clic su **[!UICONTROL Add]**.

I filtri operano utilizzando la logica **contains** rispetto all&#39;URL completo. Adobe consiglia di omettere il protocollo (`https://`) e i sottodomini durante la creazione dei filtri, a meno che il traffico da sottodomini separati non sia desiderato come traffico esterno.
