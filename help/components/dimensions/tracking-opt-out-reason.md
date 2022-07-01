---
title: Tracking del motivo di rinuncia
description: Visualizza in anteprima quali dati verrebbero esclusi se si attivassero le impostazioni di privacy.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: b7209b914695423099266f5c507eaa34c2b98bc5
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# Tracking del motivo di rinuncia

*Questa pagina fa riferimento alla dimensione che ti consente di vedere il potenziale impatto dei dati derivante dall’abilitazione di determinate impostazioni della suite di rapporti. Non è correlato al [Servizio Opt-in Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=it).*

La dimensione &quot;Tracking opt-out reason&quot; funge da anteprima per i dati che verrebbero esclusi se avessi abilitato Impostazioni privacy. Questa dimensione viene utilizzata principalmente per determinare se l’implementazione risulterebbe compromessa se abilitata [Impostazioni privacy](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) in Impostazioni suite di rapporti.

Le implementazioni tipiche vedono l’1% o meno del traffico complessivo della suite di rapporti sotto questa dimensione se le Impostazioni privacy non sono ancora state abilitate. Percentuali superiori all’1% del traffico indicano un potenziale problema di implementazione che impedisce ad AppMeasurement di impostare cookie di prime parti.

## Popolare questa dimensione con i dati

Questa dimensione è preconfigurata per tutte le implementazioni che non sono ancora state abilitate [Impostazioni privacy](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). Se l’organizzazione ha già abilitato la **[!UICONTROL Remove users who have blocked all cookies]** sia per i browser desktop che per quelli mobili, questa dimensione non contiene dati.

## Elementi Dimension

Gli elementi del Dimension includono `"Cookies disabled by Desktop Browser"` e `"Cookies disabled by Mobile Browser"`.

* **Cookie disabilitati dal browser desktop**: Il visitatore ha bloccato i cookie utilizzando un browser desktop e **[!UICONTROL Remove users who have blocked all cookies on desktop browsers]** è disabilitato.
* **Cookie disabilitati dal browser mobile**: Il visitatore ha bloccato i cookie utilizzando un browser mobile e **[!UICONTROL Remove users who have blocked all cookies on mobile browsers]** è disabilitato.
