---
title: referrer
description: Ignora il referente raccolto automaticamente per un hit.
feature: Variables
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 1%

---

# referrer

La `referrer` sostituisce il referente raccolto automaticamente nei rapporti. Questa variabile è utile in situazioni in cui il referente potrebbe andare perso, ad esempio durante i reindirizzamenti o l&#39;inoltro temporaneo del visitatore a un elaboratore dei pagamenti. Questa variabile consente di compilare le dimensioni &quot;Referrer&quot; e &quot;Referring Domain&quot;.

## Referente che utilizza i tag in Adobe Experience Platform

Puoi impostare il referente sia durante la configurazione dell&#39;estensione Analytics (variabili globali) che in regole.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Referrer] sezione .

Puoi impostare il referente su qualsiasi valore di stringa, inclusi gli elementi dati.

## s.referrer in AppMeasurement e nell&#39;editor di codice personalizzato

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
