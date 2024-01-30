---
description: Quando un rapporto ha molti valori univoci, Adobe utilizza l’elemento dimensione Traffico ridotto per migliorare le prestazioni del rapporto.
title: Valore a traffico ridotto in Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: d3a959d128f4740fd98ff40e5b92a3ea983d3c05
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 0%

---

# Valore a traffico ridotto in Adobe Analytics

Quando un rapporto ha molti valori univoci, Adobe fornisce funzionalità per garantire che vengano visualizzati i valori più importanti. I valori univoci delle variabili raccolti oltre una certa soglia (vedi sotto) sono elencati sotto un elemento dimensione etichettato **[!UICONTROL Low-Traffic]**.

## Come [!UICONTROL Low-Traffic] lavori

* Adobe Analytics utilizza due soglie per determinare quali valori univoci vengono visualizzati nei rapporti ogni mese: A **[!UICONTROL low threshold]** e un **[!UICONTROL high threshold]**. Tali soglie possono essere modificate di volta in volta per Adobe. Gli attuali limiti di soglia sono:
   * **[!UICONTROL Low threshold]**: >500.000 valori univoci durante il mese.
   * **[!UICONTROL High threshold]**: >1.000.000 valori univoci durante il mese.
* La generazione di rapporti non viene influenzata se la variabile non raggiunge la soglia bassa in un dato mese.
* Quando una variabile raggiunge la soglia bassa, i dati iniziano a essere inseriti nel bucket sotto [!UICONTROL Low-Traffic]. Ogni valore oltre questa soglia viene calcolato in base alla logica seguente:
   * Se un valore è già presente nei rapporti, aggiungilo normalmente.
   * Se un valore non è ancora visualizzato nei rapporti, inizialmente viene inserito nel bucket [!UICONTROL Low-Traffic] elemento dimensione.
   * Se un valore inserito nel bucket [!UICONTROL Low-Traffic] riceve un afflusso di traffico (in genere istanze nelle due cifre in un singolo giorno), inizia a essere riconosciuto come proprio elemento dimensionale. Le istanze raccolte prima del raggiungimento della soglia rimangono inferiori a [!UICONTROL Low-Traffic]. Il punto esatto in cui l’elemento dimensionale inizia a essere visualizzato nei rapporti ha molte dipendenze, ad esempio il numero di server che elaborano i dati per la suite di rapporti e il tempo tra ogni istanza dell’elemento dimensionale.
* Se una variabile raggiunge la soglia elevata, viene applicato un filtro più aggressivo. I valori univoci richiedono istanze nelle tre cifre in un singolo giorno prima di essere riconosciuti come un proprio elemento dimensione.

Questa logica consente ad Adobe di ottimizzare le funzionalità di reporting, consentendo al contempo all’organizzazione di creare rapporti su elementi dimensionali fondamentali raccolti più avanti nel mese. Ad esempio, se la tua organizzazione gestisce un sito con milioni di articoli e un nuovo articolo diventa popolare verso la fine del mese (dopo aver superato entrambe le soglie univoche), puoi comunque analizzare le prestazioni di tale articolo senza che sia incluso nel bucket [!UICONTROL Low-Traffic]. Questa logica non ha lo scopo di rimuovere tutto ciò che ottiene un certo numero di visualizzazioni di pagina al giorno o al mese.

>[!NOTE]
>Il [Pagina](../components/dimensions/page.md) La dimensione utilizza diverse colonne back-end che vengono conteggiate tutte ai fini del raggiungimento di soglie univoche, tra cui `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`, e `click_context`. Queste colonne di back-end possono causare [!UICONTROL Low-Traffic] logica da applicare molto prima che il numero di elementi dimensionali di pagina univoci in Workspace raggiunga la soglia bassa.

La logica di traffico ridotto descritta sopra funziona meglio con le variabili che hanno elementi dimensionali che si ripresentano più volte durante il mese. Se gli elementi dimensionali di una variabile sono quasi o completamente univoci su ogni hit, la variabile raggiungerà rapidamente la soglia bassa e tutti i nuovi elementi dimensionali per il mese finiranno nel bucket di traffico ridotto.

## Modifica delle soglie dei limiti univoci

I limiti di soglia possono a volte essere modificati per singole variabili. Contatta l’Assistenza clienti Adobe o il team del tuo account Adobe per richiedere questa modifica. La misura in cui le soglie possono essere aumentate dipende da diversi fattori e l&#39;Adobe potrebbe non essere in grado di tenere conto degli aumenti delle soglie in tutti i casi. Quando si richiede una modifica, includere:

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
