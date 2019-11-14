---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieDomain

La variabile determina il dominio in cui [!DNL Analytics] sono impostati i cookie `s_cc` e `s_sq` .

Comunemente, `s.cookieDomainPeriods` è utilizzato per generare `s.cookieDomain` da `window.location.hostname`. Invece di utilizzare `s.cookieDomainPeriods`, potete impostare esplicitamente `s.cookieDomain` ciò che desiderate utilizzare nell'implementazione. Ad esempio, puoi impostare i cookie sul nome di pagina completo utilizzando:

`s.cookieDomain = window.location.hostname;`
