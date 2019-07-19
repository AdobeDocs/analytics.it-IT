---
description: nulle
keywords: Implementazione di Analytics
seo-description: nulle
seo-title: Panoramica delle variabili merchandising
solution: Analytics
title: Panoramica delle variabili merchandising
topic: Sviluppatore e implementazione
uuid: 2 ccf 516 a-a 7 ee -48 ab -92 aa -414228 a 4102 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Panoramica delle variabili merchandising

Quando si misura il successo di campagne esterne o termini di ricerca esterni, si desidera generalmente che un singolo valore riceva credito per tutti gli eventi di successo che si verificano. Ad esempio, se un cliente fa clic su un collegamento in una campagna e-mail per visitare il sito Web, tutti gli acquisti effettuati come risultato dovrebbero essere accreditati su tale campagna.

Ma cosa succede agli eventi basati su ricerca interna o esplorando la categoria quando un cliente cerca più elementi? Ad esempio, un cliente cerca il sito per «goggles» e quindi aggiunge una coppia al carrello:

![](assets/merch-example-goggles.png)

Prima di eseguire il checkout, il cliente cerca "inverno", quindi aggiunge una giacca verso il basso al carrello:

![](assets/merch-example-coat.png)

Al termine dell'acquisto, se l'allocazione non è stata modificata da Più recente, verrà visualizzata una ricerca interna «cappotto inverno» con l'acquisto di una coppia di goggles. Buona per "inverno", ma insoddisfacente per decisioni di marketing:

| Termine ricerca interno | Ricavi |
|---|---|
| inverno | $157 |

**Come risolvere il problema con le variabili di merchandising**

Le variabili merchandising tra categorie, o «evar merchandising», consentono di assegnare il valore corrente di un evar a un prodotto al momento dell'evento di successo. Questo valore rimane collegato a tale prodotto, anche se uno o più nuovi valori vengono impostati successivamente per quella particolare evar.

Se il merchandising è abilitato per evar nell'esempio precedente, il termine di ricerca «goggles» è associato a Fernie Snow Goggles e il termine di ricerca «inverno» è associato alla giacca di El Gordo Giù. Le variabili di merchandising assegnano entrate a livello di prodotto, quindi ogni termine riceve credito per la quantità di ricavi per il prodotto a cui è associato:

| Termine ricerca interno | Ricavi |
|---|---|
| inverno | $119 |
| goggles | $38 |

