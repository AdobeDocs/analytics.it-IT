---
title: campaign
description: Popolare la dimensione "Codice di tracciamento".
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 19%

---

# campaign

La variabile `campaign` è dedicata alla raccolta dei codici di tracciamento sul sito. Nelle versioni precedenti di Adobe Analytics, aveva un trattamento speciale in cui poteva essere utilizzato come raggruppamento per la maggior parte delle dimensioni. Nella versione corrente di Adobe Analytics, agisce come un eVar.

Questa variabile popola la dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md). In genere ottiene il valore da una stringa di query utilizzando il metodo di utilità [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md). Tuttavia, l’organizzazione determina esattamente come impostare questa variabile.

## Campagna con l’SDK per web

Campaign è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `marketing.trackingCode`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.campaign` o `data.__adobe.analytics.v0`

## Campaign tramite l’estensione Adobe Analytics

Puoi impostare la campagna sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Campaign].

Puoi impostare campaign su un valore o su un parametro di stringa query.

## s.campaign in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.campaign` è una stringa che in genere contiene un codice di tracciamento utilizzato nelle attività di marketing. La lunghezza massima è di 255 byte; i valori superiori a 255 byte vengono troncati automaticamente quando vengono inviati all&#39;Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
