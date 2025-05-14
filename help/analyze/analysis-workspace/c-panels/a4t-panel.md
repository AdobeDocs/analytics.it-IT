---
description: Il pannello Analytics for Target (A4T) ti consente di analizzare le attività e le esperienze Adobe Target in Analysis Workspace.
title: Pannello Analytics for Target (A4T)
feature: Panels
role: User, Admin
exl-id: 36bca104-37b8-43c6-b8d0-b607a9a333cc
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 50%

---

# Pannello Analytics for Target {#analyze-for-target-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_a4t_button"
>title="Analytics for Target"
>abstract="Analizza le attività ed esperienze Target in Analysis Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_a4t_panel"
>title="Pannello Analytics for Target"
>abstract="Analizza le attività ed esperienze Target in Analysis Workspace.<br/><br>**Parametri **<br/>**Attività Target**: l’attività Target che verrà analizzata.<br/>**Esperienza di controllo**: esperienza di controllo per l’attività Target selezionata.<br/>**Metrica di normalizzazione**: visitatori, visite o impression. Questa metrica (detta anche metodologia di conteggio) diventa il denominatore del calcolo dell’incremento. Inoltre, influisce sul modo in cui i dati vengono aggregati prima dell’applicazione del calcolo del valore di affidabilità.<br/>**Metriche di successo**: fino a 3 metriche di successo standard (non calcolate) per analizzare l’attività Target."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Questo articolo documenta il pannello Analytics for Target in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulta [Pannello Sperimentazione](https://experienceleague.adobe.com/it/docs/analytics/analyze/analysis-workspace/panels/a4t-panel) per informazioni su come confrontare diverse esperienze utente, varianti di marketing o di messaggistica in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Il pannello Analytics for Target consente di analizzare le attività e le esperienze Adobe Target in Analysis Workspace. Il pannello consente inoltre di visualizzare l’incremento e l’affidabilità per un massimo di 3 metriche di successo. Per accedere al pannello Analytics for Target, passa a una suite di rapporti i cui sono abilitati i componenti Analytics for Target. Quindi, seleziona l’icona del pannello all’estrema sinistra e trascina il pannello Analytics for Target nel progetto Analysis Workspace.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Pannello Analytics for Target](https://video.tv.adobe.com/v/37247?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]

## Utilizzo

Per usare un pannello **[!UICONTROL Analytics for Target]**:

1. Crea un pannello **[!UICONTROL Analytics for Target]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.

### Input del pannello {#panel-nput}

Puoi configurare il pannello Analytics for Target utilizzando le seguenti impostazioni di input:

![Input pannello A4T](assets/a4t-panel-input.png)

| Impostazione | Descrizione |
|---|---|
| **[!UICONTROL Target Activity]** | Seleziona da un elenco di attività di destinazione. L’elenco è composto dagli ultimi 6 mesi di attività che hanno avuto almeno 1 hit. Se nell’elenco non viene visualizzata un’attività, potrebbe essere più vecchia di 6 mesi. Può essere comunque aggiunta dalla barra a sinistra, che ha un periodo di lookback fino a 18 mesi. |
| **[!UICONTROL Control Experience]** | Seleziona l’esperienza di controllo. |
| **[!UICONTROL Normalizing metric]** | Seleziona Visitatori, Visite o Impression. [!UICONTROL Visitors] è consigliato per la maggior parte dei casi di utilizzo di analisi. Questa metrica (detta anche metodologia di conteggio) diventa il denominatore del calcolo dell’incremento. Inoltre, influisce sul modo in cui i dati vengono aggregati prima dell’applicazione del calcolo del valore di affidabilità. |
| **[!UICONTROL Success metrics]** | Seleziona fino a 3 eventi di successo standard (non calcolati) dal menu a discesa, oppure trascina e rilascia le metriche da Metriche nella barra Componenti. Ogni metrica dispone di una tabella e di una visualizzazione dedicate nel pannello renderizzato. |

Seleziona **[!UICONTROL Build]** per creare il pannello.

### Output del pannello {#panel-output}

Il pannello Analytics for Target restituisce un set completo di dati e visualizzazioni per consentirti di comprendere meglio le prestazioni dell’attività e delle esperienze Adobe Target. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate. Per ogni metrica di successo selezionata, viene visualizzata una [tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) e una visualizzazione [riga](/help/analyze/analysis-workspace/visualizations/line.md) che mostra la tendenza del tasso di conversione:

![Rendering](assets/a4t-panel-output.png)

Ogni tabella a forma libera mostra le seguenti colonne di metriche:

| Metrica | Descrizione |
|---|---|
| **[!UICONTROL Normalizing metrics]** | La metrica di normalizzazione selezionata nel pannello di input: Visitatori univoci, Visite o Impression attività. |
| **[!UICONTROL Success metric]** | La metrica di successo selezionata nel pannello di input. |
| **[!UICONTROL Conversion rate]** | La metrica di successo/metrica di normalizzazione. |
| **[!UICONTROL Lift]** | Confronta il tasso di conversione per ogni esperienza rispetto all’esperienza di controllo. Nota: Incremento è una *metrica bloccata* per le esperienze Target; non può essere raggruppata o utilizzata con altre dimensioni. |
| **[!UICONTROL Lift (Lower)]** | Questo valore rappresenta l’incremento peggiore che un’esperienza diversa potrebbe avere sul controllo con un intervallo di affidabilità del 95%.<br>Per ulteriori informazioni, vedere [Calcoli statistici](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) e [Completa calcolatore di affidabilità](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) file Excel. |
| **[!UICONTROL Lift (Mid)]** | Questo valore rappresenta l’incremento intermedio che un’esperienza diversa potrebbe avere sul controllo con un intervallo di affidabilità del 95%. <br>Per ulteriori informazioni, vedere [Calcoli statistici](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) e [Completa calcolatore di affidabilità](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) file Excel. |
| **[!UICONTROL Lift (Upper)]** | Questo valore rappresenta l’incremento migliore che un’esperienza diversa potrebbe avere sul controllo con un intervallo di affidabilità del 95%.<br>Per ulteriori informazioni, vedere [Calcoli statistici](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) e [Completa calcolatore di affidabilità](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) file Excel. |
| **[!UICONTROL Confidence]** | Il test t di Student calcola il livello di affidabilità, che indica la probabilità che i risultati vengano duplicati se il test viene eseguito di nuovo. Alla metrica è stato applicato un intervallo di formattazione condizionale fisso del 75%/85%/95%. Questa formattazione può essere personalizzata, se necessario, in Column settings. Nota: Affidabilità è una “metrica bloccata” per le esperienze Target, non può essere raggruppata o utilizzata con altre dimensioni.<br>Per ulteriori informazioni, vedere [Calcoli statistici](https://experienceleague.adobe.com/en/docs/target/using/reports/statistical-methodology/statistical-calculations) e [Completa calcolatore di affidabilità](https://experienceleague.adobe.com/docs/target/assets/complete_confidence_calculator.xlsx) file Excel. |

Come per qualsiasi pannello in Analysis Workspace, puoi continuare la tua analisi aggiungendo ulteriori tabelle e [visualizzazioni](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations) che ti aiuteranno ad analizzare le tue attività Adobe Target. È inoltre possibile applicare un segmento a livello di pannello o all’interno della tabella a forma libera. Se lo si aggiunge all’interno della tabella a forma libera, è necessario sovrapporlo all’intera tabella per mantenere i calcoli relativi all’incremento e all’attendibilità. Al momento, i segmenti a livello di colonna non sono supportati.

Utilizza ![Modifica](/help/assets/icons/Edit.svg) per riconfigurare e ricreare il pannello.

## Domande frequenti {#FAQ}

| Domanda | Risposta |
|---|---|
| Quali tipi di attività sono supportati in Analytics for Target? | [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-activity-setup) sui tipi di attività supportati. |
| Le metriche calcolate sono supportate nei calcoli di incremento e affidabilità? | No. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence) sui motivi per cui le metriche calcolate non sono supportate in incremento e affidabilità. Tuttavia, le metriche calcolate possono essere utilizzate nel reporting di Analytics for Target al di fuori di tali metriche. |
| Perché i visitatori univoci dovrebbero variare tra Target e Analytics? | [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports) sulle varianze di visitatori univoci tra i prodotti. |
| Quando applico un segmento di hit per una specifica attività Target nell’analisi, perché viene restituita un’esperienza non correlata? | La dimensione di Analytics for Target è una variabile di elenco, il che significa che può contenere più attività (ed esperienze) alla volta. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-viewing-reports) |
| La metrica di affidabilità tiene conto di ordini estremi o applica una correzione Bonferroni per offerte multiple? | No. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t-faq/a4t-faq-lift-and-confidence) su come Analytics calcola l’affidabilità. |
| È possibile utilizzare le metriche Incremento e Affidabilità con altre dimensioni o raggruppamenti? | Incremento e Affidabilità sono “metriche bloccate” per la dimensione delle esperienze di Target perché richiedono un controllo e una variante su cui eseguire il calcolo. In quanto tali, non possono essere suddivise o utilizzate con altre dimensioni. |
| Quando ricalcolano Incremento e Affidabilità? | Incremento e affidabilità vengono ricalcolati ogni volta che il pannello viene generato, l’intervallo di date del pannello viene modificato o un segmento viene applicato al pannello o alla tabella. Quando applichi un filtro segmento alla tabella a forma libera, il segmento deve essere applicato a tutte le colonne; in caso contrario, l’incremento e l’affidabilità non vengono aggiornati correttamente. I segmenti a livello di colonna non sono supportati. |

Per ulteriori informazioni sul reporting di Analytics for Target, visita [Reporting di Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/reporting)
