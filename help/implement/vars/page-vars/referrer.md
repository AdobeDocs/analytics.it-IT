---
title: referrer
description: Ignora il referente raccolto automaticamente per un hit.
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 1%

---

# referrer

La variabile `referrer` sostituisce il referente raccolto automaticamente nei rapporti. Questa variabile è utile in situazioni in cui il referente potrebbe andare perso, ad esempio durante i reindirizzamenti o l&#39;inoltro temporaneo del visitatore a un elaboratore dei pagamenti. Questa variabile consente di compilare le dimensioni &quot;Referrer&quot; e &quot;Referring Domain&quot;.

## Referente che utilizza i tag in Adobe Experience Platform

Puoi impostare il referente sia durante la configurazione dell&#39;estensione Analytics (variabili globali) che in regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Referrer] .

Puoi impostare il referente su qualsiasi valore di stringa, inclusi gli elementi dati.

## s.referrer in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.referrer` è una stringa contenente l’URL della pagina precedente. Questa variabile può memorizzare un massimo di 255 byte; i valori superiori a 255 byte vengono troncati. AppMeasurement imposta automaticamente questa variabile su `document.referrer`; non è necessario impostare questa variabile a meno che non si desideri ignorare il valore raccolto automaticamente.

```js
s.referrer = "https://example.com";
```

Se utilizzi il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>Evita di impostare questa variabile su valori non URL. Non eliminare il protocollo dell’URL.

## Esempio

Molte organizzazioni si occupano di implementazioni intorno ai reindirizzamenti. Puoi utilizzare l&#39;utilità [`Util.getQueryParam()`](../functions/util-getqueryparam.md) per ottenere il referente dall&#39;URL se il sito lo contiene. Assicurati di codificare nell’URL tutti i valori inclusi nella stringa di query.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
