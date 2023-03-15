---
title: campaign
description: Popolare la dimensione "Codice di tracciamento".
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
source-git-commit: e46b15eedda78303e6e29faceea6db8483eee277
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 27%

---

# campaign

Il `campaign` La variabile è dedicata alla raccolta dei codici di tracciamento sul sito. Nelle versioni precedenti di Adobe Analytics, aveva un trattamento speciale in cui poteva essere utilizzato come raggruppamento per la maggior parte delle dimensioni. Nella versione corrente di Adobe Analytics, agisce come un eVar.

Questa variabile compila il [Codice di tracciamento](/help/components/dimensions/tracking-code.md) dimensione. In genere ottiene il suo valore da una stringa di query utilizzando [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) metodo di utilità. Tuttavia, l’organizzazione determina esattamente come impostare questa variabile.

## Campagna con l’SDK per web

La campagna è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `marketing.trackingCode`.

## Campaign tramite l’estensione Adobe Analytics

Puoi impostare la campagna sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Campaign].

Puoi impostare campaign su un valore o su un parametro di stringa query.

## s.campaign in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.campaign` la variabile è una stringa che in genere contiene un codice di tracciamento utilizzato nelle attività di marketing. La lunghezza massima è di 255 byte; i valori superiori a 255 byte vengono troncati automaticamente quando vengono inviati all&#39;Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
