---
title: cookieLifetime
description: Ignorare la scadenza dei cookie creati da AppMeasurement.
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# cookieLifetime

I cookie impostati da AppMeasurement hanno in genere una scadenza di 2 anni. Utilizza la `cookieLifetime` per ignorare la data di scadenza dei cookie impostati da AppMeasurement.

>[!NOTE]
>
>Questa variabile influisce sui conteggi e sull’attribuzione dei visitatori univoci. Presta attenzione quando imposti questa variabile.

## Durata dei cookie tramite tag in Adobe Experience Platform

Cookie Lifetime è un menu a discesa sotto [!UICONTROL Cookies] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
1. Espandi la [!UICONTROL Cookies] fisarmonica, che rivela [!UICONTROL Cookie Lifetime] a discesa.

Questo elenco a discesa contiene i seguenti valori:

* **Predefinito**: Il cookie scade dopo 2 anni.
* **Nessuno**: AppMeasurement non imposta i cookie.
* **Sessione**: Il cookie scade alla fine della sessione del visitatore.
* **Seconds**: Il cookie scade dopo che è trascorso il numero specificato di secondi. Ad esempio, l’impostazione di questo menu a discesa su [!UICONTROL Seconds] e la collocazione `86400` nel campo personalizzato forza la scadenza dei cookie dopo esattamente 24 ore.

## s.cookieLifetime in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.cookieLifetime` è una stringa che determina la data di scadenza dei cookie impostati da AppMeasurement.

* Se impostato su `SESSION`, i cookie impostati da AppMeasurement scadono al termine della sessione del browser.
* Se impostato su `NONE`, AppMeasurement non tenta di impostare i cookie.
* Se impostato su una stringa intera, i cookie impostati da AppMeasurement scadono dopo che è trascorso il numero specificato di secondi.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
