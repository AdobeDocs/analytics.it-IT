---
description: I filtri URL interni identificano i referenti considerati interni al sito. Agevolano la compilazione dei dati nei rapporti sulle origini del traffico e aiutano a filtrare il traffico interno.
title: Filtri URL interni
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 34%

---


# Filtri URL interni

I filtri URL interni consentono di identificare i referenti considerati interni al sito. Agevolano la compilazione dei dati nei rapporti sulle origini del traffico e aiutano a filtrare il traffico interno.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**

Un referente o pagina di riferimento è in genere la pagina da cui un visitatore è entrato nel sito. Per evitare alterazioni dei dati, puoi filtrare i referenti interni. I Dimension che si basano su filtri URL interni includono [Referrer](/help/components/dimensions/referrer.md), [Dominio di riferimento](/help/components/dimensions/referring-domain.md), [Canali di marketing](/help/components/dimensions/marketing-channel.md) e altre dimensioni dell&#39;origine del traffico.

[Le regole di elaborazione del canale di marketing](../marketing-channels/c-rules.md) forniscono &quot;[!UICONTROL Matches internal URL filters]&quot; come criteri di regola possibili.

>[!IMPORTANT]
>
>Alcune suite di rapporti hanno un filtro URL interno di un punto (`.`) configurato per impostazione predefinita. Quando questo filtro esiste, tutto il traffico viene classificato come interno. I rapporti del referente non funzionano finché questo filtro non viene rimosso e sostituito con uno o più domini interni desiderati.

* Visualizza tutti i filtri esistenti nella sezione **[!UICONTROL Current Filters]**.
* Aggiungere un filtro utilizzando la casella di testo nella sezione **[!UICONTROL Add Filter]**, quindi fare clic su **[!UICONTROL Add]**.

I filtri operano utilizzando la logica **contains** rispetto all&#39;URL completo. L&#39;Adobe consiglia di omettere il protocollo (`https://`) e i sottodomini durante la creazione dei filtri, a meno che il traffico da sottodomini separati non sia desiderato come traffico esterno.
