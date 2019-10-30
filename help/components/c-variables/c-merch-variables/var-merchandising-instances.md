---
description: Descrive come vengono conteggiate le istanze sulle variabili di merchandising.
keywords: Implementazione di Analytics
seo-description: Descrive come vengono conteggiate le istanze sulle variabili di merchandising.
seo-title: Istanze sulle variabili merchandising
solution: Analytics
title: Istanze sulle variabili merchandising
topic: Sviluppatore e implementazione
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Istanze sulle variabili merchandising

Descrive come vengono conteggiate le istanze sulle variabili di merchandising.

Le istanze non sono attualmente supportate per le variabili merchandising. Se notate delle istanze in un rapporto contenente una variabile di merchandising, significa che l'eVar viene impostata in alcune posizioni al di fuori della stringa di prodotti e non deve essere considerata come un conteggio effettivo delle istanze per la variabile di merchandising selezionata.

Se si utilizza la sintassi della variabile di conversione, viene conteggiata un'istanza ogni volta che la variabile viene impostata. Tuttavia, l'istanza è attribuita a "None" a meno che quanto segue non si verifichi ogni volta che la variabile viene impostata:

* È impostato un evento di binding.
* La variabile products è impostata.
* L'eVar di merchandising ha un valore.

Ad esempio, la seguente istanza di eVar1 è assegnata a "Outdoors:Ski Goggles":

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

Tuttavia, nell'esempio seguente, l'istanza di eVar1 viene assegnata a "None", poiché tutte le condizioni non vengono soddisfatte quando l'eVar è impostato (non esiste alcun evento di binding e la variabile products non è impostata):

Pagina 1 della visita:

```js
s.eVar1="Outdoors:Ski Goggles"
```

Pagina 2 della visita:

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

L'allocazione a "None" si verifica se si imposta un valore per un'eVar su una pagina in cui non si verifica alcun evento di binding, o se si imposta il valore eVar nella stringa products senza un evento di binding.

> [!NOTE] La funzionalità corrente per il conteggio delle istanze sulle variabili di merchandising è in fase di revisione ed è prevista una modifica in una prossima release.

