---
title: Override variabili
description: Le sostituzioni delle variabili consentono di modificare un valore variabile per una singola chiamata di tracciamento o di tracciamento dei collegamenti.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 4%

---

# Override variabili

Le sostituzioni delle variabili consentono di modificare i valori di Analytics per un singolo hit senza influire sulle variabili esistenti nella pagina.

## Flusso di lavoro

1. Crea un nuovo oggetto JavaScript. Il nome dell’oggetto può essere qualsiasi cosa desideri.

   ```js
   var y = new Object();
   ```

2. Assegna proprietà Analytics valide all&#39;oggetto:

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

Quando una chiamata di tracciamento riceve un oggetto nel parametro di override, tutti i valori validi nell&#39;oggetto di override sovrascrivono i valori nell&#39;oggetto Analytics standard. Le variabili già definite nell’oggetto Analytics esistente non vengono influenzate.
