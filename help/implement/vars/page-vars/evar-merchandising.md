---
title: eVar (Merchandising)
description: Variabili personalizzate che si legano a singoli prodotti.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---


# eVar (Merchandising)

*Questa pagina della Guida descrive come implementare le eVar di merchandising. Per informazioni sul funzionamento delle eVar di merchandising come dimensione, vedi[eVar (Merchandising)](/help/components/dimensions/evar-merchandising.md)nella guida utente Componenti.*

## Configurare le eVar nelle impostazioni della suite di rapporti

Prima di utilizzare le eVar nell&#39;implementazione, accertati di configurare l&#39;eVar in base alla sintassi desiderata nelle impostazioni della suite di rapporti. Consulta Variabili [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione nella guida di amministrazione.

>[!IMPORTANT] Se non si configurano correttamente le eVar di merchandising, la variabile presenta valori imprevisti o perdita di dati. Accertatevi che sia configurato correttamente per l’implementazione.

## Implementa utilizzando la sintassi del prodotto

Quando l&#39;opzione &quot;Sintassi prodotto&quot; è abilitata, la categoria merchandising viene compilata direttamente all&#39;interno della `products` variabile, pertanto la selezione e l&#39;impostazione di un evento di binding non è obbligatoria. Questo è il metodo consigliato e deve essere utilizzato a meno che il valore non sia disponibile per l&#39;impostazione in `products` corrispondenza dell&#39;evento success.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

Il valore per `eVar1` è assegnato al prodotto. Tutti gli eventi di successo successivi che coinvolgono questo prodotto vengono accreditati sul valore eVar.

## Implementazione mediante la sintassi della variabile di conversione

Sintassi variabile di conversione viene utilizzata quando il valore eVar non è disponibile per l&#39;impostazione nella `products` variabile. In genere questo scenario indica che la pagina non ha contesto del canale di merchandising o del metodo di ricerca. In questi casi, è possibile impostare la variabile merchandising prima di arrivare alla pagina del prodotto e il valore persiste finché non si verifica l&#39;evento di binding.

Quando si verifica l&#39;evento di binding selezionato durante la configurazione, il valore persistente dell&#39;eVar è associato al prodotto. Ad esempio, se `prodView` è specificato come evento di binding, la categoria merchandising è associata all&#39;elenco di prodotti corrente solo al momento in cui si verifica l&#39;evento. Solo gli eventi di binding successivi possono aggiornare un&#39;eVar di merchandising già assegnata a un prodotto.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

Il valore `"Aviary"` per `eVar1` è assegnato al prodotto `"Canary"`. Tutti gli eventi di successo successivi che coinvolgono questo prodotto vengono accreditati `"Canary"`. Inoltre, il valore corrente della variabile merchandising è associato a tutti i prodotti successivi fino al soddisfacimento di una delle seguenti condizioni:

* La scadenza dell&#39;eVar (in base all&#39;impostazione &#39;Scade dopo&#39;)
* L&#39;eVar di merchandising viene sovrascritto con un nuovo valore.
