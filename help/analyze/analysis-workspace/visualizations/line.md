---
description: Utilizzare la visualizzazione delle linee per rappresentare set di dati con tendenze (basati sul tempo)
title: Linee
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 34db4e99589827fd41f642788e3409834b96d78a
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 16%

---


# Linee

Questa visualizzazione rappresenta le metriche con linee che mostrano come cambiano i valori nel tempo. Un grafico a linee può essere usato solo con una dimensione temporale.

## Impostazioni visualizzazione

>[!IMPORTANT]
>
> Alcune impostazioni di visualizzazione Linea, come Mostra linea di tendenza, sono attualmente in fase di test limitati. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/landing/an-releases.html).

Fai clic sull’icona a forma di ingranaggio in alto a destra della visualizzazione Linea per accedere alle impostazioni [**di**](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html#section_D3BB5042A92245D8BF6BCF072C66624B) visualizzazione disponibili. Le impostazioni sono suddivise in categorie:

* Generale: impostazioni comuni tra i tipi di visualizzazione
* Asse: impostazioni che influiranno sull’asse x o y della visualizzazione della linea
* Sovrapposizioni - opzioni per aggiungere ulteriore contesto alla serie mostrata nella visualizzazione a linee.

### Modificare la granularità

Nelle [impostazioni di visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_D3BB5042A92245D8BF6BCF072C66624B), un elenco a discesa di granularità permette di cambiare una visualizzazione con tendenza (ad esempio un grafico a linee) da base giornaliera a settimanale, mensile e così via. La granularità viene aggiornata anche nella tabella dell&#39;origine dati.

### Mostra min o max

In Impostazioni **visualizzazione > Sovrapposizioni > Mostra min/max**, potete sovrapporre un’etichetta di valore minimo e massimo per evidenziare rapidamente picchi e valli in una metrica.

### Mostra sovrapposizione linea di tendenza

In Impostazioni **visualizzazione > Sovrapposizioni > Mostra linea di tendenza**, puoi scegliere di aggiungere una linea di tendenza di regressione alla serie di linee. Le linee di tendenza consentono di rappresentare un pattern più chiaro nei dati.

Tutti i modelli sono adattabili utilizzando i minimi quadrati ordinari:

| Modello | Descrizione |
|---|---|
| Lineare | Crea una linea retta adatta per set di dati lineari semplici ed è utile quando i dati aumentano o diminuiscono a una velocità costante. Equazione: y = a + b * x |
| Logaritmico | Crea una linea curva di adattamento ottimale ed è utile quando il tasso di variazione nei dati aumenta o diminuisce rapidamente e poi si livella. Una linea di tendenza logaritmica può usare valori negativi e positivi. Equazione: y = a + b * log(x) |
| Esponenziale | Crea una linea curva ed è utile quando i dati aumentano o scendono a ritmi costantemente crescenti. Questa opzione non deve essere utilizzata se i dati contengono valori zero o negativi. Equazione: y = a +<sup>eb * x |
| Alimentazione | Crea una linea curva ed è utile per i set di dati che confrontano misurazioni che aumentano a una velocità specifica. Questa opzione non deve essere utilizzata se i dati contengono valori zero o negativi. Equazione: y = a *<sup>xb |
| Quadratico | Trova la soluzione ottimale per un set di dati a forma di parabola (concavo verso l’alto o il basso). Equazione: y = a + b * x + c * x<sup>2 |
| Polinomio | Utile quando il set di dati varia, ad esempio analizzando guadagni e perdite su un insieme di dati di grandi dimensioni. Equazione: y = a + b * x + .. + k *<sup>xorder |
