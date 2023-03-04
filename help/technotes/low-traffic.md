---
description: Quando un rapporto ha molti valori univoci, Adobe utilizza l’elemento dimensione Traffico ridotto per migliorare le prestazioni del rapporto.
title: Valore a traffico ridotto in Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# Valore a traffico ridotto in Adobe Analytics

Quando un rapporto ha molti valori univoci, Adobe fornisce funzionalità per garantire che vengano visualizzati i valori più importanti. I valori di variabile univoci raccolti dopo circa 500.000 valori esistenti sono elencati in un elemento dimensione etichettato **[!UICONTROL Low-Traffic]**.

## Come [!UICONTROL Low-Traffic] lavori

* Il reporting non viene influenzato se la variabile non raggiunge 500.000 valori univoci in un dato mese.
* Quando una variabile raggiunge 500.000 valori univoci, i dati iniziano ad essere inseriti nel bucket sotto [!UICONTROL Low-Traffic]. Ogni valore oltre questa soglia viene calcolato in base alla logica seguente:
   * Se un valore è già presente nei rapporti, aggiungilo normalmente.
   * Se un valore non è ancora visualizzato nei rapporti, inizialmente viene inserito nel bucket [!UICONTROL Low-Traffic] elemento dimensione.
   * Se un valore inserito nel bucket [!UICONTROL Low-Traffic] riceve un afflusso di traffico (in genere istanze nelle due cifre in un singolo giorno), inizia a essere riconosciuto come proprio elemento dimensionale. Le istanze raccolte prima del raggiungimento della soglia rimangono inferiori a [!UICONTROL Low-Traffic]. La soglia esatta ha molte dipendenze, ad esempio il numero di server che elaborano i dati per la suite di rapporti e il tempo tra ogni istanza dell’elemento dimensionale.
* Se una suite di rapporti raggiunge più di 1.000.000 di valori univoci, viene applicato un filtro più aggressivo. I valori univoci richiedono istanze nelle tre cifre in un singolo giorno prima di essere riconosciuti come un proprio elemento dimensione.

Questa logica consente ad Adobe di ottimizzare le funzionalità di reporting, consentendo al contempo all’organizzazione di creare rapporti su elementi dimensionali fondamentali raccolti più avanti nel mese. Ad esempio, la tua organizzazione gestisce un sito con milioni di articoli e un nuovo articolo è diventato popolare verso la fine del mese (dopo aver superato entrambe le soglie univoche). Puoi comunque analizzare le prestazioni di quell’articolo senza che venga inserito nel bucket [!UICONTROL Low-Traffic]. Questa logica non ha lo scopo di rimuovere tutto ciò che ottiene un certo numero di visualizzazioni di pagina al giorno o al mese.

>[!NOTE]
>Il [Pagina](../components/dimensions/page.md) La dimensione utilizza diverse colonne back-end che vengono conteggiate tutte ai fini del raggiungimento di soglie univoche, tra cui `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`, e `click_context`. Queste colonne di back-end possono causare [!UICONTROL Low-Traffic] da applicare molto prima che il numero di elementi dimensionali di pagina univoci in Workspace raggiunga 500.000.

## Modifica delle soglie dei limiti univoci

Per impostazione predefinita, i limiti di soglia sono di 500.000 e 1 milione di valori univoci. Questi limiti possono essere modificati per singole variabili. Contatta l’Assistenza clienti Adobe o il team del tuo account Adobe per richiedere questa modifica. Quando si richiede una modifica, includere:

* ID suite di rapporti
* La variabile per la quale desideri aumentare la soglia
* Sia la prima che la seconda soglia desiderate

Le modifiche alle soglie possono influire sulle prestazioni dei rapporti. L’Adobe consiglia vivamente di dare prova di buon senso quando richiede un aumento a valori univoci in una variabile. Aumenta solo i limiti univoci per le variabili critiche per le esigenze di reporting della tua organizzazione.

Le soglie di traffico ridotto non sono visibili nell’interfaccia utente di Analytics. Per ulteriori informazioni sulle soglie esistenti, contatta l’Assistenza clienti Adobe.

## Traffico ridotto utilizzando componenti e altre funzionalità

Diverse funzionalità trattano i valori di traffico ridotto in modi diversi.

* **Data Warehouse:** Non esiste alcun limite al numero di valori univoci nei rapporti di Data Warehouse. La sua architettura univoca consente il reporting di qualsiasi numero di valori univoci.
   * In alcuni scenari limitati, possono ancora apparire valori di traffico ridotto. Alcuni esempi includono variabili elenco, prop elenco, eVar di merchandising e dimensioni di dettaglio del canale di marketing.
* **Segmentazione:** Se i criteri del segmento includono una variabile con un numero elevato di valori univoci, i valori acquisiti in condizioni di traffico ridotto non vengono inclusi.
* **Classificazioni:** Anche i rapporti di classificazione sono soggetti a limiti univoci. Se il valore della variabile padre di una classificazione è incluso in traffico ridotto, il valore non viene classificato.
   * I valori di classificazione a traffico ridotto ottenuti tramite l’importazione possono essere visualizzati in Data Warehouse. <!-- AN-115871 -->
   * Valori di classificazione a traffico ridotto ottenuti tramite il generatore di regole *non può* essere visualizzato nella Data Warehouse. <!-- AN-122872 -->
