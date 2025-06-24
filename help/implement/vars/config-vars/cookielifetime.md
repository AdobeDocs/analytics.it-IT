---
title: cookieLifetime
description: Ignora la scadenza per i cookie creati da AppMeasurement.
feature: Appmeasurement Implementation
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 12%

---

# cookieLifetime

I cookie impostati da AppMeasurement in genere hanno una scadenza di 2 anni. Utilizza la variabile `cookieLifetime` per ignorare la data di scadenza dei cookie impostata da AppMeasurement.

>[!NOTE]
>
>Questa variabile influisce sui conteggi e sull’attribuzione univoci dei visitatori. Presta attenzione quando imposti questa variabile.

## Durata dei cookie tramite Web SDK

Il Web SDK non offre ancora la personalizzazione per la durata dei cookie impostati.

## Durata dei cookie tramite l’estensione Adobe Analytics

La durata dei cookie è un elenco a discesa nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandere il pannello a soffietto [!UICONTROL Cookies], che mostra l&#39;elenco a discesa [!UICONTROL Cookie Lifetime].

Questo elenco a discesa contiene i seguenti valori:

* **Predefinito**: il cookie scade dopo 2 anni.
* **Nessuno**: AppMeasurement non imposta i cookie.
* **Sessione**: il cookie scade alla fine della sessione del visitatore.
* **Secondi**: il cookie scade dopo il numero di secondi specificato. Ad esempio, se si imposta l&#39;elenco a discesa su [!UICONTROL Seconds] e si inserisce `86400` nel campo personalizzato, i cookie scadranno dopo esattamente 24 ore.

## s.cookieLifetime in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La variabile `s.cookieLifetime` è una stringa che determina la data di scadenza dei cookie impostati da AppMeasurement.

* Se è impostato su `SESSION`, i cookie impostati da AppMeasurement scadono al termine della sessione del browser.
* Se è impostato su `NONE`, AppMeasurement non tenta di impostare i cookie.
* Se è impostata su una stringa di numeri interi, i cookie impostati da AppMeasurement scadono dopo il numero di secondi specificato.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
