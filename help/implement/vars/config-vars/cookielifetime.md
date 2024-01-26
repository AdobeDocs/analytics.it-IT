---
title: cookieLifetime
description: Ignora la scadenza per i cookie creati da AppMeasurement.
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 12%

---

# cookieLifetime

I cookie impostati dall’AppMeasurement hanno in genere una scadenza di 2 anni. Utilizza il `cookieLifetime` per ignorare la data di scadenza dei cookie impostata da AppMeasurement.

>[!NOTE]
>
>Questa variabile influisce sui conteggi e sull’attribuzione univoci dei visitatori. Presta attenzione quando imposti questa variabile.

## Durata dei cookie tramite Web SDK

L’SDK per web non offre ancora la personalizzazione per la durata dei cookie impostata.

## Durata dei cookie tramite l’estensione Adobe Analytics

La durata dei cookie è un elenco a discesa sotto il [!UICONTROL Cookies] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi [!UICONTROL Cookies] Pannello a soffietto, che mostra [!UICONTROL Cookie Lifetime] elenco a discesa.

Questo elenco a discesa contiene i seguenti valori:

* **Predefinito**: il cookie scade dopo 2 anni.
* **Nessuno**: l’AppMeasurement non imposta i cookie.
* **Sessione**: il cookie scade alla fine della sessione del visitatore.
* **Secondi**: il cookie scade dopo il numero di secondi specificato. Ad esempio, impostando questo elenco a discesa su [!UICONTROL Seconds] e posizionamento `86400` nel campo personalizzato costringe i cookie a scadere esattamente dopo 24 ore.

## s.cookieLifetime in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

Il `s.cookieLifetime` la variabile è una stringa che determina la data di scadenza dei cookie impostati dall’AppMeasurement.

* Se impostato su `SESSION`, i cookie impostati dall’AppMeasurement scadono al termine della sessione del browser.
* Se impostato su `NONE`, AppMeasurement non tenta di impostare i cookie.
* Se è impostata su una stringa di numeri interi, i cookie impostati dall’AppMeasurement scadono dopo il numero di secondi specificato.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
