---
title: Util.cookieRead
description: Ottiene il valore di un cookie.
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 11%

---

# Util.cookieRead

I cookie possono memorizzare e recuperare informazioni tra le pagine dello stesso dominio. Utilizzare il metodo `Util.cookieRead()` per recuperare un valore da un cookie.

## Leggere i cookie tramite l’estensione Adobe Analytics e l’estensione Web SDK

Puoi leggere i cookie impostando i valori negli elementi di dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Data Elements], quindi fai clic sull&#39;elemento dati desiderato (o crea un elemento dati).
4. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su **[!UICONTROL Core]** e [!UICONTROL Data Element Type] su **[!UICONTROL Cookie]**.
5. Immetti il nome del cookie nel campo di testo.

Il valore del cookie viene memorizzato nell&#39;elemento dati. Puoi quindi fare riferimento all’elemento dati nelle regole per assegnare le variabili desiderate.

## s.Util.cookieRead() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiamare il metodo `s.Util.cookieRead()` per leggere un valore cookie desiderato. Il suo unico argomento è una stringa, che è obbligatoria. Questo metodo restituisce una stringa contenente il valore del cookie. Se i cookie non esistono, viene restituita una stringa vuota.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
