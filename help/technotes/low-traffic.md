---
description: Quando un report contiene molti valori univoci, Adobe utilizza l’elemento dimensione Traffico ridotto per migliorarne le prestazioni.
title: Valore Traffico ridotto in Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 42d044c3c56f13a232b721ef60f64bcf622ffa9f
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 8%

---

# Valore [!UICONTROL Low-Traffic] in Adobe Analytics

Quando una dimensione contiene milioni di valori univoci, Adobe fornisce funzionalità per garantire che i valori più importanti vengano visualizzati nel rapporto in modo tempestivo. I valori univoci raccolti oltre una determinata soglia sono elencati in un elemento dimensione con etichetta **[!UICONTROL Low-Traffic]**.

L&#39;elemento dimensione [!UICONTROL Low-Traffic] consente ad Adobe di garantire che i rapporti vengano restituiti in modo tempestivo, inserendo valori univoci eccessivi e raggruppandoli.

La logica [!UICONTROL Low-traffic] funziona al meglio con dimensioni che hanno elementi che si ripresentano più volte durante il mese. Se gli elementi dimensionali sono quasi o completamente univoci su ogni hit, il numero di valori univoci raggiunge rapidamente la soglia e tutti i valori successivi per il mese terminano nel bucket [!UICONTROL Low-Traffic].

## Come i valori immettono [!UICONTROL Low-Traffic]

Per impostazione predefinita, viene impostata una soglia di **2.000.000 valori univoci** per dimensione, per suite di rapporti, per mese di calendario. Gli elementi Dimension che superano questa soglia di valore univoco vengono inseriti nel bucket in [!UICONTROL Low-Traffic].

* Gli elementi Dimension raccolti prima del raggiungimento della soglia vengono calcolati normalmente.
* Gli elementi Dimension raccolti dopo il superamento della soglia sono inseriti nel bucket in [!UICONTROL Low-Traffic].

>[!NOTE]
>La dimensione [Pagina](../components/dimensions/page.md) utilizza diverse colonne di back-end che vengono conteggiate tutte ai fini della soglia univoca, inclusi `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url` e `click_context`. Queste colonne di back-end possono causare l&#39;applicazione della logica [!UICONTROL Low-Traffic] ben prima che il numero di elementi dimensionali di pagina univoci in Workspace raggiunga la soglia.

