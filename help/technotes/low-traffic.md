---
description: Quando un rapporto ha molti valori univoci, Adobe utilizza l’elemento dimensione traffico ridotto per migliorare le prestazioni del rapporto.
title: Valore di traffico ridotto in Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# Valore di traffico ridotto in Adobe Analytics

Quando un rapporto ha molti valori univoci, Adobe fornisce funzionalità che garantiscono la visualizzazione dei valori più importanti nel rapporto. I valori delle variabili univoci raccolti dopo circa 500.000 valori esistenti sono elencati sotto un elemento dimensione etichettato **[!UICONTROL Low-Traffic]**.

## Come [!UICONTROL Low-Traffic] lavori

* La generazione di rapporti non viene influenzata se la variabile non raggiunge 500.000 valori univoci in un dato mese.
* Quando una variabile raggiunge 500.000 valori univoci, i dati iniziano a essere inseriti nei bucket in [!UICONTROL Low-Traffic]. Ogni valore oltre questa soglia passa attraverso la logica seguente:
   * Se un valore è già visualizzato nei rapporti, aggiungilo come di consueto.
   * Se un valore non è ancora visualizzato nei rapporti, viene inizialmente inserito nei [!UICONTROL Low-Traffic] elemento dimensione.
   * Se un valore inserito in [!UICONTROL Low-Traffic] riceve un afflusso di traffico (in genere istanze con due cifre in un singolo giorno), inizia a essere riconosciuto come elemento dimensionale proprio. Le istanze raccolte prima di raggiungere la soglia rimangono sotto [!UICONTROL Low-Traffic]. La soglia esatta include molte dipendenze, ad esempio il numero di server che elaborano i dati per la suite di rapporti e il tempo tra ogni istanza di elemento dimensione.
* Se una suite di rapporti raggiunge più di 1.000.000 valori univoci, viene applicato un filtro più aggressivo. I valori univoci richiedono le istanze con tre cifre in un singolo giorno prima di essere riconosciuti come elemento dimensione proprio.

Questa logica consente ad Adobe di ottimizzare le funzionalità di reporting, consentendo allo stesso tempo alla tua organizzazione di generare rapporti sugli elementi dimensionali cruciali raccolti più avanti nel mese. Ad esempio, la tua organizzazione esegue un sito con milioni di articoli e un nuovo articolo è diventato popolare verso la fine del mese (dopo aver superato entrambe le soglie univoche). Si potrebbe ancora analizzare le prestazioni di quell&#39;articolo senza che sia inserito in [!UICONTROL Low-Traffic]. Questa logica non prevede di rimuovere dal bucket tutto ciò che ottiene un certo numero di visualizzazioni di pagina al giorno o al mese.

>[!NOTE]
>La [Pagina](../components/dimensions/page.md) la dimensione utilizza diverse colonne di backend che vengono conteggiate in base a soglie univoche, tra cui `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`e `click_context`. Queste colonne di back-end possono causare [!UICONTROL Low-Traffic] da applicare molto prima che il numero di elementi dimensionali pagina univoci in Workspace raggiunga 500.000.

## Modifica delle soglie dei limiti univoci

I limiti di soglia sono 500.000 e 1 milione di valori univoci per impostazione predefinita. Questi limiti possono essere modificati per ogni variabile. Per richiedere questa modifica, contatta l’Assistenza clienti Adobe o il team dell’account Adobe. Quando richiedi una modifica, includi:

* ID suite di rapporti
* Variabile per la quale desideri aumentare la soglia
* Desiderate la prima e la seconda soglia

Le modifiche alle soglie possono influire sulle prestazioni dei rapporti. L&#39;Adobe consiglia vivamente di utilizzare il buon senso quando si richiede un aumento di valori univoci in una variabile. Aumenta solo i limiti univoci per le variabili che sono fondamentali per le esigenze di reporting della tua organizzazione.

Le soglie a traffico ridotto non sono visibili nell’interfaccia utente di Analytics. Per ulteriori informazioni sulle soglie esistenti, contatta l’Assistenza clienti di Adobe.

## Traffico ridotto utilizzando componenti e altre funzionalità

Funzionalità diverse trattano i valori a traffico ridotto in modi diversi.

* **Data Warehouse:** Non esiste alcun limite al numero di valori univoci nei rapporti sulle Date Warehouse. La sua architettura unica consente di riportare qualsiasi numero di valori univoci.
   * In alcuni scenari limitati, possono ancora apparire valori di traffico bassi. Gli esempi includono variabili elenco, proprietà elenco, eVar per merchandising e dimensioni di dettaglio del canale di marketing.
* **Segmentazione:** Se i criteri del segmento includono una variabile con un numero elevato di valori univoci, i valori acquisiti con traffico limitato non vengono inclusi.
* **Classificazioni:** Anche i rapporti di classificazione sono soggetti a limiti unici. Se il valore della variabile padre di una classificazione è incluso in traffico limitato, il valore non viene classificato.
   * I valori di classificazione a traffico ridotto ottenuti tramite l’importazione possono essere visualizzati in Data Warehouse. <!-- AN-115871 -->
   * Valori di classificazione a traffico ridotto ottenuti tramite il generatore di regole *impossibile* da visualizzare nella Data Warehouse. <!-- AN-122872 -->
