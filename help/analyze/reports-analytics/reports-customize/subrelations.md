---
description: Le sottorelazioni complete sono abilitate su tutti i rapporti di conversione, in modo da poter suddividere qualsiasi eVar per un'altra eVar. Il menu Suddivisione per nella tabella dei rapporti corrisponde al menu standard di reporting di Analytics, mantenendo le selezioni coerenti
seo-description: Le sottorelazioni complete sono abilitate su tutti i rapporti di conversione, in modo da poter suddividere qualsiasi eVar per un'altra eVar. Il menu Suddivisione per nella tabella dei rapporti corrisponde al menu standard di reporting di Analytics, mantenendo le selezioni coerenti
seo-title: Sottorelazioni
solution: Analytics
title: Sottorelazioni
topic: Reports and Analytics
uuid: ca6df50f-5d4c-4f91-bf27-86ccd01391a2
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Sottorelazioni

Le sottorelazioni complete sono abilitate su tutti i rapporti di conversione, in modo da poter suddividere qualsiasi eVar per un'altra eVar. Il menu Suddivisione per nella tabella dei rapporti corrisponde al menu standard di reporting di Analytics, mantenendo le selezioni coerenti

![](assets/subrelations.png)

## Come funzionano le sottorelazioni {#section_5BD862BB74FE411B96B59204520E4631}

Per illustrare il funzionamento delle sottorelazioni, prendere in considerazione l'esempio seguente:

1. Un utente accede al sito tramite Campaign_A e arriva sulla pagina principale.
1. L'utente cerca 'gatti' e visualizza i risultati della ricerca. eVar1 tiene traccia dei termini di ricerca interni.
1. L'utente si iscrive a una mailing list, tracciata utilizzando event1.
1. Un altro utente accede al sito anche tramite Campaign_A e arriva sulla pagina principale.
1. Questo utente cerca 'gattini', visualizza i risultati di ricerca (eVar1), e anche gli abbonati alla mailing list (event1).

Se hai estratto un rapporto sul codice di tracciamento, vedrai quanto segue:

![](assets/subrel_1.png)

Se hai estratto un rapporto eVar1, vedrai quanto segue:

![](assets/subrel_2.png)

Se hai correlato il rapporto Campagna per eVar1, ottieni quanto segue:

![](assets/subrel_3.png)

Se hai correlato il rapporto eVar1 per Campagne, ottieni quanto segue:

![](assets/subrel_4.png)

A causa della natura persistente delle variabili di conversione, per memorizzare i valori eVar sono utilizzate due colonne di dati. il valore che viene attivato e il valore che persiste. Se si considerasse un'esportazione di dati non elaborati per questo esempio, si verificherebbe quanto segue (semplificato per questo esempio):

![](assets/subrel_5.png)

Il nostro backend funziona consentendo a post_campaign e post_evar1 di mantenere i valori definiti in campaign ed evar1. I rapporti sulle sottorelazioni esaminano specificamente solo gli hit contenenti eventi di successo (righe evidenziate in giallo chiaro). Vengono quindi compilati i rapporti delle sottorelazioni in base ai valori persistenti (in questo caso, post_campaign e post_evar1, celle evidenziate in giallo chiaro).

In sostanza, le sottorelazioni seguono questi passaggi per compilare il rapporto:

* Isolate le richieste di immagini contenenti gli eventi di successo che state visualizzando nel rapporto.
* Restituisce i valori persistenti da ogni variabile di conversione utilizzata nella sottorelazione.
* Organizzare i valori in base all'ordine della sottorelazione. Se una variabile non ha un valore persistente (ad esempio, se un'eVar non è mai stata definita o è scaduta), verrà creata con un pacchetto "None".

