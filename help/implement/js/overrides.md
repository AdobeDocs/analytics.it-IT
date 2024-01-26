---
title: Override variabili
description: Le sostituzioni di variabili consentono di modificare un valore di variabile per una singola chiamata di tracciamento o collegamento.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 4%

---

# Override variabili

Le sostituzioni di variabili consentono di modificare i valori di Analytics per un singolo hit senza influire sulle variabili esistenti sulla pagina.

## Flusso di lavoro

1. Crea un nuovo oggetto JavaScript. Il nome dell&#39;oggetto può essere qualsiasi cosa si desideri.

   ```js
   var y = new Object();
   ```

2. Assegna proprietà Analytics valide a questo oggetto:

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. Utilizza l’oggetto come argomento all’interno della chiamata di tracciamento appropriata:

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

Quando una chiamata di tracciamento riceve un oggetto nel parametro overrides, tutti i valori validi nell’oggetto override sovrascrivono quelli nell’oggetto Analytics standard. Le variabili già definite nell’oggetto Analytics esistente non vengono interessate.
