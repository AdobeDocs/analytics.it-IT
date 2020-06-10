---
description: Il pannello Analytics for Target (A4T) consente di analizzare le attività e le esperienze Adobe Target in Analysis Workspace.
title: Pannello Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: f688748e21b2b494845c682b380b12d3d346bfd3
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 6%

---


# Pannello Analytics for Target (A4T)

>[!IMPORTANT]
>
>**[!UICONTROL Analytics for Target (A4T)]** al momento il test del pannello è limitato. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/landing/an-releases.html)

Il pannello Analytics for Target (A4T) consente di analizzare le attività e le esperienze Adobe Target in Analysis Workspace. Consente inoltre di visualizzare l&#39;incremento e la confidenza per un massimo di 3 metriche di successo. Per accedere al pannello A4T, andate a una suite di rapporti con i componenti A4T abilitati. Quindi, fai clic sull’icona del pannello a sinistra e trascina il pannello Analytics for Target nel progetto Analysis Workspace.

## Generatore di pannelli A4T

Potete configurare il pannello A4T usando le seguenti impostazioni:

| Impostazione | Descrizione |
|---|---|
| Target Attività | Selezionate da un elenco di attività Target, oppure trascinate e rilasciate un&#39;attività dalla barra a sinistra.<br>**Nota:**L&#39;elenco è composto con gli ultimi 6 mesi di attività che hanno avuto almeno 1 hit. Se nell&#39;elenco non viene visualizzata un&#39;attività, la durata potrebbe essere superiore a 6 mesi. Può essere aggiunto dalla barra a sinistra, che ha un periodo di look-back fino a 18 mesi. |
| Esperienza di controllo | Seleziona la tua esperienza di controllo. Se necessario, potete modificarlo nel menu a discesa. |
| Normalizzazione della metrica | Scegli tra Visitatori univoci, Visite o Impressioni dell&#39;attività. I visitatori univoci sono consigliati per la maggior parte dei casi di utilizzo dell&#39;analisi. |
| Metriche di successo | Seleziona fino a 3 eventi di successo standard (non calcolati) dai menu a discesa, oppure trascina e rilascia le metriche dalla barra a sinistra. Ogni metrica avrà una tabella e una visualizzazione dedicate nel pannello di cui è stato effettuato il rendering. |
| Intervallo date calendario | Questo verrà compilato automaticamente in base all&#39;intervallo di date dell&#39;attività da Adobe Target. Potete cambiarlo se necessario. |

![](assets/a4t-panel-builder.png)

## Uscita pannello A4T

Il pannello Analytics for Target restituisce un set completo di dati e visualizzazioni per consentirvi di comprendere meglio le prestazioni dell&#39;attività e delle esperienze Adobe Target. Nella parte superiore del pannello, viene visualizzata una riga di riepilogo con cui ricordare le impostazioni del pannello selezionate. In qualsiasi momento, potete modificare il pannello facendo clic sulla matita di modifica in alto a destra.

Per ogni metrica di successo selezionata, verrà visualizzata una tabella a forma libera e una tendenza del tasso di conversione:

![](assets/a4t-rendered.png)

Ogni tabella a forma libera mostra le seguenti colonne di metriche:

| Metrica | Descrizione |
|---|---|
| Normalizzazione delle metriche | Visitatori, visite o impressioni di attività univoche. |
| Metrica di successo | La metrica selezionata nel generatore |
| Tasso di conversione | Metrica di successo/Normalizzazione della metrica |
| Incremento | Confronta il tasso di conversione per ogni esperienza rispetto all’esperienza di controllo.<br>**Nota:**Lift è una &quot;metrica bloccata&quot; per le esperienze Target; non può essere suddiviso o utilizzato con altre dimensioni. |
| Lift (Inferiore) | Rappresenta l&#39;incremento peggiore che una variante potrebbe avere sul controllo. |
| Lift (Mid) | Rappresenta l&#39;incremento di un punto intermedio che una variante potrebbe avere sul controllo, a un intervallo di confidenza del 95%. Questo è &quot;Lift&quot; in Reporting e analisi. |
| Solleva (superiore) | Rappresenta l&#39;incremento migliore che un&#39;esperienza di variante potrebbe avere sul controllo. |
| Affidabilità | Il test degli studenti calcola il livello di confidenza, il che indica la probabilità che i risultati vengano duplicati se il test viene eseguito di nuovo. Alla metrica è stato applicato un intervallo di formattazione condizionale fisso del 75%/85%/95%. Questa formattazione può essere personalizzata, se necessario, in Impostazioni colonna. <br>**Nota:**La confidenza è una &quot;metrica bloccata&quot; per le esperienze Adobe Target. Non può essere suddiviso o utilizzato con altre dimensioni. |

Come per qualsiasi pannello in Analysis Workspace, puoi continuare l&#39;analisi aggiungendo ulteriori tabelle e [visualizzazioni](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) che ti aiuteranno ad analizzare le tue attività Adobe Target.

## Domande frequenti sul pannello A4T

| Domanda | Risposta |
|---|---|
| Quali tipi di attività sono supportati in A4T? | [Ulteriori](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup.html) informazioni sui tipi di attività supportati. |
| Le metriche calcolate sono supportate nel reporting A4T? | No. [Ulteriori](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence.html) informazioni sui motivi per cui le metriche calcolate non sono supportate. |
| Perché i visitatori unici dovrebbero variare tra Target e Analytics? | [Ulteriori](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports.html) informazioni sulle varianti di visitatori unici tra i prodotti. |

Per ulteriori informazioni sui report di Analytics per Target, visita il report [A4T](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/reporting.html)
