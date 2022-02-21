---
title: Mappare manualmente i dati XDM su Analytics
description: Mappare manualmente i dati XDM da Experience Platform ad Adobe Analytics
feature: AEP Edge
exl-id: 6d973b35-1558-435c-9ae5-80c012d4e7ba
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 5%

---

# Mappare manualmente i dati XDM su Analytics

L’SDK per web di Adobe Experience Platform (AEP) include strumenti che consentono di mappare manualmente i dati tra Platform e Analytics.

Per i dati XDM che non vengono mappati automaticamente in Analytics, puoi aggiungere [dati contestuali](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/contextdata.html) per abbinare [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=it). Quindi può essere utilizzato da Analytics [regole di elaborazione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) per popolare le variabili di Analytics.

Inoltre, puoi utilizzare un set predefinito di azioni ed elenchi di prodotti per inviare o recuperare dati con [AEP Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en).

## Dati contestuali

Per essere utilizzati da Analytics, i dati XDM vengono appiattiti utilizzando la notazione del punto e resi disponibili come `contextData`. Il seguente elenco di coppie di valori mostra un esempio di `context data`:

```javascript
{
          "bh": "900",
          "bw": "1680",
          "c": "24",
          "c.a.d.key.[0]": "value1",
          "c.a.d.key.[1]": "value2",
          "c.a.d.object.key1": "value1",
          "c.a.d.object.key2.[0]": "value2",
          "c.a.x.environment.browserdetails.javascriptenabled": "true",
          "c.a.x.environment.type": "browser",
          "cust_hit_time_gmt": "1579781427",
          "g": "https://example.com/home",
          "gn": "home",
          "j": "1.8.5",
          "k": "Y",
          "s": "1680x1050",
          "tnta": "218287:1:0|0,218287:1:0|2,218287:1:0|1,218287:1:0|32767,218287:1:0|1,218287:1:0|0,218287:1:0|1,218287:1:0|0,218287:1:0|1",
          "user_agent": "Mozilla/5.0 AppleWebKit/537.36 Safari/537.36",
          "v": "Y"
        }
```

## Regole di elaborazione

Tutti i dati raccolti dalla rete Edge sono accessibili tramite [regole di elaborazione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html). In Analytics puoi utilizzare le regole di elaborazione per incorporare i dati contestuali nelle variabili di Analytics.

Ad esempio, nella regola seguente, Analytics è impostato per compilare **Termini di ricerca interni (eVar2)** con i dati associati a **a.x_atag.search.term(Dati contestuali)**.

![](assets/examplerule.png)


## Schema XDM

Experience Platform utilizza gli schemi per descrivere la struttura dei dati in modo coerente e riutilizzabile. Definendo i dati in modo coerente tra i diversi sistemi, diventa più facile mantenere il significato e quindi ottenere valore dai dati. I dati contestuali di Analytics funzionano con la struttura definita dallo schema.

L’esempio seguente mostra come [`event` command](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html) può essere utilizzato con `xdm` per inviare e recuperare dati con AEP Web SDK. In questo esempio, la `event` corrisponde al comando [Schema dei dettagli di Commerce di ExperienceEvent](https://github.com/adobe/xdm/blob/1c22180490558e3c13352fe3e0540cb7e93c69ca/docs/reference/context/experienceevent-commerce.schema.md) in modo che productListItems `name` e `SKU` vengono tracciati i valori:


```
alloy("event",{
  "xdm":{
    "commerce":{
      "productViews":{
        "value":1
      }
    },
    "productListItems":[
      {
        "SKU":"HT105",
        "name":"Large Field Hat",
      },
      {
        "SKU":"HT104",
        "name":"Small Field Hat",
      }
    ]
  }
});
```

Per ulteriori informazioni sul tracciamento degli eventi con AEP Web SDK, vedi [Tracciamento eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html).
