---
title: Override variabili
description: Le sostituzioni delle variabili consentono di modificare il valore di una variabile per una singola chiamata di tracciamento o di tracciamento dei collegamenti.
translation-type: tm+mt
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de

---


# Override variabili

Le sostituzioni delle variabili consentono di modificare i valori di Analytics per un singolo hit senza influenzare le variabili esistenti sulla pagina.

## Flusso di lavoro

1. Creare un nuovo oggetto JavaScript. Il nome dell&#39;oggetto può essere quello desiderato.

   ```js
   var y = new Object();
   ```

2. Assegnare proprietà Analytics valide all&#39;oggetto:

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

Quando una chiamata di tracciamento riceve un oggetto nel parametro di esclusione, tutti i valori validi nell&#39;oggetto override sovrascrivono i valori nell&#39;oggetto Analytics standard. Le variabili già definite nell&#39;oggetto Analytics esistente non vengono modificate.
