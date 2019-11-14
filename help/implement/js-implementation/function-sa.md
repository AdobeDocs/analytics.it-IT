---
description: La funzione s.sa() consente di modificare dinamicamente una suite di rapporti in qualsiasi momento della pagina, prima o dopo l'attivazione di una richiesta di immagine.
keywords: Analytics Implementation
solution: Analytics
subtopic: Functions
title: La funzione s.sa()
topic: Developer and implementation
uuid: a6aacd10-2a5b-448b-b3b7-bed5590b71d4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# La funzione s.sa()

La funzione s.sa() consente di modificare dinamicamente una suite di rapporti in qualsiasi momento della pagina, prima o dopo l'attivazione di una richiesta di immagine.

Se l'organizzazione desidera inviare dati a suite di rapporti diverse senza ricaricare la pagina, è vivamente consigliato utilizzare questa funzione.

Queste informazioni sono adatte agli utenti avanzati che hanno una buona conoscenza sia del reporting che dell'implementazione. Non tentare di apportare modifiche alla tua implementazione senza una conoscenza completa delle sue conseguenze. Se hai bisogno di modifiche all'implementazione, contatta l'Account Manager della tua organizzazione.

## Proprietà della funzione {#section_E10CB41A0CF749F4A24C8377958E3671}

L'impostazione di questa funzione prende tutte le variabili definite in precedenza e le consente di utilizzarle in una suite di rapporti diversa.

## Esempi di implementazione {#section_14B0B8C853244D5F82B08B995773640C}

Invio di dati video a una suite di rapporti durante l’invio del resto a un’altra:

```js
// Set in the core JS file by default 
var s=s_gi('prodrsid'); 
 
// Define this when a user interacts with a video 
s.sa('videorsid'); 
s.t(); // Sends an image request
```

Utilizzo di s.sa() e tag per più suite:

```js
// Set in the core JS file by default 
var s=s_gi('rsid1'); 
 
// Call the function when you wish to change report suites 
s.sa('rsid1,rsid2'); 
s.t();
```

