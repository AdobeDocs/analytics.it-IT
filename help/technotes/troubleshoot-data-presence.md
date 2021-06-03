---
title: Risoluzione dei problemi di presenza dei dati
description: Scopri quali passi puoi compiere quando non visualizzi i dati nei rapporti.
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 1%

---


# Risoluzione dei problemi di presenza dei dati

In Analysis Workspace, alcune configurazioni di progetto restituiscono zero righe. In Reports &amp; Analytics, la visualizzazione di alcuni rapporti restituisce il seguente messaggio:

**&quot;Nessun dato per il criterio selezionato.&quot;**

Utilizza i seguenti passaggi per determinare il motivo per cui un report non mostra dati.

## I dati esistono ma vengono filtrati

La suite di rapporti contiene dati, ma i componenti specifici utilizzati nel rapporto filtrano tutti i dati.

* **Segmenti**: I segmenti possono impedire facilmente la visualizzazione di tutti i dati in un rapporto. Controlla tutte le definizioni dei segmenti e rimuovi tutti i segmenti per vedere se un segmento causa la mancata visualizzazione dei dati.
* **Metriche**: Verifica che siano utilizzate le metriche corrette. Modifica la metrica in [Occorrenze](/help/components/metrics/occurrences.md) per assicurarti che la metrica non sia il contributore a un rapporto senza dati.
* **Intervalli** di date: Gli intervalli di date troppo lontani nel passato o in qualsiasi momento nel futuro non restituiscono i dati. I [criteri di conservazione dei dati](data-retention.md) della tua organizzazione determinano la distanza di conservazione dei dati.
* **Filtri**: Rimuovi tutti i filtri di ricerca dal report.

## I dati non esistono

Se non sono presenti segmenti, la metrica è Occorrenze, l’intervallo di date è il mese corrente e non sono disponibili filtri di ricerca, controlla quanto segue:

* **Verifica la suite** di rapporti: Assicurati di essere in una suite di rapporti che contiene dati. Molte organizzazioni dispongono di suite di rapporti nuove, di test o di sviluppo che in genere non contengono molti dati.
* **Latenza**: Se si visualizzano dati recenti, i dati potrebbero essere solo in ritardo. Per ulteriori informazioni, consulta [Latenza](latency.md) .
* **Convalida raccolta** dati: Passa alla proprietà web di cui la suite di rapporti deve tenere traccia e apri  [Adobe Debugger](https://docs.adobe.com/content/help/it-IT/experience-cloud/user-guides/home.translate.html). Assicurati che sia presente una richiesta di immagine Analytics durante il caricamento di una pagina. Se ricevi una richiesta di immagine, accertati che utilizzi l’ID suite di rapporti corretto, che includa un [currencyCode](/help/implement/vars/config-vars/currencycode.md) valido e che il [supporto timestamp](/help/implement/vars/page-vars/timestamp.md) corrisponda tra la richiesta di immagine e la suite di rapporti.
