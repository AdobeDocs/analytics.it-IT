---
description: Il pannello Analytics for Target (A4T) ti consente di analizzare le attività e le esperienze Adobe Target in Analysis Workspace.
title: Pannello Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 3d9bfabba6752f85173814c0e18d485122f7aa76
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 87%

---


# Pannello Analytics for Target (A4T)

Il pannello Analytics for Target (A4T) ti consente di analizzare le attività e le esperienze Adobe Target in Analysis Workspace. Ti consente inoltre di visualizzare l’incremento e l’affidabilità per un massimo di 3 metriche di successo. Per accedere al pannello A4T, accedi a una suite di rapporti con i componenti A4T abilitati. Fai clic sull’icona del pannello all’estrema sinistra, quindi trascina il pannello Analytics for Target nel progetto Analysis Workspace.

## Input del pannello {#Input}

Puoi configurare il pannello A4T usando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| Target Attività | Seleziona da un elenco di attività di Target oppure trascina e rilascia un’attività dalla barra a sinistra.<br>**Nota:** l’elenco è composto dagli ultimi 6 mesi di attività che hanno avuto almeno 1 hit. Se nell’elenco non viene visualizzata un’attività, potrebbe essere più vecchia di 6 mesi. Può essere comunque aggiunta dalla barra a sinistra, che ha un periodo di lookback fino a 18 mesi. |
| Control Experience | Seleziona la tua esperienza di controllo. Se necessario, puoi modificarla nel menu a discesa. |
| Normalizing metric | Scegli tra Unique Visitors, Visits, o Activity Impressions. L’opzione Unique visitors è consigliata per la maggior parte dei casi di utilizzo dell’analisi. Questa metrica (detta anche metodologia di conteggio) diventa il denominatore del calcolo dell’incremento. Inoltre, influisce sul modo in cui i dati vengono aggregati prima dell’applicazione del calcolo del valore di affidabilità. |
| Success metrics | Seleziona fino a 3 eventi di successo standard (non calcolati) dai menu a discesa, oppure trascina e rilascia le metriche dalla barra a sinistra. Ogni metrica avrà una tabella e una visualizzazione dedicate nel pannello di cui è stato effettuato il rendering. |
| Intervallo date del calendario | Questo verrà compilato automaticamente in base all’intervallo di date dell’attività di Adobe Target. Puoi cambiarlo se necessario. |

![Generatore di pannelli](assets/a4t-panel-builder2.png)

## Output del pannello {#Output}

Il pannello Analytics for Target restituisce un set completo di dati e visualizzazioni per consentirti di comprendere meglio le prestazioni dell’attività e delle esperienze Adobe Target. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate. In qualsiasi momento, puoi modificare il pannello facendo clic sulla matita di modifica in alto a destra.

Per ogni metrica di successo selezionata, verrà visualizzata una tabella a forma libera e una tendenza del tasso di conversione:

![Rendering](assets/a4t-rendered.png)


Ogni tabella a forma libera mostra le seguenti colonne di metriche:

| Metrica | Descrizione |
|---|---|
| Normalizing metrics | Visitatori, visite o impressioni di attività univoche. |
| Success metric | La metrica selezionata nel generatore |
| Conversion rate | Metrica di successo/Metrica di Normalizzazione |
| Incremento | Confronta il tasso di conversione per ogni esperienza rispetto all’esperienza di controllo.<br>**Nota:** Lift è una &quot;metrica bloccata&quot; per le esperienze Target; non può essere suddiviso o utilizzato con altre dimensioni. |
| Lift (Lower) | Rappresenta l’incremento peggiore che un’esperienza diversa potrebbe avere sul controllo. |
| Lift (Mid) | Rappresenta l’incremento intermedio che un’esperienza diversa potrebbe avere sul controllo con un intervallo di affidabilità del 95%. Corrisponde a “Lift” in Reports &amp; Analytics. |
| Lift (Upper) | Rappresenta l’incremento migliore che un’esperienza diversa potrebbe avere sul controllo. |
| Confidence | Il test t di Student calcola il livello di affidabilità, che indica la probabilità che i risultati vengano duplicati se il test viene eseguito di nuovo. Alla metrica è stato applicato un intervallo di formattazione condizionale fisso del 75%/85%/95%. Questa formattazione può essere personalizzata, se necessario, in Column settings. <br>**Nota:** Confidence è una &quot;metrica bloccata&quot; per le esperienze Target; non può essere suddiviso o utilizzato con altre dimensioni. |

Come per qualsiasi pannello in Analysis Workspace, puoi continuare la tua analisi aggiungendo ulteriori tabelle e [visualizzazioni](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) che ti aiuteranno ad analizzare le tue attività Adobe Target.

## Domande frequenti {#FAQ}

| Domanda | Risposta |
|---|---|
| Quali tipi di attività sono supportati in A4T? | [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html) sui tipi di attività supportati. |
| Le metriche calcolate sono supportate nei calcoli di incremento e affidabilità? | No. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) sui motivi per cui le metriche calcolate non sono supportate in incremento e affidabilità. Le metriche calcolate possono tuttavia essere utilizzate nel reporting A4T al di fuori di queste metriche. |
| Perché i visitatori unici dovrebbero variare tra Target e Analytics? | [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) sulle discrepanze di visitatori unici tra i prodotti. |
| Quando applico un segmento di hit per una specifica attività Target nell’analisi, perché viene restituita un’esperienza non correlata? | La dimensione A4T è una variabile di elenco, il che significa che può contenere più attività (ed esperienze) alla volta. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) |
| La metrica di affidabilità tiene conto di ordini estremi o applica una correzione Bonferroni per offerte multiple? | No. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) su come Analytics calcola l’affidabilità. |
| È possibile utilizzare metriche di incremento e confidenza con altre dimensioni o suddivisioni? | Lift e confidence sono &quot;metriche bloccate&quot; per la dimensione Esperienze di Target perché richiedono un controllo e una variante da calcolare in tutta l&#39;area. In quanto tali, non possono essere suddivisi o utilizzati con altre dimensioni. |
| Quando vengono ricalcolati incrementi e affidabilità? | L’incremento e la confidenza vengono ricalcolati ogni volta che il pannello viene eseguito (o rieseguito), che l’intervallo di date del pannello viene modificato o che un segmento viene applicato al pannello o alla tabella. |

Per ulteriori informazioni sul reporting di Analytics for Target, visita [Reporting di A4T](https://docs.adobe.com/content/help/it-IT/target/using/integrate/a4t/reporting.html)
