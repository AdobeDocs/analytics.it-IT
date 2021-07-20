---
title: eVar (merchandising)
description: Variabili personalizzate che si legano alla dimensione prodotti.
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
source-git-commit: 2e3f078500b80eefa2ca7c4a67de5bd0e91e764f
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---

# eVar (merchandising)

*Questa pagina di aiuto descrive il funzionamento degli eVar di merchandising come una dimensione. Per informazioni su come implementare le eVar di merchandising, consulta [eVar](/help/implement/vars/page-vars/evar.md) nella guida utente Implementazione.*

Per una discussione dettagliata sul funzionamento delle eVar per merchandising, consulta [eVar per merchandising e metodi di ricerca dei prodotti](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=en).

Quando si misura il successo di campagne esterne o termini di ricerca esterni, in genere si desidera che un singolo valore riceva credito per eventuali eventi di successo. Ad esempio, se un cliente fa clic su un collegamento presente in una campagna e-mail per visitare il sito web, tutti gli acquisti effettuati come risultato devono essere accreditati su tale campagna.

Cosa succede negli eventi generati dalla ricerca interna o dalla navigazione tra categorie quando un cliente cerca più elementi? Ad esempio, un cliente cerca nel sito `"goggles"`, quindi aggiunge una coppia al carrello:

![Esempio di occhiali](assets/merch-example-goggles.png)

Prima del pagamento, il cliente cerca `"winter coat"`, quindi aggiunge una giacca giù al carrello:

![Esempio di rivestimento](assets/merch-example-coat.png)

Quando il visitatore completa questo acquisto, avrai una ricerca interna per `"winter coat"` accreditata con l&#39;acquisto di una coppia di occhiali (supponendo che l&#39;eVar utilizzi l&#39;allocazione predefinita di &#39;Più recente&#39;). Buono per `"winter coat"`, ma cattivo per le decisioni di marketing:

| Termine di ricerca interno | Ricavi |
|---|---|
| cappotto invernale | $ 157 |

## Come le variabili merchandising risolvono questo problema

Le eVar di merchandising consentono di assegnare il valore corrente di un eVar a un prodotto nel momento in cui si verifica un evento riuscito. Questo valore rimane legato a quel prodotto, anche se uno o più nuovi valori vengono successivamente impostati per quel particolare eVar.

Se per l’eVar nell’esempio precedente è abilitato il merchandising, il termine di ricerca `"goggles"` è legato agli occhialini da neve e il termine di ricerca `"winter coat"` è legato al giubbotto inferiore. Le eVar di merchandising allocano i ricavi a livello di prodotto, in modo che ogni termine riceva credito per l’importo dei ricavi per il prodotto a cui è stato associato il termine:

| Termine di ricerca interno | Ricavi |
|---|---|
| cappotto invernale | $ 119 |
| occhialini | $38 |

Per istruzioni sull’implementazione, consulta [Merchandising eVars](/help/implement/vars/page-vars/evar-merchandising.md) .

## Istanze sulle variabili merchandising

La metrica [Istanze](../metrics/instances.md) non è consigliata per l&#39;utilizzo su variabili merchandising.

* Per le variabili di merchandising che utilizzano la sintassi di prodotto, le istanze non vengono affatto incrementate.
* Per le variabili merchandising che utilizzano la sintassi della variabile di conversione, le istanze vengono conteggiate ogni volta che l’eVar viene impostato. Tuttavia, attribuisce all’elemento dimensione `"None"` a meno che non si verifichino tutte le seguenti situazioni sullo stesso hit:
   * L’eVar merchandising è impostato con un valore.
   * La variabile `products` è definita con un valore.
   * È impostato un evento di binding.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Poiché la maggior parte dei casi d’uso per la sintassi della variabile di conversione richiede la variabile eVar e products su hit diversi, l’utilizzo della metrica &quot;Istanze&quot; non è realistico.
