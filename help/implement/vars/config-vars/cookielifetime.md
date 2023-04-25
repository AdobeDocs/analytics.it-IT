---
title: cookieLifetime
description: Ignorare la scadenza dei cookie creati da AppMeasurement.
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 12%

---

# cookieLifetime

I cookie impostati da AppMeasurement hanno in genere una scadenza di 2 anni. Utilizza la `cookieLifetime` per ignorare la data di scadenza dei cookie impostati da AppMeasurement.

>[!NOTE]
>
>Questa variabile influisce sui conteggi e sull’attribuzione dei visitatori univoci. Presta attenzione quando imposti questa variabile.

## Ciclo di vita dei cookie con l’SDK per web

L’SDK per web non offre ancora la personalizzazione per tutta la durata dei cookie che imposta.

## Durata dei cookie tramite l’estensione Adobe Analytics

Cookie Lifetime è un elenco a discesa sotto [!UICONTROL Cookies] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi la [!UICONTROL Cookies] fisarmonica, che rivela [!UICONTROL Cookie Lifetime] elenco a discesa.

Questo elenco a discesa contiene i seguenti valori:

* **Predefinito**: Il cookie scade dopo 2 anni.
* **Nessuno**: AppMeasurement non imposta i cookie.
* **Sessione**: Il cookie scade alla fine della sessione del visitatore.
* **Seconds**: Il cookie scade dopo che è trascorso il numero specificato di secondi. Ad esempio, l’impostazione di questo elenco a discesa su [!UICONTROL Seconds] e la collocazione `86400` nel campo personalizzato forza la scadenza dei cookie dopo esattamente 24 ore.

## s.cookieLifetime in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

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
