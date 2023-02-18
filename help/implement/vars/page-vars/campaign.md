---
title: campaign
description: Popolare la dimensione "Tracking Code" (Codice di tracciamento).
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
source-git-commit: e46b15eedda78303e6e29faceea6db8483eee277
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 27%

---

# campaign

La `campaign` è dedicata alla raccolta dei codici di tracciamento sul sito. Nelle versioni precedenti di Adobe Analytics, aveva un trattamento speciale in cui poteva essere utilizzato come suddivisione per la maggior parte delle dimensioni. Nella versione corrente di Adobe Analytics, agisce in modo identico a un eVar.

Questa variabile popola il [Codice di tracciamento](/help/components/dimensions/tracking-code.md) dimensione. In genere ottiene il suo valore da una stringa di query utilizzando [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) metodo di utilità. Tuttavia, l’organizzazione determina esattamente come impostare questa variabile.

## Campaign utilizzando l’SDK per web

Campaign è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `marketing.trackingCode`.

## Campaign utilizzando l’estensione Adobe Analytics

Puoi impostare campaign sia durante la configurazione dell’estensione Analytics (variabili globali) che in regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Campaign].

Puoi impostare campaign su un valore o su un parametro di stringa query.

## s.campaign in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La `s.campaign` è una stringa che in genere contiene un codice di tracciamento utilizzato nelle attività di marketing. La sua lunghezza massima è di 255 byte; i valori superiori a 255 byte vengono troncati automaticamente quando inviati ad Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
