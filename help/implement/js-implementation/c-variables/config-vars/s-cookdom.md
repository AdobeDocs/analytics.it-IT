---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.cookieDomain

La variabile determina il dominio in cui [!DNL Analytics] sono impostati i cookie `s_cc` e `s_sq` .

Comunemente, `s.cookieDomainPeriods` è utilizzato per generare `s.cookieDomain` da `window.location.hostname`. Invece di utilizzare `s.cookieDomainPeriods`, potete impostare esplicitamente `s.cookieDomain` ciò che desiderate utilizzare nell'implementazione. Ad esempio, puoi impostare i cookie sul nome di pagina completo utilizzando:

`s.cookieDomain = window.location.hostname;`
