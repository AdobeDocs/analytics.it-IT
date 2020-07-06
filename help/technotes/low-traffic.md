---
description: Quando un rapporto ha un numero elevato di valori univoci, Adobe fornisce funzionalità per garantire che i valori più importanti vengano visualizzati nel rapporto.
title: Valore di traffico basso in Adobe  Analytics
topic: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---


# Valore di traffico basso in Adobe  Analytics

Quando un rapporto ha un numero elevato di valori univoci, Adobe fornisce funzionalità per garantire che i valori più importanti vengano visualizzati nel rapporto. I valori delle variabili univoche raccolti dopo circa 500.000 valori esistenti sono elencati in un elemento di riga denominato **(Basso traffico)**.

## Funzionamento del traffico limitato

* I rapporti non vengono influenzati se la variabile non raggiunge 500.000 valori univoci in un dato mese.
* Quando una variabile raggiunge la prima soglia di 500.000, i dati iniziano ad essere inseriti nei pacchetti con traffico limitato. Ogni valore oltre questa soglia passa attraverso la logica seguente:
   * Se un valore è già presente nei rapporti, aggiungetelo normalmente.
   * Se un valore non è ancora nel reporting, verificare se tale valore è stato visualizzato più di dieci volte al giorno d&#39;oggi. In caso affermativo, aggiungete questo valore al reporting. Se non è stato conteggiato più di dieci volte, lasciatelo sotto traffico limitato.
* Se una suite di rapporti raggiunge più di 1.000.000 valori univoci, viene applicato un filtro più aggressivo:
   * Se un valore è già presente nei rapporti, aggiungetelo normalmente.
   * Se un valore non è ancora nel reporting, verificare che sia stato visualizzato più di 100 volte al giorno d&#39;oggi. In caso affermativo, aggiungete il valore al reporting. In caso contrario, lasciatela sotto il traffico limitato.

>[!NOTE]
>
>Se un valore di variabile riceve un traffico sufficiente per lasciare il periodo fisso di traffico basso, i primi valori raccolti non si spostano sul relativo elemento di riga. Quelle prime 10-100 istanze rimangono sotto il traffico basso.

## Modifica di soglie univoche

Per impostazione predefinita, i limiti di soglia sono 500.000 e 1 milione di valori univoci. Tali limiti possono essere modificati per ogni variabile. Per richiedere la modifica, contatta l’account manager della tua organizzazione. Quando viene richiesta una modifica, includi:

* ID suite di rapporti
* La variabile per la quale si desidera aumentare la soglia
* Sia la prima che la seconda soglia desiderata

Le modifiche alle soglie possono influire sulle prestazioni del report. Adobe consiglia vivamente di utilizzare il buon senso quando si richiede un aumento di valori univoci in una variabile.

Le soglie di traffico basso non sono visibili nell&#39;interfaccia  di Analytics. Se desiderate ulteriori informazioni sulle soglie esistenti, rivolgetevi a un utente supportato della vostra azienda.

## Basso traffico con componenti e altre funzionalità

Diverse funzionalità gestiscono i valori di traffico ridotto in modi diversi.

* **Data warehouse:** Non esiste alcun limite al numero di valori univoci nei rapporti sulle Date warehouse. La sua architettura unica permette di riportare qualsiasi numero di valori univoci.
   * In alcuni scenari limitati, i valori di traffico ridotti possono ancora essere visualizzati. Alcuni esempi includono le variabili elenco, le proprietà elenco, le eVar merchandising e le dimensioni dei dettagli del canale di marketing.
* **Segmentazione:** Se i criteri del segmento includono una variabile con un numero elevato di valori univoci, i valori acquisiti con traffico limitato non vengono inclusi.
* **Classificazioni:** Anche i rapporti sulla classificazione sono soggetti a limiti univoci. Se il valore della variabile padre di una classificazione è incluso in traffico limitato, il valore non è classificato.
   * Se si classificano i valori prima che vengano visualizzati nei dati, tali valori vengono conteggiati verso la soglia univoca per quel mese.
