---
title: Risoluzione dei problemi di presenza dei dati
description: Scopri i passaggi che puoi eseguire quando non visualizzi dati nei report.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---


# Risoluzione dei problemi di presenza dei dati

In  Analysis Workspace, alcune impostazioni di progetto restituiscono zero righe. In Reporting e analisi, la visualizzazione di alcuni rapporti restituisce il messaggio seguente:

**&quot;Nessun dato per il criterio selezionato.&quot;**

Per determinare il motivo per cui un rapporto non mostra dati, attenersi alla procedura descritta di seguito.

## I dati esistono ma vengono filtrati

La suite di rapporti contiene dati, ma i componenti specifici utilizzati nel rapporto filtrano tutti i dati.

* **Segmenti**: I segmenti possono impedire facilmente la visualizzazione di tutti i dati in un rapporto. Controlla tutte le definizioni dei segmenti e rimuovi tutti i segmenti per verificare se un segmento causa la mancata visualizzazione dei dati.
* **Metriche**: Verificate che vengano utilizzate le metriche corrette. Cambia la metrica in [Occorrenze](/help/components/metrics/occurrences.md) per essere sicuri che la metrica non sia il collaboratore di un report senza dati.
* **Intervalli** di date: Gli intervalli di date troppo lunghi nel passato o in qualsiasi momento nel futuro non restituiscono i dati. Il criterio [di conservazione dei](data-retention.md) dati dell&#39;organizzazione determina la distanza di conservazione dei dati.
* **Filtri**: Rimuovete tutti i filtri di ricerca dal rapporto.

## I dati non esistono

Se non ci sono segmenti, la metrica è Occorrenze, l&#39;intervallo di date è il mese corrente e non ci sono filtri di ricerca, verifica quanto segue:

* **Verifica la suite** di rapporti: Accertatevi di essere in una suite di rapporti che contenga dati. Molte organizzazioni dispongono di suite di rapporti nuove, di test o di sviluppo che in genere non contengono molti dati.
* **Latenza**: Se si visualizzano dati recenti, è possibile che i dati siano in ritardo. Per ulteriori informazioni, consulta [Latenza](latency.md) .
* **Convalida raccolta** dati: Andate alla proprietà Web che la suite di rapporti deve tenere traccia e aprite il debugger [del Adobe](https://docs.adobe.com/content/help/it-IT/debugger/using/experience-cloud-debugger.html). Accertatevi che sia presente una richiesta di immagine Analytics quando caricate una pagina. Se visualizzi una richiesta di immagine, accertati che utilizzi l’ID suite di rapporti corretto, che includa un [currencyCode](/help/implement/vars/config-vars/currencycode.md)valido e che il supporto [](/help/implement/vars/page-vars/timestamp.md) delle marche temporali corrisponda alle corrispondenze tra la richiesta di immagine e la suite di rapporti.
