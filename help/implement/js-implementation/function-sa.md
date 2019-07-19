---
description: La funzione s. sa () consente di modificare dinamicamente una suite di rapporti in qualsiasi momento sulla pagina, prima o dopo l'attivazione di una richiesta di immagine.
keywords: Implementazione di Analytics
seo-description: La funzione s. sa () consente di modificare dinamicamente una suite di rapporti in qualsiasi momento sulla pagina, prima o dopo l'attivazione di una richiesta di immagine.
seo-title: La funzione s. sa ()
solution: Analytics
subtopic: Funzioni
title: La funzione s. sa ()
topic: Sviluppatore e implementazione
uuid: a 6 aacd 10-2 a 5 b -448 b-b 3 b 7-bed 5590 b 71 d 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# La funzione s. sa ()

La funzione s. sa () consente di modificare dinamicamente una suite di rapporti in qualsiasi momento sulla pagina, prima o dopo l'attivazione di una richiesta di immagine.

Se l'organizzazione desidera inviare dati a suite di rapporti diverse senza ricaricare la pagina, l'utilizzo di questa funzione è fortemente consigliato.

Queste informazioni sono adatte agli utenti avanzati che sono ben orientati sia in reporting che nell'implementazione. Non tentare di apportare modifiche alla vostra implementazione senza conoscerne le conseguenze. Se avete bisogno di modifiche di implementazione, contattate l'Account Manager della vostra organizzazione.

## Properties of the Function {#section_E10CB41A0CF749F4A24C8377958E3671}

L'impostazione di questa funzione utilizza tutte le variabili definite in precedenza e ne consente l'utilizzo in una suite di rapporti diversa.

## Implementation Examples {#section_14B0B8C853244D5F82B08B995773640C}

Invio di dati video a una suite di rapporti durante l'invio del resto a un altro:

```js
// Set in the core JS file by default 
var s=s_gi('prodrsid'); 
 
// Define this when a user interacts with a video 
s.sa('videorsid'); 
s.t(); // Sends an image request
```

Utilizzo di s. sa () e di tag per più suite:

```js
// Set in the core JS file by default 
var s=s_gi('rsid1'); 
 
// Call the function when you wish to change report suites 
s.sa('rsid1,rsid2'); 
s.t();
```

