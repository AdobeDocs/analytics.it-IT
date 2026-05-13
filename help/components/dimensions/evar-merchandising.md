---
title: eVar (dimensione merchandising)
description: Variabili personalizzate collegate alla dimensione prodotti.
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
TQID: https://experienceleague.adobe.com/No-Va3JzN6Qz9hBu73A5ZzKudEB1Tqa4sNPKVKAASGI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 6%

---

# eVar (merchandising)

*Questa pagina della guida descrive il funzionamento delle eVar di merchandising come [dimensione](overview.md). Per informazioni su come implementare le eVar di merchandising, vedi [eVar (variabile di merchandising)](/help/implement/vars/page-vars/evar-merchandising.md) nella guida utente per l&#39;implementazione.*

Per una discussione dettagliata sul funzionamento delle eVar di merchandising, consulta [eVar di merchandising e metodi di ricerca dei prodotti](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md).

Quando si misura il successo di campagne esterne o dei termini di ricerca esterni, in genere si desidera che a un singolo valore venga attribuito il merito per eventuali eventi di successo che si verificano. Ad esempio, se un cliente fa clic su un collegamento in una campagna e-mail per visitare il tuo sito web, tutti gli acquisti effettuati come risultato devono essere accreditati a tale campagna.

Cosa succede quando un cliente cerca più elementi per eventi guidati dalla ricerca interna o dalla navigazione per categorie? Ad esempio, un cliente cerca nel tuo sito `"goggles"`, quindi aggiunge una coppia al carrello:

![Attiva/disattiva esempio](assets/merch-example-goggles.png)

Prima del pagamento, il cliente cerca `"winter coat"`, quindi aggiunge una piumina al carrello:

![Esempio di cappotto](assets/merch-example-coat.png)

Quando il visitatore completa questo acquisto, viene effettuata una ricerca interna per `"winter coat"` accreditata dell&#39;acquisto di una coppia di occhiali (supponendo che eVar utilizzi l&#39;allocazione predefinita &quot;Più recente&quot;). Buono per `"winter coat"`, ma cattivo per le decisioni di marketing:

| Termine di ricerca interno | Ricavi |
|---|---|
| cappotto invernale | $157 |

## Come le variabili di merchandising risolvono questo problema

Le eVar di merchandising consentono di assegnare il valore corrente di un’eVar a un prodotto nel momento in cui si verifica un evento di successo. Questo valore rimane associato a quel prodotto, anche se uno o più nuovi valori vengono successivamente impostati per quel particolare eVar.

Se il merchandising è abilitato per l&#39;eVar nell&#39;esempio precedente, il termine di ricerca `"goggles"` è associato agli occhiali da neve e il termine di ricerca `"winter coat"` è associato al piumino. Le eVar di merchandising allocano i ricavi a livello di prodotto, pertanto a ogni termine viene attribuito il merito per l’importo dei ricavi per il prodotto a cui è stato associato il termine:

| Termine di ricerca interno | Ricavi |
|---|---|
| cappotto invernale | $119 |
| occhiali | $38 |

Per istruzioni sull&#39;implementazione, consulta [eVar per merchandising](/help/implement/vars/page-vars/evar-merchandising.md).

## Istanze sulle variabili merchandising

La metrica [Istanze](../metrics/instances.md) non è consigliata per l&#39;utilizzo su variabili merchandising.

* Per le variabili di merchandising con sintassi di prodotto, le istanze non vengono affatto incrementate.
* Per le variabili di merchandising con sintassi per variabili di conversione, le istanze vengono conteggiate ogni volta che si imposta eVar. Tuttavia, attribuisce all&#39;elemento dimensione `"None"` a meno che tutte le seguenti condizioni non si verifichino sullo stesso hit:
   * L’eVar di merchandising è impostata con un valore.
   * La variabile `products` è definita con un valore.
   * È impostato un evento di binding.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Poiché la maggior parte dei casi d’uso della sintassi per le variabili di conversione richiedono la variabile eVar e products per hit diversi, l’utilizzo della metrica &quot;Istanze&quot; non è realistico.
