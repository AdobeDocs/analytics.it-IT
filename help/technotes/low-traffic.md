---
description: Quando un rapporto ha un numero elevato di valori univoci, Adobe fornisce funzionalità che garantiscono la visualizzazione dei valori più importanti nel rapporto.
title: Valore di traffico ridotto in Adobe Analytics
feature: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---

# Valore di traffico ridotto in Adobe Analytics

Quando un rapporto ha un numero elevato di valori univoci, Adobe fornisce funzionalità che garantiscono la visualizzazione dei valori più importanti nel rapporto. I valori di variabili univoche raccolti dopo circa 500.000 valori esistenti sono elencati sotto una voce denominata **(Basso traffico)**.

## Funzionamento a traffico ridotto

* La generazione di rapporti non viene influenzata se la variabile non raggiunge 500.000 valori univoci in un dato mese.
* Quando una variabile raggiunge la prima soglia di 500.000, i dati iniziano a essere inseriti nei bucket con traffico limitato. Ogni valore oltre questa soglia passa attraverso la logica seguente:
   * Se un valore è già presente nei rapporti, aggiungilo come di consueto.
   * Se un valore non è ancora nel rapporto, controlla se al momento è stato visualizzato più di dieci volte. In caso affermativo, aggiungi questo valore al reporting. Se non è stato conteggiato più di dieci volte, lascialo sotto traffico ridotto.
* Se una suite di rapporti raggiunge più di 1.000.000 valori univoci, viene applicato un filtro più aggressivo:
   * Se un valore è già presente nei rapporti, aggiungilo come di consueto.
   * Se un valore non è ancora nel rapporto, controlla se al momento è stato visualizzato più di 100 volte circa. In caso affermativo, aggiungi il valore al reporting. Se non l&#39;ha fatto, lasciala sotto traffico ridotto.

>[!NOTE]
>
>Se un valore di variabile riceve abbastanza traffico per lasciare l’intervallo di traffico basso, i primi valori raccolti non si spostano alla rispettiva voce di riga. Le prime 10-100 istanze rimangono sotto traffico ridotto.

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
