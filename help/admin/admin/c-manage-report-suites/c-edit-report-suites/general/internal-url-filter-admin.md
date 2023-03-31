---
description: I filtri URL interni identificano i referenti considerati interni al sito. Agevolano la compilazione dei dati nei rapporti sulle origini del traffico e aiutano a filtrare il traffico interno.
title: Filtri URL interni
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 2beb4cd38fc8b48e2b34468a4570f7168aeacb78
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 32%

---


# Filtri URL interni

I filtri URL interni ti consentono di identificare i referenti che ritieni interni al sito. Agevolano la compilazione dei dati nei rapporti sulle origini del traffico e aiutano a filtrare il traffico interno.

Un referente o pagina di riferimento è in genere la pagina da cui un visitatore è entrato nel sito. Per evitare alterazioni dei dati, puoi filtrare i referenti interni. I rapporti escludono i referenti filtrati dalla dimensione [Referenti](/help/components/dimensions/referrer.md), dalla dimensione [Domini di riferimento](/help/components/dimensions/referring-domain.md) e da altre dimensioni dell’origine del traffico.

## Visualizzare i filtri URL interni esistenti

>[!NOTE]
>
>Alcune suite di rapporti hanno un filtro URL interno di un punto (.) configurato per impostazione predefinita. Quando questo filtro esiste, tutto il traffico viene classificato come interno. I rapporti referente non funzionano fino al punto (.) il filtro viene rimosso.

Per verificare quali filtri URL interni sono configurati per una suite di rapporti: <!-- I don't see the period in my instance? Is the following information valid? "To avoid this, remove the rule listing a period (.) as a filter, and add your own site. The reason why a period is the default internal URL filter is to allow data to be collected in the Pages report. If hits do not match internal URL filters, all pages come up as Other. A period is always somewhere in the URL, which guarantees the Pages report is populated.")-->

1. Seleziona **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** per accedere a Report Suite Manager.

1. Seleziona la suite di rapporti in cui desideri verificare quali filtri URL interni sono configurati, quindi seleziona **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**.

   Tutti i filtri esistenti sono elencati nella [!UICONTROL **Filtri correnti**] sezione .

## Aggiungere un filtro URL interno a una suite di rapporti

1. Seleziona **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** per accedere a Report Suite Manager.

1. Seleziona la suite di rapporti in cui desideri aggiungere un filtro URL interno, quindi seleziona **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**.

1. Nella sezione Aggiungi filtro del campo fornito inizia a digitare l’URL della pagina da filtrare, quindi seleziona [!UICONTROL **Aggiungi**].

   L’URL aggiunto è ora visibile nel [!UICONTROL **Filtri correnti**] sezione .
