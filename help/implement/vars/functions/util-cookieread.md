---
title: Util.cookieRead
description: Ottiene il valore di un cookie.
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 1%

---

# Util.cookieRead

I cookie possono memorizzare e recuperare informazioni tra le pagine dello stesso dominio. Utilizza la `Util.cookieRead()` per recuperare un valore da un cookie.

## Cookie di lettura mediante tag in Adobe Experience Platform

Puoi leggere i cookie impostando i valori negli elementi dati.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Data Elements] , quindi fai clic sull’elemento dati desiderato (o crea un elemento dati).
4. Imposta la [!UICONTROL Extension] a discesa [!UICONTROL Core]e [!UICONTROL Data Element Type] a [!UICONTROL Cookie].
5. Immetti il nome del cookie nel campo di testo.

Il valore del cookie viene memorizzato nell’elemento dati . Puoi quindi fare riferimento all’elemento dati nelle regole per assegnare le variabili di Analytics.

## s.Util.cookieRead() in AppMeasurement e nell&#39;editor di codice personalizzato

Chiama il `s.Util.cookieRead()` per leggere il valore desiderato del cookie. L&#39;unico argomento è una stringa, obbligatoria. Questo metodo restituisce una stringa contenente il valore del cookie. Se i cookie non esistono, viene restituita una stringa vuota.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
