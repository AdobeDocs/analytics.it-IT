---
title: cookieLifetime
description: Ignora la scadenza per i cookie creati da AppMeasurement.
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 13%

---

# cookieLifetime

I cookie impostati da AppMeasurement hanno in genere una scadenza di 2 anni. Utilizza il `cookieLifetime` per ignorare la data di scadenza dei cookie impostata da AppMeasurement.

>[!NOTE]
>
>Questa variabile influisce sui conteggi e sull’attribuzione univoci dei visitatori. Presta attenzione quando imposti questa variabile.

## Durata dei cookie tramite Web SDK

L’SDK per web non offre ancora la personalizzazione per la durata dei cookie impostata.

## Durata dei cookie tramite l’estensione Adobe Analytics

La durata dei cookie è un elenco a discesa sotto [!UICONTROL Cookies] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi [!UICONTROL Cookies] Pannello a soffietto, che mostra [!UICONTROL Cookie Lifetime] a discesa.

Questo menu a discesa contiene i seguenti valori:

* **Predefinito**: il cookie scade dopo 2 anni.
* **Nessuno**: AppMeasurement non imposta i cookie.
* **Sessione**: il cookie scade alla fine della sessione del visitatore.
* **Secondi**: il cookie scade dopo il numero di secondi specificato. Ad esempio, impostando questo menu a discesa su [!UICONTROL Seconds] e posizionamento `86400` nel campo personalizzato costringe i cookie a scadere esattamente dopo 24 ore.

## s.cookieLifetime in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

Il `s.cookieLifetime` La variabile è una stringa che determina la data di scadenza dei cookie impostati da AppMeasurement.

* Se impostato su `SESSION`, i cookie impostati da AppMeasurement scadono al termine della sessione del browser.
* Se impostato su `NONE`, AppMeasurement non tenta di impostare i cookie.
* Se è impostata su una stringa di numeri interi, i cookie impostati da AppMeasurement scadono dopo il numero di secondi specificato.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
