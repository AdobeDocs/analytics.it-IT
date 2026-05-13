---
title: Tipi di eventi di Edge Network in Adobe Analytics
description: Come Adobe Analytics interpreta gli eventi ricevuti da Edge Network.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
TQID: https://experienceleague.adobe.com/Bf-OnlQu7TFYb1V4uKCVVoQkaPP4MuhyVWSdgjlZ6e8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 478
ht-degree: 18%

---

# Tipi di eventi di Edge Network in Adobe Analytics

Adobe Analytics tratta gli hit in modo diverso a seconda delle funzioni chiamate in AppMeasurement. Ad esempio, [`s.t`](/help/implement/vars/functions/t-method.md) e [`s.tl`](/help/implement/vars/functions/tl-method.md) includono o omettono determinate dimensioni e incrementano [visualizzazioni di pagina](/help/components/metrics/page-views.md) in modo diverso. Adobe Experience Platform contiene solo il comando [`sendEvent`](https://experienceleague.adobe.com/it/docs/experience-platform/collection/js/commands/sendevent/overview). Le proprietà specifiche all&#39;interno del payload [`xdm`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/xdm) o [`data`](https://experienceleague.adobe.com/it/docs/experience-platform/collection/js/commands/sendevent/data) determinano il modo in cui tali dati vengono interpretati in Adobe Analytics.

Edge Network utilizza la seguente logica per determinare le [visualizzazioni di pagina](/help/components/metrics/page-views.md) e i [eventi di collegamento](/help/components/metrics/page-events.md) di Adobe Analytics:

## Visualizzazioni di pagina ed eventi di collegamento tramite l&#39;oggetto `xdm`

| Il payload XDM contiene... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.URL` e non `xdm.web.webInteraction.type` | considera il payload una **visualizzazione di pagina** |
| `xdm.eventType = web.webpagedetails.pageViews` | considera il payload una **visualizzazione di pagina** |
| `xdm.web.webInteraction.type` e (`xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.URL`) | considera il payload un **evento collegamento** <br/>Imposta anche `xdm.web.webPageDetails.name` e `xdm.web.webPageDetails.URL` su `null` |
| `xdm.web.webInteraction.type` e (`xdm.web.webInteraction.name` o `xdm.web.webInteraction.URL`) | considera il payload un **evento collegamento** <br/>Imposta anche `xdm.web.webPageDetails.name` e `xdm.web.webPageDetails.URL` su `null`, se presente |
| nessun `xdm.web.webInteraction.type` e nessun `xdm.web.webPageDetails.name` e nessun `xdm.web.webPageDetails.URL` | elimina il payload e ignora i dati |

>[!TIP]
>
>I nomi dei campi XDM nel payload fanno distinzione tra maiuscole e minuscole, ad esempio `webPageDetails.URL`. Il campo `xdm.eventType` è un valore stringa con il proprio set di valori accettati e le maiuscole in essi contenute potrebbero non corrispondere ai nomi dei campi XDM. Per i valori accettati, vedere il campo `eventType` nella classe [XDM ExperienceEvent](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/classes/experienceevent#eventType).

+++Visualizzazione pagina minima utilizzando `xdm` campi

```json
{
  "xdm": {
    "web": {
      "webPageDetails": {
        "name": "Example page",
        "URL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Visualizzazione pagina minima tramite `xdm.eventType`

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++Evento di collegamento minimo utilizzando i campi consigliati

```json
{
  "xdm": {
    "web": {
      "webInteraction": {
        "type": "other",
        "name": "Header nav: Pricing",
        "URL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

## Visualizzazioni di pagina ed eventi di collegamento tramite l&#39;oggetto `data`

| Il payload dell’oggetto dati contiene... | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` o `data.__adobe.analytics.pageURL` e non `data.__adobe.analytics.linkType` | considera il payload una **visualizzazione di pagina** |
| `data.__adobe.analytics.linkType` e (`data.__adobe.analytics.linkName` o `data.__adobe.analytics.linkURL`) | considera il payload un **evento collegamento** <br/>Imposta anche `data.__adobe.analytics.pageName` e `data.__adobe.analytics.pageURL` su `null` |
| nessun `data.__adobe.analytics.linkType` e nessun `data.__adobe.analytics.pageName` e nessun `data.__adobe.analytics.pageURL` | elimina il payload e ignora i dati |

+++Visualizzazione pagina minima utilizzando `data` campi

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "pageName": "Example page",
        "pageURL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Evento di collegamento minimo utilizzando `data` campi

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "linkType": "o",
        "linkName": "Header nav: Pricing",
        "linkURL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

>[!NOTE]
>
>Se includi nello stesso payload sia un oggetto `xdm` che un oggetto `data`, Adobe Analytics controlla entrambi gli oggetti per i rispettivi campi.

## A4T ed eventi relativi al processo decisionale

Oltre a differenziare le visualizzazioni di pagina e gli eventi di collegamento, la logica seguente determina se alcuni eventi decisionali sono classificati come A4T o vengono scartati.

| Il payload XDM contiene... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` e `xdm._experience.decisioning` | considera il payload una chiamata **A4T**. |
| `xdm.eventType = decisioning.propositionDisplay` e nessun `xdm._experience.decisioning` | elimina il payload e ignora i dati |
| `xdm.eventType = decisioning.propositionInteract` e `xdm._experience.decisioning` e nessun `xdm.web.webInteraction.type` | considera il payload una chiamata **A4T**. |
| `xdm.eventType = decisioning.propositionInteract` e nessun `xdm._experience.decisioning` e nessun `xdm.web.webInteraction.type` | rilascia il payload e ignora i dati. |
| `xdm.eventType = decisioning.propositionFetch` | elimina il payload e ignora i dati |

>[!TIP]
>
>I seguenti valori `eventType` sono obsoleti. Si noti che questi valori influiscono sulla logica allo stesso modo delle controparti correnti:
>
>* Tipo di evento `display` obsoleto. Al suo posto, utilizza `decisioning.propositionDisplay`.
>* Tipo di evento `click` obsoleto. Al suo posto, utilizza `decisioning.propositionInteract`.
>* Tipo di evento `personalization.request` obsoleto. Al suo posto, utilizza `decisioning.propositionFetch`.

+++Visualizzazione minima A4T

```json
{
  "xdm": {
    "eventType": "decisioning.propositionDisplay",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "display": 1 }
      }
    }
  }
}
```

+++

+++Interazione A4T minima

```json
{
  "xdm": {
    "eventType": "decisioning.propositionInteract",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "interact": 1 }
      }
    }
  }
}
```

+++

Per ulteriori informazioni, consulta [Gruppo di campi schema di estensione completo di Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/field-groups/event/analytics-full-extension).
