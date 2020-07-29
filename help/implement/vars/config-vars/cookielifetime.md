---
title: cookieLifetime
description: Ignorate la scadenza per i cookie creati da AppMeasurement.
translation-type: tm+mt
source-git-commit: 7c0d363cc3d0f504d638479b02bf4435491b22fd
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 1%

---


# cookieLifetime

I cookie impostati da AppMeasurement hanno in genere una scadenza di 2 anni. Utilizzate la `cookieLifetime` variabile per ignorare la data di scadenza per i cookie impostati da AppMeasurement.

>[!NOTE]
>
>Questa variabile interessa i conteggi e l’attribuzione univoci dei visitatori. Prestate attenzione quando impostate questa variabile.

## Durata del cookie in  Adobe Experience Platform Launch

Cookie Lifetime è un menu a discesa sotto la [!UICONTROL Cookies] struttura di navigazione quando si configura l’estensione Adobe Analytics .

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto  Adobe Analytics.
4. Espandete la [!UICONTROL Cookies] fisarmonica, che mostra il [!UICONTROL Cookie Lifetime] menu a discesa.

Questo elenco a discesa contiene i seguenti valori:

* **Predefinito**: Cookie scade dopo 2 anni.
* **Nessuno**: AppMeasurement non imposta i cookie.
* **Sessione**: Il cookie scade alla fine della sessione del visitatore.
* **Secondi**: Il cookie scade dopo che è trascorso il numero specificato di secondi. Ad esempio, impostando questo menu a discesa su [!UICONTROL Seconds] e inserendo `86400` nel campo personalizzato, i cookie scadono esattamente dopo 24 ore.

## s.cookieLifetime nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.cookieLifetime` variabile è una stringa che determina la data di scadenza dei cookie impostati da AppMeasurement.

* Se impostato su `SESSION`, i cookie impostati da AppMeasurement scadono al termine della sessione del browser.
* Se impostato su `NONE`, AppMeasurement non tenta di impostare i cookie.
* Se impostato su una stringa intera, i cookie impostati da AppMeasurement scadono dopo che è trascorso il numero specificato di secondi.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
