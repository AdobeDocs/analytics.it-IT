---
description: Lo Strumento di confronto segmenti (IQ segmento) rileva le differenze più importanti dal punto di vista statistico tra un numero illimitato di segmenti attraverso un’analisi automatizzata di ciascuna metrica e dimensione a cui hai accesso. Rileva automaticamente le caratteristiche chiave dei segmenti di pubblico che guidano i KPI della tua azienda e ti consente di conoscere il livello di sovrapposizione dei segmenti.
keywords: Analysis Workspace; IQ segmento
seo-description: Lo Strumento di confronto segmenti (IQ segmento) rileva le differenze più importanti dal punto di vista statistico tra un numero illimitato di segmenti attraverso un’analisi automatizzata di ciascuna metrica e dimensione a cui hai accesso. Rileva automaticamente le caratteristiche chiave dei segmenti di pubblico che guidano i KPI della tua azienda e ti consente di conoscere il livello di sovrapposizione dei segmenti.
seo-title: Panoramica di IQ segmento
solution: Analytics
title: Panoramica di IQ segmento
topic: Reports & Analytics
uuid: 80 b 8343 a -8 e 09-4234-9510-1 eecce 18567 f
translation-type: tm+mt
source-git-commit: f5f5b294f503911108e1693b7c6cd128bee659c6

---


# Panoramica di IQ segmento

Lo Strumento di confronto segmenti (IQ segmento) rileva le differenze più importanti dal punto di vista statistico tra un numero illimitato di segmenti attraverso un’analisi automatizzata di ciascuna metrica e dimensione a cui hai accesso. Rileva automaticamente le caratteristiche chiave dei segmenti di pubblico che guidano i KPI della tua azienda e ti consente di conoscere il livello di sovrapposizione dei segmenti.

Gli analisti possono passare molte ore o persino giorni ricercando differenze rilevanti tra i segmenti di ampi gruppi di dimensioni e metriche della tua azienda. Questa analisi non solo è tediosa e dispendiosa dal punto di vista del tempo, ma non consente neanche di rilevare con certezza tutte le differenze chiave di un segmento, con un conseguente grosso impatto sulle tue attività di marketing mirate.

