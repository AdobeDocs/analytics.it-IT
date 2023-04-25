---
title: referrer
description: Ignora il referente raccolto automaticamente per un hit.
feature: Variables
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 19%

---

# referrer

La `referrer` sostituisce il referente raccolto automaticamente nei rapporti. Questa variabile è utile in situazioni in cui il referente potrebbe andare perso, ad esempio durante i reindirizzamenti o l&#39;inoltro temporaneo del visitatore a un elaboratore dei pagamenti. Questa variabile consente di compilare le dimensioni &quot;Referrer&quot; e &quot;Referring Domain&quot;.

## Referente che utilizza l’SDK per web

Referrer è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `web.webReferrer.URL`.

## Referrer che utilizza l&#39;estensione Adobe Analytics

Puoi impostare il referente sia durante la configurazione dell&#39;estensione Analytics (variabili globali) che in regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Imposta la [!UICONTROL Extension] elenco a discesa in Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Referrer].

Puoi impostare il referente su qualsiasi valore di stringa, inclusi gli elementi dati.

## s.referrer in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.referrer` è una stringa contenente l&#39;URL della pagina precedente. Questa variabile può memorizzare un massimo di 255 byte; i valori superiori a 255 byte vengono troncati. AppMeasurement imposta automaticamente questa variabile su `document.referrer`; non è necessario impostare questa variabile a meno che non si desideri ignorare il valore raccolto automaticamente.

```js
s.referrer = "https://example.com";
```

Se utilizzi `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>Evita di impostare questa variabile su valori non URL. Non eliminare il protocollo dell’URL.

## Esempio

Molte organizzazioni si occupano di implementazioni intorno ai reindirizzamenti. È possibile utilizzare [`Util.getQueryParam()`](../functions/util-getqueryparam.md) utilità per ottenere il referente dall&#39;URL se il sito lo ospita. Assicurati di codificare nell’URL tutti i valori inclusi nella stringa di query.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
