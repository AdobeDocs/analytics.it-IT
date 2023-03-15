---
title: referrer
description: Sostituisci il referente raccolto automaticamente per un hit.
feature: Variables
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 23%

---

# referrer

Il `referrer` la variabile sostituisce il referente raccolto automaticamente nei rapporti. Questa variabile è utile nelle situazioni in cui il referente potrebbe andare perso, ad esempio durante i reindirizzamenti o l’inoltro temporaneo del visitatore a un elaboratore dei pagamenti. Questa variabile consente di popolare le dimensioni &quot;Referrer&quot; e &quot;Dominio di riferimento&quot;.

## Referente che utilizza l’SDK web

Il referrer è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `web.webReferrer.URL`.

## Referente che utilizza l’estensione Adobe Analytics

Puoi impostare il referente sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Referrer].

Puoi impostare il referente su qualsiasi valore stringa, inclusi gli elementi dati.

## s.referrer in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.referrer` variabile è una stringa contenente l’URL della pagina precedente. Questa variabile può memorizzare un massimo di 255 byte; i valori superiori a 255 byte vengono troncati. AppMeasurement imposta automaticamente questa variabile su `document.referrer`; non è necessario impostare questa variabile a meno che non si desideri ignorare il valore raccolto automaticamente.

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

Molte organizzazioni si occupano di implementazioni relative ai reindirizzamenti. È possibile utilizzare [`Util.getQueryParam()`](../functions/util-getqueryparam.md) per ottenere il referente dall&#39;URL, se il sito lo gestisce. Assicurati di codificare nell’URL tutti i valori inclusi nella stringa di query.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
