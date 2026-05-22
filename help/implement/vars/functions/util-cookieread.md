---
title: Util.cookieRead
description: Ottiene il valore di un cookie.
feature: Appmeasurement Implementation
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/puEimpy5b-hdgo186YqHzsgxC-LGKPluxN5mVdxFer4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 176
ht-degree: 13%

---

# Util.cookieRead

I cookie possono memorizzare e recuperare informazioni tra le pagine dello stesso dominio. Utilizzare il metodo `Util.cookieRead()` per recuperare un valore da un cookie.

## Leggere i cookie tramite l’estensione Adobe Analytics e l’estensione Web SDK

Puoi leggere i cookie impostando i valori negli elementi di dati.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
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
