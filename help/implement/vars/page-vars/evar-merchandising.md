---
title: Variabili eVar (Merchandising)
description: Variabili personalizzate correlate a singoli prodotti.
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
source-git-commit: 2624a18896f99aadcfe0a04538ece21c370a28b9
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 2%

---

# eVar  (Merchandising)

*Questa pagina di aiuto descrive come implementare le eVar di merchandising. Per informazioni sul funzionamento degli eVar di merchandising come dimensione, consulta [eVar (Merchandising)](/help/components/dimensions/evar-merchandising.md) nella guida utente Componenti .*

Per una discussione dettagliata sul funzionamento delle eVar per merchandising, vedi [eVar per merchandising e metodi di ricerca dei prodotti](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=it).

## Configurare eVar nelle impostazioni della suite di rapporti

Prima di utilizzare le eVar nell’implementazione, accertati di configurare l’eVar alla sintassi desiderata nelle impostazioni della suite di rapporti. Vedi [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) nella guida Amministratore.

>[!WARNING]
>
>Se non si configura correttamente l’eVar di merchandising, si ottengono valori imprevisti o perdite di dati per la variabile. Assicurati che sia configurato correttamente per la tua implementazione.

## Implementare utilizzando la sintassi del prodotto

Quando l’opzione &quot;Product Syntax&quot; è abilitata, la categoria merchandising viene compilata direttamente all’interno di `products` pertanto non è necessario selezionare e impostare un evento di binding. Questo è il metodo consigliato e deve essere utilizzato a meno che il valore non sia disponibile per l&#39;impostazione in `products` quando si verifica l’evento di successo.

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

Valore per `eVar1` viene assegnato al prodotto. Tutti gli eventi di successo successivi che coinvolgono questo prodotto vengono accreditati al valore eVar.

### Utilizzo di XDM per Edge Collection

Ogni campo nella variabile &quot;products&quot; viene compilato da un campo XDM corrispondente. È disponibile un elenco di tutte le mappature dai parametri XDM ad Analytics [qui](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en). Di seguito è riportato un esempio che illustra come i campi XDM productListItems vengono combinati per creare una variabile di prodotto.

Struttura XDM:

```js
              "productListItems": [
                    {
                        "name": "Bahama Shirt",
                        "priceTotal": "12.99",
                        "quantity": 3,
                        "_experience": {
                            "analytics": {
                                "customDimensions" : {
                                    "eVars" : {
                                        "eVar10" : "green",
                                        "eVar33" : "large"
                                    }
                                },
                                "event1to100" : {
                                    "event4" : {
                                        "value" : 1
                                    },
                                    "event10" : {
                                        "value" : 2,
                                        "id" : "abcd"
                                    }
                                }
                            }
                        }
                    }
                ]
```

Parametro &quot;products&quot; risultante passato ad Analytics:

```js
pl = ;Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large
```

## Implementare utilizzando la sintassi della variabile di conversione

La sintassi della variabile di conversione viene utilizzata quando il valore eVar non è disponibile per l&#39;impostazione nel `products` variabile. In genere, questo scenario indica che la pagina non ha contesto del canale di merchandising o del metodo di ricerca. In questi casi, è possibile impostare la variabile merchandising prima di arrivare alla pagina del prodotto e il valore viene mantenuto finché non si verifica l’evento di binding.

Quando si verifica l’evento di binding selezionato durante la configurazione, il valore persistente dell’eVar è associato al prodotto. Ad esempio, se `prodView` è specificato come evento di binding, la categoria merchandising è associata all’elenco di prodotti corrente solo al momento in cui si verifica l’evento. Solo gli eventi di binding successivi possono aggiornare un eVar merchandising già assegnato a un prodotto.

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

Il valore `"Aviary"` per `eVar1` viene assegnato al prodotto `"Canary"`. Tutti gli eventi di successo successivi che coinvolgono questo prodotto vengono accreditati a `"Canary"`. Inoltre, il valore corrente della variabile merchandising è associato a tutti i prodotti successivi fino a quando non viene soddisfatta una delle seguenti condizioni:

* La scadenza dell’eVar (in base all’impostazione &quot;Scade dopo&quot;)
* L’eVar merchandising viene sovrascritto con un nuovo valore.

### Utilizzo di XDM per Edge Collection

Puoi specificare le stesse informazioni utilizzando i campi XDM mappati ai campi di Analytics. È disponibile un elenco di tutte le mappature dai parametri XDM ad Analytics [qui](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en). Il mirroring XDM dell&#39;esempio precedente sarà simile al seguente:

```js
                  "_experience": {
                      "analytics": {
                          "customDimensions": {
                              "eVars": {
                                  "eVar1" : "Aviary"
                              }
                          }
                      }
                  },
                  "commerce": {
                      "productViews" : {
                          "value" : 1
                      }
                  },
                  "productListItems": [
                      {
                          "name": "Canary"
                      }
                  ]
```
