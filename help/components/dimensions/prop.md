---
title: Prop
description: Una dimensione personalizzata che puoi utilizzare nel reporting.
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 8%

---

# Prop

*Questa pagina della guida descrive come funziona prop come dimensione. Per informazioni su come implementare prop, consulta [prop](/help/implement/vars/page-vars/prop.md) nella guida utente Implementa.*

Le proprietà sono variabili personalizzate che puoi utilizzare come desideri. Non persistono oltre l’hit impostato.

>[!TIP]
>
>L’Adobe consiglia di utilizzare [eVar](evar.md) nella maggior parte dei casi. Nelle versioni precedenti di Adobe Analytics, prop e eVar presentavano vantaggi e svantaggi l’uno per l’altro. Tuttavia, Adobe ha migliorato le eVar in modo da soddisfare quasi tutti i casi d’uso per prop.

Se si dispone di [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), puoi allocare queste dimensioni personalizzate a valori specifici dell’organizzazione. Il numero di prop disponibili dipende dal contratto con Adobe. Se il contratto con Adobe lo supporta, sono disponibili fino a 75 proprietà.

## Popolare prop con i dati

Ogni prop raccoglie dati da [`c1` - `c75` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il `c1` parametro stringa query raccoglie dati per prop1, mentre il parametro `c68` il parametro della stringa di query raccoglie i dati per prop68.

AppMeasurement, che compila variabili JavaScript in una richiesta di immagine per la raccolta dati, utilizza le variabili `prop1` - `prop75`. Consulta [prop](/help/implement/vars/page-vars/prop.md) nella Guida utente di implementazione per le linee guida sull’implementazione.

## Elementi dimensionali

Poiché le proprietà contengono stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensionali di ciascuna proprietà. Assicurati di registrare lo scopo di ogni proprietà e degli elementi dimensionali tipici in una [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).

## Distinzione tra maiuscole e minuscole

Per impostazione predefinita, le proprietà non distinguono tra maiuscole e minuscole. Se invii lo stesso valore in casi diversi (ad esempio, `"DOG"` e `"Dog"`), Analysis Workspace li raggruppa nello stesso elemento dimensione. Viene utilizzato il caso del primo valore visualizzato all’inizio del mese di riferimento. Data Warehouse mostra il primo valore rilevato durante il periodo della richiesta.

Puoi fare distinzione tra maiuscole e minuscole in qualsiasi proprietà. Puoi anche disattivare la distinzione tra maiuscole e minuscole per qualsiasi proprietà una volta abilitata. Per attivare o disattivare la distinzione tra maiuscole/minuscole, contatta l’Assistenza clienti Adobe con l’ID della suite di rapporti e le variabili desiderate.

>[!WARNING]
>
>L’attivazione della distinzione tra maiuscole e minuscole può causare il cliff di elementi dimensionali, risultati imprevisti con i segmenti e problemi con i filtri. Adobe consiglia vivamente di alternare questa impostazione tra due periodi di tempo principali, ad esempio l’inizio di un mese o di un anno.

## Valore delle proprietà rispetto alle eVar

Nella maggior parte dei casi, l’Adobe consiglia di utilizzare le eVar. Le eccezioni a questa istruzione sono le seguenti:

* Puoi utilizzare prop nei rapporti in tempo reale. Le eVar richiedono almeno 30 minuti per essere visualizzate nel reporting.
* Le proprietà possono diventare prop elenco, che accettano più valori nello stesso hit. Le variabili elenco sono una variabile separata e sono disponibili solo tre variabili elenco.
* Quando abiliti il percorso in una prop, [Voce](entry-dimensions.md) e [Esci](exit-dimensions.md) le dimensioni diventano immediatamente disponibili. Se desideri dimensioni di entrata e di uscita per le eVar, puoi creare manualmente un segmento.

Consulta [eVar](evar.md) per ulteriori confronti tra prop ed eVar.