Il limite univoco di 2.000.000 di può essere modificato per ogni dimensione. Consulta [Modifica delle soglie dei limiti univoci](#changing-unique-limit-thresholds) di seguito. Al termine di un mese di calendario, il numero di valori univoci tracciati viene reimpostato a livello globale.

## Come i valori possono uscire da [!UICONTROL Low-Traffic] dopo aver superato la soglia

Se una determinata dimensione raccoglie oltre 2.000.000 valori univoci in un dato mese, i singoli elementi dimensionali possono tornare a segnalare il proprio elemento dimensionale. Il caso d’uso principale di questa funzione consiste nel consentire la segnalazione di elementi dimensionali fondamentali che potrebbero ricevere un aumento di popolarità nell’ultimo mese dopo il superamento della soglia univoca. Ad esempio, se la tua organizzazione gestisce un sito con milioni di articoli e un nuovo articolo diventa popolare verso la fine del mese, puoi ancora analizzare le prestazioni di tale articolo. Questa logica non ha lo scopo di rimuovere tutti gli elementi che ottengono un certo numero di istanze, ma offre piuttosto un modo per analizzare il contenuto che riceve un afflusso di traffico.

I requisiti per l&#39;escape di [!UICONTROL Low-Traffic] per un singolo elemento dimensione dipendono da molti fattori, molti dei quali impediscono di calcolare una soglia esatta:

* **Numero di server che elaborano dati per la suite di rapporti**: le suite di rapporti con più traffico richiedono più istanze di un singolo elemento dimensione per l&#39;escape di [!UICONTROL Low-Traffic].
* **Periodo di tempo tra ciascuna istanza dell&#39;elemento dimensione**: gli hit contenenti un elemento dimensione distribuiti nell&#39;arco della giornata richiedono più istanze di un picco di hit concentrato.
* **Numero di valori univoci per la dimensione**: per impostazione predefinita, ogni dimensione ha una seconda soglia impostata su 2.100.000 valori univoci. Se il numero di valori univoci in una dimensione supera questa soglia più alta, viene applicato un filtro molto più aggressivo.

Tenendo conto dei fattori di cui sopra, si prevede che **centinaia fino a migliaia** di istanze per un singolo elemento della dimensione possano uscire da [!UICONTROL Low-Traffic] se viene superata solo la prima soglia. Se viene superata la soglia più alta, è previsto che **migliaia, decine di migliaia** di istanze per un singolo elemento della dimensione possano uscire da [!UICONTROL Low-Traffic]. Adobe non garantisce che gli elementi dimensionali siano inclusi in modo affidabile nel bucket [!UICONTROL Low-Traffic]. Questo concetto è in genere riservato agli elementi dimensionali con volumi insolitamente elevati alla fine del mese.

Quando un elemento dimensione esce dal bucket [!UICONTROL Low-Traffic], le istanze raccolte prima dell&#39;afflusso di traffico rimangono in [!UICONTROL Low-Traffic].

## Modifica delle soglie limite univoche

I limiti di soglia possono a volte essere modificati per singole dimensioni. Contatta l’assistenza clienti di Adobe o il team Adobe account per richiedere questa modifica. La misura in cui le soglie possono essere aumentate dipende da più fattori; Adobe non garantisce che tutte le richieste di aumento delle soglie possano essere soddisfatte. Quando richiedi una modifica, includi:

* L’ID della suite di rapporti
* La dimensione per la quale desideri aumentare la soglia
* La prima e la seconda soglia erano entrambe desiderate:
   * La prima soglia (bucket iniziale) è impostata su **2.000.000** per impostazione predefinita.
   * La seconda soglia (filtro più aggressivo) è impostata su **2.100.000** per impostazione predefinita.

>[!IMPORTANT]
>
>Le modifiche alle soglie possono influire sulle prestazioni del rapporto. Adobe consiglia vivamente di dare prova di buon senso quando si richiede un aumento a valori univoci per una dimensione. Aumenta solo i limiti univoci per le dimensioni critiche per le esigenze di reporting della tua organizzazione.

[!UICONTROL Low-Traffic] soglie non sono visibili nell&#39;interfaccia utente di Analytics. Se desideri maggiori informazioni sulle soglie esistenti, contatta l’assistenza clienti di Adobe.

## Interazioni con altre funzionalità

Diverse funzionalità trattano i valori [!UICONTROL Low-Traffic] in modi diversi.

* **Data Warehouse:** Nella maggior parte dei casi non esiste alcun limite al numero di valori univoci nei report di Data Warehouse. La sua architettura univoca consente il reporting di qualsiasi numero di valori univoci. Tuttavia, i valori [!UICONTROL Low-Traffic] possono ancora essere visualizzati in alcuni scenari limitati. Alcuni esempi includono variabili elenco, prop elenco, eVar di merchandising e dimensioni di dettaglio del canale di marketing.
* **Segmentazione:** Se i criteri del segmento includono una dimensione con un numero elevato di valori univoci, i valori acquisiti in [!UICONTROL Low-Traffic] non sono inclusi.
* **Classificazioni:** anche i rapporti di classificazione sono soggetti a limiti univoci. Se l&#39;elemento dimensione padre di una classificazione è incluso in [!UICONTROL Low-Traffic], il valore non viene classificato.
   * I valori [!UICONTROL Low-Traffic] classificati tramite l&#39;importazione possono essere visualizzati in Data Warehouse. <!-- AN-115871 -->
   * [!UICONTROL Low-Traffic] valori classificati tramite il generatore di regole *non possono* essere visualizzati in Data Warehouse. <!-- AN-122872 -->
