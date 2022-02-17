---
description: Quando un rapporto ha un numero elevato di valori univoci, Adobe fornisce funzionalità che garantiscono la visualizzazione dei valori più importanti nel rapporto.
title: Valore di traffico ridotto in Adobe Analytics
feature: Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---

# Valore di traffico ridotto in Adobe Analytics

Quando un rapporto ha molti valori univoci, Adobe fornisce funzionalità che garantiscono la visualizzazione dei valori più importanti nel rapporto. I valori delle variabili univoche raccolti dopo circa 500.000 valori esistenti sono elencati sotto una voce con titolo **[!UICONTROL Low-Traffic]**.

## Come [!UICONTROL Low-Traffic] lavori

* La generazione di rapporti non viene influenzata se la variabile non raggiunge 500.000 valori univoci in un dato mese.
* Quando una variabile raggiunge la prima soglia di 500.000, i dati iniziano a essere inseriti nei bucket con traffico limitato. Ogni valore oltre questa soglia passa attraverso la logica seguente:
   * Se un valore è già visualizzato nei rapporti, aggiungilo come di consueto.
   * Se un valore non è ancora visualizzato nei rapporti, verrà visualizzato nella [!UICONTROL Low-Traffic] riga. Se un valore è stato incluso nel [!UICONTROL Low-Traffic] l’elemento di riga viene visualizzato un numero significativo di volte in un breve periodo di tempo, inizierà a essere riconosciuto come elemento di riga proprio. Il numero significativo di volte in cui un elemento deve essere visualizzato ha molte dipendenze, ad esempio il numero di server di elaborazione e di demoni che elaborano i dati per quella particolare suite di rapporti.
* Se una suite di rapporti raggiunge più di 1.000.000 valori univoci, viene applicato un filtro più aggressivo:
   * Se un valore è già visualizzato nei rapporti, aggiungilo come di consueto.
   * Se un valore non è ancora visualizzato nei rapporti, verrà visualizzato nella [!UICONTROL Low-Traffic] riga. Se un valore è stato incluso nel [!UICONTROL Low-Traffic] l’elemento di riga viene visualizzato un numero significativo di volte in un breve periodo di tempo, inizierà a essere riconosciuto come elemento di riga proprio. Il numero significativo di volte in cui un elemento deve essere visualizzato ha molte dipendenze, ad esempio il numero di server di elaborazione e di demoni che elaborano i dati per quella particolare suite di rapporti.

Perché Adobe sposta un elemento dal [!UICONTROL Low Traffic] riga al proprio elemento riga? Ad esempio, questo spostamento potrebbe riconoscere una nuova pagina o un nuovo elemento popolare aggiunto più avanti nel mese (dopo il superamento di univoci) e che ottiene un sacco di hit/visualizzazioni. Lo spostamento non ha lo scopo di rilevare tutto ciò che riceve un certo numero di hit/visualizzazioni al giorno o al mese.

>[!NOTE]
>Il conteggio di ricerca della pagina non include solo i valori per [!UICONTROL pagename]/[!UICONTROL page_url]. La tabella di ricerca delle pagine include diverse colonne/campi, ad esempio [!UICONTROL pagename], [!UICONTROL first_hit_pagename]/[!UICONTROL page_url], [!UICONTROL visit_pagename]/[!UICONTROL page_url], e il contesto di clic (i vecchi dati di ClickMap).

## Modifica delle soglie dei limiti univoci

I limiti di soglia sono 500.000 e 1 milione di valori univoci per impostazione predefinita. Questi limiti possono essere modificati per ogni variabile. Per richiedere questa modifica, contatta l’account manager della tua organizzazione. Quando richiedi una modifica, includi:

* ID suite di rapporti
* Variabile per la quale desideri aumentare la soglia
* Desiderate la prima e la seconda soglia

Le modifiche alle soglie possono influire sulle prestazioni dei rapporti. L&#39;Adobe consiglia vivamente di utilizzare il buon senso quando si richiede un aumento di valori univoci in una variabile.

Le soglie a traffico ridotto non sono visibili nell’interfaccia utente di Analytics. Se desideri ulteriori informazioni sulle soglie esistenti, chiedi a un utente supportato della tua organizzazione di contattare l’Assistenza clienti Adobe.

## Traffico ridotto utilizzando componenti e altre funzionalità

Funzionalità diverse trattano i valori a traffico ridotto in modi diversi.

* **Data Warehouse:** Non esiste alcun limite al numero di valori univoci nei rapporti sulle Date Warehouse. La sua architettura unica consente di riportare qualsiasi numero di valori univoci.
   * In alcuni scenari limitati, possono ancora apparire valori di traffico bassi. Gli esempi includono variabili elenco, proprietà elenco, eVar per merchandising e dimensioni di dettaglio del canale di marketing.
* **Segmentazione:** Se i criteri del segmento includono una variabile con un numero elevato di valori univoci, i valori acquisiti con traffico limitato non vengono inclusi.
* **Classificazioni:** Anche i rapporti di classificazione sono soggetti a limiti unici. Se il valore della variabile padre di una classificazione è incluso in traffico limitato, il valore non viene classificato.
   * I valori di classificazione a traffico ridotto ottenuti tramite l’importazione possono essere visualizzati in Data Warehouse. <!-- AN-115871 -->
   * Valori di classificazione a traffico ridotto ottenuti tramite il generatore di regole *impossibile* da visualizzare nella Data Warehouse. <!-- AN-122872 -->
