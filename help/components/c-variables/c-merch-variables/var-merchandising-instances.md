---
description: Descrive il modo in cui le istanze vengono conteggiate per le variabili merchandising.
keywords: Implementazione di Analytics
seo-description: Descrive il modo in cui le istanze vengono conteggiate per le variabili merchandising.
seo-title: Istanze sulle variabili merchandising
solution: Analytics
title: Istanze sulle variabili merchandising
topic: Sviluppatore e implementazione
uuid: 4 cdfd 53 e -88 aa -48 cf-a 135-98 f 7 fc 8 dcece
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Istanze sulle variabili merchandising

Descrive il modo in cui le istanze vengono conteggiate per le variabili merchandising.

Le istanze non sono attualmente supportate per le variabili merchandising. Se notate le istanze in un rapporto contenente una variabile di merchandising, essa indica che la evar viene impostata in alcune posizioni all'esterno della stringa products e non deve essere considerata un numero reale di istanze per la variabile di merchandising selezionata.

Se si utilizza Sintassi variabile conversione, un'istanza viene conteggiata ogni volta che la variabile viene impostata. Tuttavia, l'istanza viene assegnata a "None" (Nessuno) a meno che non si verifichi quanto segue ogni volta che la variabile viene impostata:

* Viene impostato un evento di binding.
* La variabile products è impostata.
* L'evar di merchandising ha un valore.

Ad esempio, la seguente istanza di evar 1 è allocata a «Outdoors: Sci goggles ":

```js
s.eVar1="Outdoors:Ski Goggles" 
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

Tuttavia, nell'esempio successivo, l'istanza di evar 1 è assegnata a "None", poiché tutte le condizioni non vengono soddisfatte quando la evar è impostata (non esiste un evento di binding e la variabile products non è impostata):

Pagina 1 della visita:

```js
s.eVar1="Outdoors:Ski Goggles"
```

Pagina 2 della visita:

```js
s.events="prodView" 
s.products=";Fernie Snow Goggles"
```

L'allocazione su «None» (Nessuno) si verifica se imposti un valore per una pagina evar in cui non si verifica alcun evento di binding, o se imposti il valore evar nella stringa products senza un evento di binding.

>[!NOTE]
>
>La funzionalità corrente per il conteggio delle istanze sulle variabili merchandising è in fase di revisione e viene pianificata di cambiare in una prossima release.

