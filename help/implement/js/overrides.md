---
title: Override variabili
description: Le sostituzioni di variabili consentono di modificare un valore di variabile per una singola chiamata di tracciamento o collegamento.
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
role: Developer
TQID: https://experienceleague.adobe.com/5PRIj1hVEvFSBdcjsAZ57R9Bc0QVew31ryzrJtGNwb4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 106
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
