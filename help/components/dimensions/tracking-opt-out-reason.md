---
title: Tracking del motivo di rinuncia
description: Visualizza in anteprima quali dati verrebbero esclusi se abiliti le Impostazioni privacy.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: b7209b914695423099266f5c507eaa34c2b98bc5
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 6%

---

# Tracking del motivo di rinuncia

*Questa pagina fa riferimento alla dimensione che consente di visualizzare il potenziale impatto dei dati derivante dall’abilitazione di determinate impostazioni della suite di rapporti. Non è correlato al [Servizio Opt-in per Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=it).*

La dimensione &quot;Motivo rinuncia al tracciamento&quot; funge da anteprima dei dati che verrebbero esclusi se avessi abilitato le Impostazioni privacy. Questa dimensione viene utilizzata principalmente per determinare se l’implementazione potrebbe essere influenzata negativamente se è abilitata [Impostazioni privacy](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) in Impostazioni suite di rapporti.

Se le impostazioni di privacy non sono ancora state abilitate, le implementazioni tipiche visualizzano l’1% o meno del traffico complessivo della suite di rapporti in questa dimensione. Percentuali superiori all’1% di tutto il traffico suggeriscono un potenziale problema di implementazione che impedisce ad AppMeasurement di impostare cookie di prime parti.

## Popola questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni che non sono ancora abilitate [Impostazioni privacy](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). Se la tua organizzazione ha già abilitato **[!UICONTROL Remove users who have blocked all cookies]** per browser desktop e mobili, questa dimensione non contiene dati.

## Elementi dimensionali

Gli elementi del Dimension includono `"Cookies disabled by Desktop Browser"` e `"Cookies disabled by Mobile Browser"`.

* **Cookie disabilitati dal browser desktop**: il visitatore ha bloccato i cookie utilizzando un browser desktop e **[!UICONTROL Remove users who have blocked all cookies on desktop browsers]** è disabilitato.
* **Cookie disabilitati dal browser mobile**: il visitatore ha bloccato i cookie utilizzando un browser mobile e **[!UICONTROL Remove users who have blocked all cookies on mobile browsers]** è disabilitato.
