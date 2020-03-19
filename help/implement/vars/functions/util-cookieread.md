---
title: Util.cookieRead
description: Ottiene il valore di un cookie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.cookieRead

I cookie possono memorizzare e recuperare informazioni tra le pagine dello stesso dominio. Utilizzare il `Util.cookieRead()` metodo per recuperare un valore da un cookie.

## Leggi i cookie in Adobe Experience Platform Launch

È possibile leggere i cookie impostando i valori negli elementi di dati.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Data Elements] scheda, quindi fai clic sull&#39;elemento dati desiderato (o crea un elemento dati).
4. Impostate il [!UICONTROL Extension] menu a discesa su [!UICONTROL Core], quindi [!UICONTROL Data Element Type] su [!UICONTROL Cookie].
5. Immettete il nome del cookie nel campo di testo.

Il valore del cookie viene memorizzato nell&#39;elemento dati. Potete quindi fare riferimento all&#39;elemento dati nelle regole per assegnare le variabili Analytics.

## s.Util.cookieRead() nell&#39;editor di codice personalizzato AppMeasurement e Launch

Chiamate il `s.Util.cookieRead()` metodo per leggere il valore del cookie desiderato. L&#39;unico argomento è una stringa, che è obbligatoria. Questo metodo restituisce una stringa contenente il valore del cookie. Se i cookie non esistono, viene restituita una stringa vuota.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