[Confronto dei segmenti su YouTube](https://www.youtube.com/watch?v=fO3PNB93U_w&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=38) (4:46)

Riportiamo alcune nuove intuizioni, grafici e tabelle introdotti con lo Strumento di confronto segmenti:

## “Everyone else” segment {#section_30AEE8181E5D46D9AB27F7CA3815D0CD}

Per comodità, abbiamo aggiunto il segmento «tutti gli altri» in modo che non sia necessario crearlo manualmente. Ad esempio, prendere l'audience Acquirenti. Non devi creare un segmento Non acquirenti, perché è già incluso nel segmento «tutti gli altri» e può essere rapidamente rimosso in caso di aggiunta di un segmento diverso per il confronto.

## Size and overlap {#section_885A71EE458C43189A77B8F552CA346A}

La visualizzazione Dimensione e sovrapposizione mostra le dimensioni comparate di ciascun segmento selezionato e il livello di sovrapposizione tra di essi. Puoi passare il mouse sull’elemento visivo per vedere quanti visitatori si trovavano in ciascuna sezione di sovrapposizione o non sovrapposizione. Puoi fare clic con il pulsante destro del mouse sulla sovrapposizione per creare un nuovo segmento per un’ulteriore analisi. Se due segmenti non si sovrappongono (ad esempio se utilizzi il segmento «tutti gli altri»), potrai vederli anche in questo elemento visivo.

![](assets/size-overlap.png)

## Population summaries {#section_21F2B66C60184A71B89E2982A6FB945D}

A destra dell’elemento visivo Dimensione e crossover, lo Strumento di confronto segmenti mostra il conteggio del visitatore singolo totale in ciascun segmento e la popolazione della sovrapposizione.

![](assets/population_summaries.png)

## Top metrics {#section_E4A38516424949B79A559DC8793071F2}

>[!NOTE]
>
>Gli elementi di riga applicati dopo il confronto dei segmenti non ricevono un punteggio di differenza; la tabella caricherà solo i dati delle metriche per i due segmenti che vengono confrontati

La tabella delle metriche principali visualizza le metriche statisticamente più differenziate tra i due segmenti selezionati. Ogni riga in questa tabella rappresenta una metrica differenziata, valutata in base al modo in cui si differenzia tra i vari segmenti. Le metriche vengono visualizzate anche per ciascun visitatore. In questo modo, se le “visite” appaiono nella tabella, i numeri corrispondenti nella tabella indicano il numero medio di visite per visitatore in ciascun segmento. Forniamo anche un punteggio di differenza, che indica il livello di differenza di questa metrica tra questi due segmenti. Il punteggio 1 rappresenta un’importante differenza statistica, mentre 0 non indica alcuna differenza statistica.

Per dettagli sulle modalità di calcolo del punteggio di differenza di ciascuna tabella, consulta [Test statistici utilizzati nel confronto dei segmenti](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/statistical-test.md#concept_0B6AC754EAED460283D4626983F838F4).

La tabella Metriche principali è simile a una qualsiasi altra tabella utilizzata in Analysis Workspace. Puoi trascinare una metrica qualsiasi nella tabella e ti verrà mostrato il confronto.

Puoi personalizzare la tabella nel modo desiderato. Inoltre, abbiamo aggiunto una nuova icona “Crea elemento visivo” per ciascuna riga nella tabella. Facendo clic su questa icona, si crea una nuova tabella e un elemento visivo sopra lo Strumento di confronto segmenti; questo è utile se preferisci continuare con un’analisi più approfondita in una nuova tabella, per non ingombrare la tabella Metriche principali. Se questa metrica non è pertinente, puoi fare clic sulla “X” per rimuoverla dalla tabella. Infine, come per altre tabelle a forma libera, puoi scorrere l’elenco di metriche visualizzate o visualizzare le 10, 20, 50 e oltre metriche principali, se desideri vedere più dei cinque elementi visualizzati in modo predefinito.

![](assets/top-metrics.png)

Sulla destra della tabella delle metriche si trova una visualizzazione collegata. Come impostazione predefinita, lo Strumento di confronto segmenti mostra la metrica principale nella tabella con tendenze degli ultimi 30 giorni per ciascun segmento. Se desideri visualizzare un’altra metrica che si trova nella tabella Metriche principali, selezionala facendo clic su di essa e l’immagine a destra si aggiorna per mostrare la metrica selezionata.

![](assets/linked-viz.png)

## Top dimension items {#section_439C1782B153427CB4FB85E177146EC0}

>[!NOTE]
>
>Gli elementi di riga applicati dopo il confronto dei segmenti non ricevono un punteggio di differenza; la tabella caricherà solo i dati delle metriche per i due segmenti che vengono confrontati

In modo analogo alla tabella Metriche principali, lo Strumento di confronto segmenti offre la tabella Elementi dimensione principali che mostra gli elementi di dimensione più differenziati tra tutte le dimensioni. Ciascuna riga mostra la percentuale di ciascun segmento che possiede questo elemento della dimensione.

Ad esempio, confrontando il “segmento A” con il “segmento B”, la tabella Elementi dimensione principali potrebbe mostrare che il 100% dei visitatori nel “segmento A” ha l’elemento della dimensione Tipo di browser: Google, posseduto invece solo per il 19,6% dal “segmento B”.

![](assets/top-dimension-item1.png)

A destra della tabella Elementi dimensione principali, lo Strumento di confronto segmenti evidenzia l’elemento della dimensione principale, selezionato insieme ad altri principali elementi della dimensione per il confronto:

![](assets/top-dimension-item.png)

## Top segments table {#section_6A0C39F930564240AF7A157005C7A80B}

>[!NOTE]
>
>Gli elementi di riga applicati dopo il confronto dei segmenti non ricevono un punteggio di differenza; la tabella caricherà solo i dati delle metriche per i due segmenti che vengono confrontati

La tabella Segmenti principali è utile perché mostra i segmenti (diversi dai due segmenti selezionati per il confronto) che si sovrappongono in modo molto diverso tra i due segmenti selezionati. Ad esempio, durante il confronto tra segmento A e segmento B, la tabella Segmenti principali potrebbe mostrare un terzo segmento. “Ripeti visitatori” si sovrappone notevolmente con il segmento A, ma non con il segmento B.

![](assets/top-segments.png)

Inoltre, il segmento aggiuntivo differenziato principale viene visualizzato in un elemento visivo della sovrapposizione sulla destra della tabella:

![](assets/segment-overlap.png)

L’immagine della sovrapposizione indica graficamente la differenza di sovrapposizione tra tutti e tre i segmenti e, come gli altri elementi visivi collegati, facendo clic su ciascun segmento aggiuntivo nella tabella, si aggiorna l’elemento visivo per conformarsi al segmento selezionato.

Fai clic qui per scoprire maggiori informazioni sui [test statistici](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/statistical-test.md#concept_0B6AC754EAED460283D4626983F838F4) utilizzati nel confronto di segmenti.
