---
description: Le relazioni secondarie complete sono abilitate in tutti i rapporti di conversione, in modo da poter suddividere qualsiasi eVar per un’altra eVar. Il menu Raggruppa per nella tabella dei rapporti corrisponde al menu standard di reporting di Analytics, mantenendo le selezioni coerenti
title: Relazioni secondarie
uuid: ca6df50f-5d4c-4f91-bf27-86ccd01391a2
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 615ed00e-91cd-45de-ae1f-e0d09ff01d26
source-git-commit: 4ddc2640aa8b3a22411c86ff8bfe0ecf345a3d63
workflow-type: ht
source-wordcount: '395'
ht-degree: 100%

---

# Relazioni secondarie

{{ra-eol}}

Le relazioni secondarie complete sono abilitate in tutti i rapporti di conversione, in modo da poter suddividere qualsiasi eVar per un’altra eVar. Il menu Raggruppa per nella tabella dei rapporti corrisponde al menu standard di reporting di Analytics, mantenendo le selezioni coerenti

![](assets/subrelations.png)

## Come funzionano le relazione secondarie {#section_5BD862BB74FE411B96B59204520E4631}

Per comprendere meglio il funzionamento delle relazioni secondarie, perndi in considerazione l’esempio seguente:

1. Un utente accede al sito tramite Campaign_A e raggiunge la pagina Home.
1. L&#39;utente cerca il termine “gatti” e gli vengono mostrati i risultati della ricerca. L’eVar1 tiene traccia dei termini di ricerca interni.
1. L’utente si iscrive a una mailing list che viene tracciata utilizzando event1.
1. Anche un altro utente accede al sito tramite Campaign_A e raggiunge la tua pagina Home.
1. Questo utente cerca il termine “gattini”, gli vengono mostrati i risultati di ricerca (eVar1) e si iscrive alla mailing list (event1).

Se hai estratto un rapporto sul codice di tracciamento, visualizzerai quanto segue:

![](assets/subrel_1.png)

Se hai estratto un rapporto sull’eVar1, visualizzerai quanto segue:

![](assets/subrel_2.png)

Se hai correlato il rapporto della campagna in base a eVar1, otterrai quanto segue:

![](assets/subrel_3.png)

Se hai correlato il rapporto eVar1 in base alle campagne, otterrai quanto segue:

![](assets/subrel_4.png)

Data la natura persistente delle variabili di conversione, esistono due colonne di dati utilizzate per memorizzare i valori eVar; il valore che viene attivato e il valore che persiste. Se per questo esempio dovessimo esaminare un’esportazione di dati non elaborati, sarebbe simile a questa (semplificata per questo esempio):

![](assets/subrel_5.png)

Il backend funziona consentendo a post_campaign e post_evar1 di mantenere i valori definiti nella campagna e nell’evar1. I rapporti delle relazioni secondarie esaminano specificamente solo gli hit contenenti eventi di successo (righe evidenziate in giallo chiaro). Quindi popolano i rapporti delle relazioni secondarie in base ai valori persistenti (in questo caso post_campaign e post_evar1, celle evidenziate in giallo chiaro).

In sostanza, per popolare il rapporto, le relazioni secondarie seguono i passaggi seguenti:

* Individua le richieste di immagini contenenti gli eventi di successo che stai visualizzando nel rapporto.
* Restituisce i valori persistenti da ogni variabile di conversione utilizzata nella relazione secondaria.
* Organizza i valori in base all’ordine della relazione secondaria. Se una variabile non ha un valore persistente (ad esempio se un eVar non è mai stato definito o è scaduto), verrà inserita nel bucket “Nessuno”.
