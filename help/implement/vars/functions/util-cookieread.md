---
title: Util.cookieRead
description: Ottiene il valore di un cookie.
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 12%

---

# Util.cookieRead

I cookie possono memorizzare e recuperare informazioni tra le pagine dello stesso dominio. Utilizza il `Util.cookieRead()` per recuperare un valore da un cookie.

## Leggere i cookie tramite l’estensione Adobe Analytics e l’estensione Web SDK

Puoi leggere i cookie impostando i valori negli elementi di dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai a [!UICONTROL Data Elements] , quindi fai clic sull’elemento dati desiderato (o crea un elemento dati).
4. Imposta il [!UICONTROL Extension] menu a discesa per **[!UICONTROL Core]** e [!UICONTROL Data Element Type] a **[!UICONTROL Cookie]**.
5. Immetti il nome del cookie nel campo di testo.

Il valore del cookie viene memorizzato nell&#39;elemento dati. Puoi quindi fare riferimento all’elemento dati nelle regole per assegnare le variabili desiderate.

## s.Util.cookieRead() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiama il `s.Util.cookieRead()` per leggere un valore cookie desiderato. Il suo unico argomento è una stringa, che è obbligatoria. Questo metodo restituisce una stringa contenente il valore del cookie. Se i cookie non esistono, viene restituita una stringa vuota.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
