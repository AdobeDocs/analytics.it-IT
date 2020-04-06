---
description: Descrive come vengono conteggiate le istanze sulle variabili di merchandising.
keywords: Analytics Implementation
title: Istanze sulle variabili merchandising
topic: Developer and implementation
uuid: 4cdfd53e-88aa-48cf-a135-98f7fc8dcece
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Istanze sulle variabili merchandising

Descrive come vengono conteggiate le istanze sulle variabili di merchandising.

Le istanze non sono attualmente supportate per le variabili merchandising. Se notate delle istanze in un rapporto contenente una variabile di merchandising, significa che l&#39;eVar viene impostata in alcune posizioni al di fuori della stringa di prodotti e non deve essere considerata come un conteggio effettivo delle istanze per la variabile di merchandising selezionata.

Se si utilizza la sintassi della variabile di conversione, viene conteggiata un&#39;istanza ogni volta che la variabile viene impostata. Tuttavia, l&#39;istanza è attribuita a &quot;None&quot; a meno che quanto segue non si verifichi ogni volta che la variabile viene impostata:

* È impostato un evento di binding.
* La variabile products è impostata.
* L&#39;eVar di merchandising ha un valore.

Ad esempio, la seguente istanza di eVar1 è assegnata a &quot;Outdoors:Ski Goggles&quot;:

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

Tuttavia, nell&#39;esempio seguente, l&#39;istanza di eVar1 viene assegnata a &quot;None&quot;, poiché tutte le condizioni non vengono soddisfatte quando l&#39;eVar è impostato (non esiste alcun evento di binding e la variabile products non è impostata):

Pagina 1 della visita:

```js
s.eVar1="Outdoors:Ski Goggles"
```

Pagina 2 della visita:

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

L&#39;allocazione a &quot;None&quot; si verifica se si imposta un valore per un&#39;eVar su una pagina in cui non si verifica alcun evento di binding, o se si imposta il valore eVar nella stringa products senza un evento di binding.

>[!NOTE] La funzionalità corrente per il conteggio delle istanze sulle variabili di merchandising è in fase di revisione ed è prevista una modifica in una prossima release.

