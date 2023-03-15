---
title: eVar (dimensione merchandising)
description: Variabili personalizzate collegate alla dimensione prodotti.
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 7%

---

# eVar  (Merchandising)

*Questa pagina della guida descrive il funzionamento delle eVar di merchandising come dimensione. Per informazioni su come implementare le eVar di merchandising, consulta [eVar (variabile merchandising)](/help/implement/vars/page-vars/evar-merchandising.md) nella guida utente all’implementazione.*

Per una discussione dettagliata sul funzionamento delle eVar di merchandising, consulta [eVar di merchandising e metodi di ricerca dei prodotti](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=it).

Quando si misura il successo di campagne esterne o dei termini di ricerca esterni, in genere si desidera che a un singolo valore venga attribuito il merito per eventuali eventi di successo che si verificano. Ad esempio, se un cliente fa clic su un collegamento in una campagna e-mail per visitare il tuo sito web, tutti gli acquisti effettuati come risultato devono essere accreditati a tale campagna.

Cosa succede quando un cliente cerca più elementi per eventi guidati dalla ricerca interna o dalla navigazione per categorie? Ad esempio, un cliente cerca nel tuo sito `"goggles"`, quindi aggiunge una coppia al carrello:

![Esempio di occhiali](assets/merch-example-goggles.png)

Prima del pagamento, il cliente cerca `"winter coat"`, quindi aggiunge una piumino al carrello:

![Esempio di cappotto](assets/merch-example-coat.png)

Al termine dell’acquisto, il visitatore effettua una ricerca interna per `"winter coat"` accreditato con l&#39;acquisto di una coppia di occhiali (supponendo che l&#39;eVar utilizzi l&#39;allocazione predefinita di &#39;Più recente&#39;). Buono per `"winter coat"`, ma non per le decisioni di marketing:

| Termine di ricerca interno | Ricavi |
|---|---|
| cappotto invernale | $157 |

## Come le variabili di merchandising risolvono questo problema

Le eVar di merchandising consentono di assegnare il valore corrente di un eVar a un prodotto nel momento in cui si verifica un evento di successo. Questo valore rimane legato a quel prodotto, anche se uno o più nuovi valori vengono successivamente impostati per quel particolare eVar.

Se nell’eVar precedente è abilitato il merchandising, il termine di ricerca `"goggles"` è legato agli occhiali da neve, e il termine di ricerca `"winter coat"` è legato al piumino. Le eVar di merchandising allocano i ricavi a livello di prodotto, pertanto a ogni termine viene attribuito il merito per l’importo dei ricavi per il prodotto a cui è stato associato il termine:

| Termine di ricerca interno | Ricavi |
|---|---|
| cappotto invernale | $119 |
| occhiali | $38 |

Consulta [eVar per merchandising](/help/implement/vars/page-vars/evar-merchandising.md) per le istruzioni di implementazione.

## Istanze sulle variabili merchandising

Il [Istanze](../metrics/instances.md) L’utilizzo della metrica non è consigliato per le variabili merchandising.

* Per le variabili di merchandising con sintassi di prodotto, le istanze non vengono affatto incrementate.
* Per le variabili di merchandising che utilizzano la sintassi per le variabili di conversione, le istanze vengono conteggiate ogni volta che viene impostato l’eVar. Tuttavia, attribuisce all’elemento dimensione `"None"` a meno che non si verifichino tutte le seguenti condizioni sullo stesso hit:
   * L’eVar di merchandising è impostato con un valore.
   * Il `products` variabile è definita con un valore.
   * È impostato un evento di binding.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Poiché la maggior parte dei casi d’uso della sintassi per le variabili di conversione richiedono la variabile eVar e products per hit diversi, l’utilizzo della metrica &quot;Istanze&quot; non è realistico.
