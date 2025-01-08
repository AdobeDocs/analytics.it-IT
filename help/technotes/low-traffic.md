---
description: Quando un report contiene molti valori univoci, Adobe utilizza l’elemento dimensione Traffico ridotto per migliorarne le prestazioni.
title: Valore Traffico ridotto in Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: f242ec6613cf046224f76f7edc7813a34c65fff8
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 77%

---

# Valore Traffico ridotto in Adobe Analytics

Quando un report contiene molti valori univoci, Adobe fornisce funzionalità per garantire che i valori più importanti vengano visualizzati nel report. I valori delle variabili univoche raccolti oltre una determinata soglia (vedi di seguito) sono elencati in un elemento dimensione etichettato **[!UICONTROL Low-Traffic]**.

## Come funziona [!UICONTROL Low-Traffic]

* Adobe Analytics utilizza due soglie per determinare quali valori univoci vengono visualizzati nei report ogni mese: una **[!UICONTROL low threshold]** e una **[!UICONTROL high threshold]**. Tali soglie possono essere modificate di volta in volta per Adobe. Gli attuali limiti di soglia sono:
   * **[!UICONTROL Low threshold]**: 2.000.000 valori univoci durante il mese.
   * **[!UICONTROL High threshold]**: 2.100.000 valori univoci durante il mese.
* Il reporting non viene influenzato se una variabile non raggiunge la soglia bassa in un dato mese.
* Quando una variabile raggiunge la soglia bassa, i dati iniziano a essere inseriti in un bucket sotto un elemento dimensione etichettato [!UICONTROL Low-Traffic]. Ogni valore oltre questa soglia segue la seguente logica:
   * Se un valore è già presente nei report, aggiungilo come faresti di normalmente.
   * Se un valore non è ancora visualizzato nei rapporti, aggiungerlo inizialmente all&#39;elemento dimensione [!UICONTROL Low-Traffic].
   * Se un valore inserito nel bucket in [!UICONTROL Low-Traffic] riceve un afflusso di traffico (in genere le istanze a due cifre in un singolo giorno), riconoscerlo come proprio elemento dimensione. Le istanze raccolte prima dell&#39;afflusso di traffico rimangono in [!UICONTROL Low-Traffic]. Il punto esatto in cui l’elemento dimensione inizia ad apparire nei report possiede molte dipendenze, ad esempio il numero di server che elaborano i dati per la suite di report e la quantità di tempo che intercorre tra ciascuna istanza dell’elemento dimensione.
* Se una variabile raggiunge la soglia alta, viene applicato un filtro più aggressivo. I valori univoci richiedono istanze a tre cifre in un solo giorno prima di essere riconosciuti come elemento dimensione proprio.

Questa logica consente ad Adobe di ottimizzare le funzionalità di generazione rapporti consentendo comunque alla tua organizzazione di riportare elementi dimensione cruciali raccolti più avanti nel corso del mese. Ad esempio, se la tua organizzazione gestisce un sito con milioni di articoli e un nuovo articolo diventa popolare verso la fine del mese (dopo aver superato entrambe le soglie univoche), puoi comunque analizzare la prestazione di quell’articolo senza che venga inserito nel bucket [!UICONTROL Low-Traffic]. Questa logica non ha lo scopo di eliminare dal bucket tutto ciò che ottiene un certo numero di visualizzazioni di pagina al giorno o al mese.

>[!NOTE]
>La dimensione [Pagina](../components/dimensions/page.md) utilizza diverse colonne di back-end che vengono tutte conteggiate ai fini delle soglie univoche, incluse `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url` e `click_context`. Queste colonne di back-end possono causare un [!UICONTROL Low-Traffic] logico da applicare molto prima che il numero di elementi dimensione Pagina univoci in Workspace raggiunga la soglia minima.

La logica di traffico ridotto funziona al meglio con le variabili che hanno elementi dimensionali che si ripresentano più volte durante il mese. Se gli elementi dimensionali di una variabile sono quasi o completamente univoci su ogni hit, il numero di valori univoci della variabile raggiunge rapidamente entrambe le soglie e tutti gli elementi dimensionali successivi per il mese terminano nel bucket di traffico ridotto.

## Modifica delle soglie limite univoche

I limiti di soglia a volte possono essere modificati in base alla variabile. Contatta l’assistenza clienti di Adobe o il team Adobe account per richiedere questa modifica. La misura in cui è possibile aumentare le soglie dipende da molteplici fattori e Adobe potrebbe non essere in grado di consentire aumenti delle soglie in tutti i casi. Quando richiedi una modifica, includi:

* L’ID della suite di rapporti
* La variabile per la quale desideri aumentare la soglia
* Sia la prima che la seconda soglia desiderate

Le modifiche alle soglie possono influire sulle prestazioni del rapporto. Adobe consiglia vivamente di usare il buon senso quando si richiede un aumento di valori univoci in una variabile. Aumenta i limiti univoci solo per le variabili fondamentali per le esigenze di reportistica della tua organizzazione.

Le soglie di traffico ridotto non sono visibili nell’interfaccia utente di Analytics. Se desideri maggiori informazioni sulle soglie esistenti, contatta l’assistenza clienti di Adobe.

## Traffico ridotto che utilizza componenti e altre funzionalità

Funzionalità diverse trattano i valori a traffico ridotto in modi diverso.

* **Data warehouse:** non esiste alcun limite al numero di valori univoci nei rapporti del data warehouse. La sua architettura univoca consente il reporting di un numero qualsiasi di valori univoci.
   * In alcuni scenari limitati, possono ancora essere visualizzati valori di traffico ridotto. Gli esempi includono variabili elenco, prop elenco, eVar di merchandising e dimensioni di dettaglio del canale di marketing.
* **Segmentazione:** se i criteri del segmento includono una variabile con un numero elevato di valori univoci, i valori acquisiti in condizioni di traffico ridotto non vengono inclusi.
* **Classificazioni:** anche i rapporti di classificazione sono soggetti a limiti univoci. Se il valore della variabile principale di una classificazione è incluso in quello del traffico ridotto, il valore non viene classificato.
   * I valori di classificazione del traffico ridotto ottenuti tramite l’importatore possono essere visualizzati nel Data Warehouse.<!-- AN-115871 -->
   * I valori di classificazione del traffico ridotto ottenuti tramite il generatore di regole *non possono* essere visualizzati nel Data Warehouse.<!-- AN-122872 -->
