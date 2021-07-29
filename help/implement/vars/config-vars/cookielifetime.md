---
title: cookieLifetime
description: Ignorare la scadenza dei cookie creati da AppMeasurement.
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# cookieLifetime

I cookie impostati da AppMeasurement hanno in genere una scadenza di 2 anni. Utilizza la variabile `cookieLifetime` per ignorare la data di scadenza dei cookie impostati da AppMeasurement.

>[!NOTE]
>
>Questa variabile influisce sui conteggi e sull’attribuzione dei visitatori univoci. Presta attenzione quando imposti questa variabile.

## Durata dei cookie tramite tag in Adobe Experience Platform

La funzione Cookie Lifetime è un menu a discesa nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
1. Espandi il [!UICONTROL Cookies] pannello a soffietto, che mostra il menu a discesa [!UICONTROL Cookie Lifetime].

Questo elenco a discesa contiene i seguenti valori:

* **Predefinito**: Il cookie scade dopo 2 anni.
* **Nessuno**: AppMeasurement non imposta i cookie.
* **Sessione**: Il cookie scade alla fine della sessione del visitatore.
* **Secondi**: Il cookie scade dopo che è trascorso il numero specificato di secondi. Ad esempio, se imposti questo menu a discesa su [!UICONTROL Seconds] e inserisci `86400` nel campo personalizzato, i cookie scadranno esattamente dopo 24 ore.

## s.cookieLifetime in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.cookieLifetime` è una stringa che determina la data di scadenza dei cookie impostati da AppMeasurement.

* Se è impostato su `SESSION`, i cookie impostati da AppMeasurement scadono al termine della sessione del browser.
* Se è impostato su `NONE`, AppMeasurement non tenta di impostare i cookie.
* Se impostato su una stringa intera, i cookie impostati da AppMeasurement scadono dopo che è trascorso il numero specificato di secondi.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
