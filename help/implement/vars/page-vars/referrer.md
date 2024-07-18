---
title: referrer
description: Sostituisci il referente raccolto automaticamente per un hit.
feature: Variables
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 16%

---

# referrer

La variabile `referrer` sostituisce il referente raccolto automaticamente nei rapporti. Questa variabile è utile nelle situazioni in cui il referente potrebbe andare perso, ad esempio durante i reindirizzamenti o l’inoltro temporaneo del visitatore a un elaboratore dei pagamenti. Questa variabile consente di popolare le dimensioni &quot;Referrer&quot; e &quot;Dominio di riferimento&quot;.

## Referente che utilizza l’SDK web

Il referrer è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webReferrer.URL`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.referrer`

L&#39;SDK Web include automaticamente `web.webReferrer.URL` su ogni evento inviato, se disponibile.

## Referente che utilizza l’estensione Adobe Analytics

Puoi impostare il referente sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Referrer].

Puoi impostare il referente su qualsiasi valore stringa, inclusi gli elementi dati.

## s.referrer in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.referrer` è una stringa contenente l&#39;URL della pagina precedente. Questa variabile può memorizzare un massimo di 255 byte; i valori superiori a 255 byte vengono troncati. AppMeasurement imposta automaticamente questa variabile su `document.referrer`. Non è necessario impostare questa variabile a meno che non si desideri sostituire il valore raccolto automaticamente.

```js
s.referrer = "https://example.com";
```

Se si utilizza il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>Evita di impostare questa variabile su valori non URL. Non eliminare il protocollo dell’URL.

## Esempio

Molte organizzazioni si occupano di implementazioni relative ai reindirizzamenti. È possibile utilizzare l&#39;utilità [`Util.getQueryParam()`](../functions/util-getqueryparam.md) per ottenere un referente dall&#39;URL, se il sito lo gestisce. Assicurati di codificare nell’URL tutti i valori inclusi nella stringa di query.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
