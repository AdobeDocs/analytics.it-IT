---
description: Scopri
title: Tipo di metrica e attribuzione
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 6%

---

# Tipo di metrica e attribuzione

Selezionando l’icona a forma di ingranaggio accanto a una metrica puoi specificare il tipo di metrica e il modello di attribuzione.

## Tipi di metriche

![](assets/cm_type_alloc.png)

| Tipi di metriche | Definizione |
|---|---|
| Standard | Queste metriche sono le stesse utilizzate in Standard [!DNL Analytics] reportistica. Se una formula è costituita da una singola metrica standard, visualizza dati identici alla sua controparte metrica non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singola riga. Ad esempio: [Ordini] / [Visite] prende ordini per quella voce specifica e lo divide per il numero di visite per quella voce specifica. |
| Totale | Utilizza il totale per il periodo di reporting in ogni voce. Se una formula è costituita da una singola metrica totale, visualizza lo stesso numero totale su ogni riga. Le metriche totali sono utili per creare metriche calcolate che si confrontano con i dati totali del sito. Ad esempio: [Ordini] / [Visite totali] mostra la proporzione di ordini rispetto a TUTTE le visite al sito, non solo le visite alla voce specifica. |

## Modello di attribuzione colonna

>[!IMPORTANT]
>
>[Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) è stato rivisto il modo in cui vengono valutati i modelli di allocazione nelle metriche calcolate. Come parte di questa modifica, le metriche calcolate che utilizzano un modello di allocazione non predefinito sono state migrate a nuovi modelli di attribuzione migliorati:
>
>* Per un elenco completo dei modelli di attribuzione e degli intervalli di lookback non predefiniti supportati, consulta [Modelli di attribuzione e intervalli di lookback](/help/analyze/analysis-workspace/attribution/models.md).
>* I modelli di allocazione &quot;Marketing Channel Last Touch&quot; e &quot;Marketing Channel First Touch&quot; verranno migrati ai nuovi modelli di attribuzione &quot;Last Touch&quot; e &quot;First Touch&quot; rispettivamente (Nota: &quot;Marketing Channels&quot; non verrà dichiarato obsoleto, verranno aggiornati solo i due modelli di allocazione visualizzati nelle metriche calcolate).
>* Inoltre verrà corretto il metodo con cui viene calcolata l’allocazione lineare. Per i clienti che utilizzano metriche calcolate con modelli di allocazione &quot;Lineare&quot;, i rapporti possono cambiare leggermente per riflettere il nuovo modello di attribuzione corretto. La modifica alle metriche calcolate si rifletterà in Analysis Workspace, Reports &amp; Analytics, API di reporting e Report Builder. Per ulteriori informazioni, consulta **Come funziona l’allocazione lineare (dal 19 luglio 2018)**, di seguito.


## Funzionamento dell’allocazione lineare (dal 19 luglio 2018)

A luglio 2018, Adobe ha modificato il modo in cui viene segnalata l’allocazione lineare per le metriche calcolate. Questa modifica interessa Analysis Workspace, Reports &amp; Analytics, Report Builder, Activity Map e le API di reporting. La modifica interessa principalmente le eVar e altre dimensioni con persistenza. Tieni presente che queste modifiche si applicano solo alle metriche calcolate e non influiscono su altri rapporti che utilizzano l’allocazione lineare (come il rapporto Pagine in Reports &amp; Analytics). Altre relazioni che utilizzano l&#39;allocazione lineare continueranno a utilizzare il metodo esistente.

L’esempio seguente illustra il modo in cui le metriche calcolate con allocazione lineare cambieranno nel reporting:

|  | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 | Hit 6 | Hit 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Dati inviati in | PROMOZIONE A | - | PROMOZIONE A | PROMOZIONE B | - | PROMOZIONE C | $10 |
| EVar ultimo contatto | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE B | PROMOZIONE B | PROMOZIONE C | $10 |
| EVar primo contatto | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | $10 |
| Esempio di prop | PROMOZIONE A | - | PROMOZIONE A | PROMOZIONE B | - | PROMOZIONE C | $10 |

In questo esempio, i valori A, B e C sono stati inviati in una variabile negli hit 1, 3, 4 e 6 prima che fosse effettuato un acquisto da 10 $ nell’hit 7. Nella seconda riga, tali valori persistono tra gli hit in base alla visita di ultimo contatto. La terza riga illustra la persistenza di una visita di primo contatto. Infine, l’ultima riga illustra come verranno registrati i dati per una proprietà che non ha persistenza.

## Differenze nel funzionamento dell’allocazione lineare in Reports &amp; Analytics rispetto a Workspace

Esistono alcune differenze nel funzionamento dell’attribuzione lineare tra questi due strumenti:

* In Reports &amp; Analytics, l’attribuzione lineare (elaborata) è sempre basata sulle visite, mentre in Workspace può essere basata sulle visite o sui visitatori.
* In Reports &amp; Analytics, se non veniva passato alcun valore al primo hit di una visita, il valore (iniziale) persisteva dalla visita precedente. Questo NON avviene in Workspace (Attribution IQ). Se non viene passato alcun valore al primo hit di una visita, allora &quot;Nessuno&quot; è il valore iniziale.

## Funzionamento dell’allocazione lineare prima di luglio 2018

Prima del 19 luglio 2018, l’attribuzione lineare era calcolata dopo che si era già verificato il primo contatto o la persistenza dell’ultimo contatto. Ciò significava che per l’ultimo eVar di contatto precedente, il $ 10 sarebbe stato distribuito come segue: A = 10 &#42; (3/6) = $5, B = 10 &#42; (2/6) = $ 3,33, C = 10 &#42; (1/6) = $1,67.

Per l’eVar di primo contatto qui sopra, tutti i $ 10 vengono dati ad A. Per la proprietà: A = 10 &#42; (2/4) = $5, B = 10 &#42; (1/4) = $2,50, e C = 10 &#42; (1/4) = $2,50. Per riepilogare l&#39;allocazione lineare come in precedenza:

| Valori | EVar ultimo contatto corrente | EVar corrente primo contatto | Proprietà corrente |
|---|---|---|---|
| PROMOZIONE A | $ 5,00 | $10.00 | $ 5,00 |
| PROMOZIONE B | $3.33 | $0 | $ 2,50 |
| PROMOZIONE C | $1.67 | $0 | $ 2,50 |
| Totale | $10.00 | $10.00 | $10.00 |

**Riepilogo del funzionamento dell&#39;allocazione lineare**

Invece di utilizzare i valori persistenti in base all’ultimo contatto o al primo contatto, [!DNL Analytics] ora utilizza solo i valori passati (la prima riga della tabella superiore). Di conseguenza, le impostazioni di allocazione delle dimensioni non influiscono più sul modo in cui viene calcolata l’allocazione lineare (ovvero prop ed eVar verranno trattate allo stesso modo) e i risultati riflettono ciò che è stato originariamente trasmesso, anziché i valori di primo o ultimo contatto che possono essere persistiti. In tutti e tre i casi, A = 10 &#42; (2/4) = $5, B = 10 &#42; (1/4) = $2,50, e C = 10 &#42; (1/4) = $2,50.

| Valori | Nuovo eVar ultimo contatto | Nuovo eVar First Touch | Nuova proprietà |
|---|---|---|---|
| PROMOZIONE A | $ 5,00 | $ 5,00 | $ 5,00 |
| PROMOZIONE B | $ 2,50 | $ 2,50 | $ 2,50 |
| PROMOZIONE C | $ 2,50 | $ 2,50 | $ 2,50 |
| Totale | $10.00 | $10.00 | $10.00 |
