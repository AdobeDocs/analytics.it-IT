---
description: Quando un rapporto ha un numero elevato di valori univoci, Adobe fornisce funzionalità che garantiscono la visualizzazione dei valori più importanti nel rapporto.
title: Valore di traffico ridotto in Adobe Analytics
feature: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 7036c6d3bc15c2cb7bd62af79229052cd772f8f8
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---

# Valore di traffico ridotto in Adobe Analytics

Quando un rapporto ha molti valori univoci, Adobe fornisce funzionalità che garantiscono la visualizzazione dei valori più importanti nel rapporto. I valori di variabili univoche raccolti dopo circa 500.000 valori esistenti sono elencati sotto una voce denominata **[!UICONTROL Low-Traffic]**.

## Come funziona [!UICONTROL Low-Traffic]

* La generazione di rapporti non viene influenzata se la variabile non raggiunge 500.000 valori univoci in un dato mese.
* Quando una variabile raggiunge la prima soglia di 500.000, i dati iniziano a essere inseriti nei bucket con traffico limitato. Ogni valore oltre questa soglia passa attraverso la logica seguente:
   * Se un valore è già visualizzato nei rapporti, aggiungilo come di consueto.
   * Se un valore non è ancora visualizzato nei rapporti, verrà visualizzato nella riga [!UICONTROL Low-Traffic]. Se un valore incluso nella riga [!UICONTROL Low-Traffic] viene visualizzato un numero significativo di volte in un breve periodo di tempo, verrà riconosciuto come elemento della riga corrispondente. Il numero significativo di volte in cui un elemento deve essere visualizzato ha molte dipendenze, ad esempio il numero di server di elaborazione e di demoni che elaborano i dati per quella particolare suite di rapporti.
* Se una suite di rapporti raggiunge più di 1.000.000 valori univoci, viene applicato un filtro più aggressivo:
   * Se un valore è già visualizzato nei rapporti, aggiungilo come di consueto.
   * Se un valore non è ancora visualizzato nei rapporti, verrà visualizzato nella riga [!UICONTROL Low-Traffic]. Se un valore incluso nella riga [!UICONTROL Low-Traffic] viene visualizzato un numero significativo di volte in un breve periodo di tempo, verrà riconosciuto come elemento della riga corrispondente. Il numero significativo di volte in cui un elemento deve essere visualizzato ha molte dipendenze, ad esempio il numero di server di elaborazione e di demoni che elaborano i dati per quella particolare suite di rapporti.

Perché Adobe sposta un elemento dalla riga [!UICONTROL Low Traffic] alla riga corrispondente? Ad esempio, questo spostamento potrebbe riconoscere una nuova pagina o un nuovo elemento popolare aggiunto più avanti nel mese (dopo il superamento di univoci) e che ottiene un sacco di hit/visualizzazioni. Lo spostamento non ha lo scopo di rilevare tutto ciò che riceve un certo numero di hit/visualizzazioni al giorno o al mese.

>[!NOTE]
>Il conteggio di ricerca della pagina non include solo i valori per [!UICONTROL pagename]/[!UICONTROL page_url]. La tabella di ricerca delle pagine include diverse colonne/campi quali [!UICONTROL pagename], [!UICONTROL first_hit_pagename]/[!UICONTROL page_url], [!UICONTROL visit_pagename]/[!UICONTROL page_url] e il contesto di clic (i vecchi dati di ClickMap).

## Modifica delle soglie dei limiti univoci

I limiti di soglia sono 500.000 e 1 milione di valori univoci per impostazione predefinita. Questi limiti possono essere modificati per ogni variabile. Per richiedere questa modifica, contatta l’account manager della tua organizzazione. Quando richiedi una modifica, includi:

* ID suite di rapporti
* Variabile per la quale desideri aumentare la soglia
* Desiderate la prima e la seconda soglia

Le modifiche alle soglie possono influire sulle prestazioni dei rapporti. L&#39;Adobe consiglia vivamente di utilizzare il buon senso quando si richiede un aumento di valori univoci in una variabile.

Le soglie a traffico ridotto non sono visibili nell’interfaccia utente di Analytics. Se desideri ulteriori informazioni sulle soglie esistenti, chiedi a un utente supportato della tua organizzazione di contattare l’Assistenza clienti Adobe.

## Traffico ridotto utilizzando componenti e altre funzionalità

Funzionalità diverse trattano i valori a traffico ridotto in modi diversi.

* **Data Warehouse:** non esiste alcun limite al numero di valori univoci nei rapporti Data Warehouse. La sua architettura unica consente di riportare qualsiasi numero di valori univoci.
   * In alcuni scenari limitati, possono ancora apparire valori di traffico bassi. Gli esempi includono variabili elenco, proprietà elenco, eVar per merchandising e dimensioni di dettaglio del canale di marketing.
* **Segmentazione:** se i criteri del segmento includono una variabile con un numero elevato di valori univoci, i valori acquisiti con traffico limitato non vengono inclusi.
* **Classificazioni:** anche i rapporti di classificazione sono soggetti a limiti univoci. Se il valore della variabile padre di una classificazione è incluso in traffico limitato, il valore non viene classificato.
   * I valori di classificazione a traffico ridotto ottenuti tramite l’importazione possono essere visualizzati in Data Warehouse. <!-- AN-115871 -->
   * I valori di classificazione con traffico ridotto ottenuti tramite il generatore di regole *non possono essere visualizzati in Data Warehouse. <!-- AN-122872 -->*
