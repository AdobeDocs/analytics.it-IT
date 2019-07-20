---
description: Le sottorelazioni complete sono abilitate in tutti i report di conversione, per cui puoi suddividere qualsiasi evar da un'altra evar. Il menu Suddivisione per nella tabella dei report corrisponde al menu standard di Analytics, mantenendo le selezioni coerenti
seo-description: Le sottorelazioni complete sono abilitate in tutti i report di conversione, per cui puoi suddividere qualsiasi evar da un'altra evar. Il menu Suddivisione per nella tabella dei report corrisponde al menu standard di Analytics, mantenendo le selezioni coerenti
seo-title: Sottorelazioni
solution: Analytics
title: Sottorelazioni
topic: Reports & Analytics
uuid: ca 6 df 50 f -5 d 4 c -4 f 91-bf 27-86 ccd 01391 a 2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Sottorelazioni

Le sottorelazioni complete sono abilitate in tutti i report di conversione, per cui puoi suddividere qualsiasi evar da un'altra evar. Il menu Suddivisione per nella tabella dei report corrisponde al menu standard di Analytics, mantenendo le selezioni coerenti

![](assets/subrelations.png)

## How Subrelations Work {#section_5BD862BB74FE411B96B59204520E4631}

Per illustrare il funzionamento delle sottorelazioni, prendete in considerazione il seguente esempio:

1. Un utente accede al sito tramite Campaign_ A e arriva nella home page.
1. L'utente cerca "gatti" e visualizza i risultati della ricerca. Evar 1 tiene traccia dei termini di ricerca interni.
1. L'utente si iscrive a una mailing list, che viene tracciata utilizzando l'evento 1.
1. Un utente diverso accede al sito anche tramite Campaign_ A e arriva nella pagina principale.
1. Questo utente cerca «kittens», riceve i risultati della ricerca (evar 1) e si iscrive alla mailing list (event 1).

Se hai rimosso un rapporto di codice di tracciamento, vedi quanto segue:

![](assets/subrel_1.png)

Se hai estratto un rapporto evar 1, vedi quanto segue:

![](assets/subrel_2.png)

Se hai sottocorrelato il rapporto Campagna per evar 1, riceveresti quanto segue:

![](assets/subrel_3.png)

Se hai sottocorrelato il rapporto evar 1 per Campagne, riceveresti quanto segue:

![](assets/subrel_4.png)

A causa della natura persistente delle variabili di conversione, sono disponibili due colonne di dati per memorizzare i valori evar; il valore che viene attivato e il valore che persiste. Se dovessimo osservare un'esportazione di dati grezzi per questo esempio, questo verrà visualizzato (semplificata per questo esempio):

![](assets/subrel_5.png)

Il nostro back-end funziona consentendo a post_ campaign e post_ evar 1 di mantenere i valori definiti in campaign ed evar 1. I rapporti delle didascalie guardano solo gli hit che contengono eventi di successo (righe evidenziate nel giallo chiaro). Quindi, compilano i report di sottorelazione in base ai valori persistenti (in questo esempio post_ campaign e post_ evar 1, celle evidenziate in giallo brillante).

In pratica, le sottorelazioni seguono i passaggi seguenti per compilare il rapporto:

* Isolate le richieste di immagini contenenti gli eventi di successo che state visualizzando nel rapporto.
* Restituisce i valori persistenti da ogni variabile di conversione utilizzata nella sottorelazione.
* Organizzate i valori in base all'ordine di sottorelazione. Se una variabile non ha un valore persistente (ad esempio, se una evar non è mai stata definita o scaduta), viene indicata in "None" (Nessuno).

