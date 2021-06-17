---
description: 'Scopri '
title: Tipo di metrica e attribuzione
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 73161e10a2f70cd0e874d2c1de6d4f418b25aefb
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 5%

---

# Tipo di metrica e attribuzione

Selezionando l’icona a forma di ingranaggio accanto a una metrica puoi specificare il tipo di metrica e il modello di attribuzione.

## Tipi di metriche

![](assets/cm_type_alloc.png)

| Tipi di metriche | Definizione |
|---|---|
| Standard | Queste metriche sono le stesse utilizzate nel reporting [!DNL Analytics] standard. Se una formula è costituita da una singola metrica standard, visualizza dati identici alla sua controparte metrica non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singolo elemento di riga. Ad esempio, [Ordini] / [Visite] prende gli ordini per quell’elemento specifico e lo divide per il numero di visite per quell’elemento specifico. |
| Totale | Utilizza il totale per il periodo di reporting in ogni riga. Se una formula è costituita da una singola metrica totale, visualizza lo stesso numero totale su ogni voce di riga. Le metriche totali sono utili per creare metriche calcolate confrontate con i dati totali del sito. Ad esempio, [Ordini] / [Visite totali] mostra la proporzione di ordini rispetto a TUTTE le visite al sito, non solo le visite alla voce di riga specifica. |

## Modello di attribuzione colonna

>[!IMPORTANT]
>
>[Attribution ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution/attribution.html) IQ ha modificato il modo in cui vengono valutati i modelli di allocazione nelle metriche calcolate. Come parte di questa modifica, le metriche calcolate che utilizzano un modello di allocazione non predefinito sono state migrate a nuovi modelli di attribuzione migliorati:
>
>* Per un elenco completo dei modelli di attribuzione non predefiniti e degli intervalli di lookback supportati, consulta la documentazione [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution/attribution.html) .
>* I modelli di allocazione &quot;Marketing Channel Last Touch&quot; (Ultimo contatto canale marketing) e &quot;Marketing Channel First Touch&quot; (Primo contatto canale marketing) verranno migrati ai nuovi modelli di attribuzione &quot;Last Touch&quot; (Ultimo contatto) e &quot;First Touch&quot; (Primo contatto canale di marketing) rispettivamente (Nota: &quot;Marketing Channels&quot; (Canali di marketing) non verrà deprecato, ma solo i due modelli di allocazione che compaiono nelle metriche calcolate.
>* Inoltre verrà corretto il metodo di calcolo dell’allocazione lineare. Per i clienti che utilizzano metriche calcolate con modelli di allocazione &quot;Lineare&quot;, i rapporti possono cambiare leggermente per riflettere il nuovo modello di attribuzione corretto. La modifica alle metriche calcolate si rifletterà in Analysis Workspace, Reports &amp; Analytics, API di reporting e Report Builder. Per ulteriori informazioni, consulta **Come funziona l’allocazione lineare (a partire dal 19 luglio 2018**, di seguito.

>



## Come funziona l’allocazione lineare (dal 19 luglio 2018)

Nel luglio 2018, Adobe ha modificato il modo in cui viene riportata l’allocazione lineare per le metriche calcolate. Questa modifica interessa Analysis Workspace, Reports &amp; Analytics, Report Builder, Activity Map e le API di reporting. La modifica interessa principalmente eVar e altre dimensioni con persistenza. Tieni presente che queste modifiche si applicano solo alle metriche calcolate e non hanno alcun impatto sugli altri rapporti che utilizzano l’allocazione lineare (ad esempio il rapporto Pagine in Reports &amp; Analytics). Altri rapporti che utilizzano l&#39;allocazione lineare continueranno a utilizzare il metodo esistente di allocazione lineare.

L’esempio seguente illustra come le metriche calcolate con allocazione lineare cambieranno nei rapporti:

|  | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 | Hit 6 | Hit 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Dati inviati in | PROMO A | - | PROMO A | PROMO B | - | PROMO C | $10 |
| eVar ultimo contatto | PROMO A | PROMO A | PROMO A | PROMO B | PROMO B | PROMO C | $ 10 |
| eVar primo contatto | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | $ 10 |
| Esempio di prop | PROMO A | - | PROMO A | PROMO B | - | PROMO C | $ 10 |

In questo esempio, i valori A, B e C sono stati inviati in una variabile sugli hit 1, 3, 4 e 6 prima di un acquisto di 10 $ sull’hit 7. Nella seconda riga, tali valori persistono tra i risultati in base all’ultima visita di contatto. La terza riga illustra la persistenza di una visita di primo contatto. Infine, l’ultima riga illustra come registrare i dati per una proprietà che non presenta persistenza.

## Differenze nel funzionamento dell’allocazione lineare in Reporting e analisi rispetto a Workspace

Esistono alcune differenze nel funzionamento dell’attribuzione lineare tra questi due strumenti:

* In Reports &amp; Analytics, l’attribuzione lineare (elaborata) è sempre basata su visite, mentre in Workspace può essere basata su visite o visitatori.
* In Reports &amp; Analytics, se non viene passato alcun valore al primo hit di una visita, il valore (iniziale) persisterebbe dalla visita precedente. NON è così in Workspace (Attribution IQ). Se non viene passato alcun valore al primo hit di una visita, il valore iniziale è &quot;None&quot;.

## Funzionamento dell’allocazione lineare prima di luglio 2018

Prima del 19 luglio 2018, l’attribuzione lineare era stata calcolata dopo che si era già verificata la persistenza del primo contatto o dell’ultimo contatto. Ciò significa che per l’ultimo eVar touch di cui sopra, i $ 10 sarebbero distribuiti come segue: A = 10 * (3/6) = $5, B = 10 * (2/6) = $3,33, C = 10 * (1/6) = $1,67.

Per l’eVar di primo contatto di cui sopra, tutti i $ 10 vengono dati a A. Per il prop: A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50 e C = 10 * (1/4) = $2,50. Per riepilogare l&#39;allocazione lineare come funzionava in precedenza:

| Valori | eVar ultimo contatto corrente | eVar primo contatto corrente | Prop corrente |
|---|---|---|---|
| PROMO A | $ 5,00 | $ 10,00 | $ 5,00 |
| PROMO B | $ 3,33 | $0 | $ 2,50 |
| PROMO C | $ 1,67 | $0 | $ 2,50 |
| Totale | $ 10,00 | $ 10,00 | $ 10,00 |

**Riepilogo del funzionamento dell&#39;allocazione lineare**

Invece di utilizzare i valori persistenti basati sull’ultimo contatto o sul primo contatto, ora [!DNL Analytics] utilizza solo i valori passati (la prima riga della tabella superiore). Di conseguenza, le impostazioni di allocazione delle dimensioni non influiscono più sul modo in cui viene calcolata l’allocazione lineare (ovvero proprietà ed eVar verranno trattate nello stesso modo) e i risultati riflettono ciò che è stato originariamente passato invece dei valori di primo o ultimo contatto che potrebbero essere persistiti. Quindi, in tutti e tre i casi, A = 10 * (2/4) = $5, B = 10 * (1/4) = $2,50 e C = 10 * (1/4) = $2,50.

| Valori | Nuovo eVar ultimo contatto | Nuovo eVar primo contatto | Nuovo prop. |
|---|---|---|---|
| PROMO A | $ 5,00 | $ 5,00 | $ 5,00 |
| PROMO B | $ 2,50 | $ 2,50 | $ 2,50 |
| PROMO C | $ 2,50 | $ 2,50 | $ 2,50 |
| Totale | $ 10,00 | $ 10,00 | $ 10,00 |
