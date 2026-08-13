---
title: Tracking del motivo di rinuncia
description: Visualizza in anteprima quali dati verrebbero esclusi se abiliti le Impostazioni privacy.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
TQID: https://experienceleague.adobe.com/mFYYrj4iBWBi87sErHnWTYXce3lUhV0pwUt63x3vfnY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 254
ht-degree: 10%

---

# Tracking del motivo di rinuncia

*Questa pagina fa riferimento alla [dimensione](overview.md) che consente di visualizzare il potenziale impatto dei dati derivante dall&#39;abilitazione di alcune impostazioni della suite di rapporti. Non è correlato al servizio Opt-in [Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=it).*

La dimensione &quot;Motivo rinuncia al tracciamento&quot; funge da anteprima dei dati che verrebbero esclusi se avessi abilitato le Impostazioni privacy. Questa dimensione viene utilizzata principalmente per determinare se l&#39;implementazione potrebbe essere influenzata negativamente se hai abilitato [Impostazioni privacy](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) in Impostazioni suite di rapporti.

Se le impostazioni di privacy non sono ancora state abilitate, le implementazioni tipiche visualizzano l’1% o meno del traffico complessivo della suite di rapporti in questa dimensione. Percentuali superiori all’1% di tutto il traffico suggeriscono un potenziale problema di implementazione che impedisce ad AppMeasurement di impostare cookie di prime parti.

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni che non hanno ancora abilitato [Impostazioni privacy](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). Se l&#39;organizzazione ha già abilitato l&#39;impostazione **[!UICONTROL Remove users who have blocked all cookies]** sia per i browser desktop che per quelli mobili, questa dimensione non contiene dati.

## Elementi dimensionali

Gli elementi Dimension includono `"Cookies disabled by Desktop Browser"` e `"Cookies disabled by Mobile Browser"`.

* **Cookie disabilitati dal browser desktop**: il visitatore ha bloccato i cookie utilizzando un browser desktop e **[!UICONTROL Remove users who have blocked all cookies on desktop browsers]** è disabilitato.
* **Cookie disabilitati dal browser mobile**: il visitatore ha bloccato i cookie utilizzando un browser mobile e **[!UICONTROL Remove users who have blocked all cookies on mobile browsers]** è disabilitato.
