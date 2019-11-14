---
description: Le sostituzioni delle variabili consentono di modificare il valore di una variabile per una singola chiamata di tracciamento o di tracciamento dei collegamenti.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Override variabili
topic: Developer and implementation
uuid: 3ec09ae8-b9df-426f-8065-42b4518e6c5f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Override variabili

Le sostituzioni delle variabili consentono di modificare il valore di una variabile per una singola chiamata di tracciamento o di tracciamento dei collegamenti.

Per ignorare le variabili, create un nuovo oggetto, assegnate valori variabili e passate l’oggetto come primo parametro a `s.t()`oppure come quarto parametro a `s.tl()`:

```js
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
  
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
  
s.t(overrides);  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

```js
s.linkTrackVars="eVar1,eVar2,eVar3,events"; 
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
 
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
 
s.tl(this,'e','AnotherSite',overrides,'navigate')  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

