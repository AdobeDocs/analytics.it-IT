---
description: Utilizza la visualizzazione di riepilogo delle metriche chiave per confrontare le prestazioni delle metriche in due timeline.
title: Riepilogo delle metriche chiave
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 96%

---

# Riepilogo delle metriche chiave {#key-metric-summary}

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Riepilogo delle metriche chiave"
>abstract="Crea una visualizzazione che combina grafici a linee, a variazione di riepilogo e a numero di riepilogo. Utilizza questa visualizzazione per confrontare la tendenza delle metriche importanti tra due periodi di tempo."


>[!BEGINSHADEBOX]

_Questo articolo documenta la visualizzazione del riepilogo delle metriche chiave in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Consulta [Riepilogo delle metriche chiave](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/visualizations/key-metric) per_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** versione di questo articolo._

>[!ENDSHADEBOX]


La visualizzazione ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric summary]** ti consente di scoprire la tendenza di una metrica importante in un singolo arco temporale. Consente inoltre di confrontare le prestazioni delle metriche in due archi temporali. Fornisce i vantaggi di più visualizzazioni combinate in un’unica visualizzazione:

* La visualizzazione **[!UICONTROL Line]** mostra la tendenza della metrica per gli intervalli di date principali e di confronto

* **[!UICONTROL Summary percent change]** mostra l’aumento o la diminuzione della metrica tra gli intervalli di date principali e di confronto

* Valore totale corrente ([!UICONTROL **numero di riepilogo**]) per la metrica

## Casi d’uso

Questa visualizzazione tratta diversi casi d’uso comuni, tra cui:

* Un analista che cerca di capire l’aspetto della creazione di opportunità questo mese rispetto allo stesso arco temporale dello scorso anno.

* Un addetto al marketing che esplora in che modo la generazione di lead per uno specifico tipo di lead è cambiata da questo mese all’ultimo mese.

* Un dirigente che vuole capire come sono cambiate le prenotazioni da questo trimestre all’ultimo trimestre.

## Utilizzo

1. Aggiungi una visualizzazione ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric summary]**. Consulta [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Configura la visualizzazione selezionando una **[!UICONTROL Metric]**, un **[!UICONTROL Primary date range]**, un **[!UICONTROL Comparison date range]** (facoltativo) e un **[!UICONTROL Filter]** (facoltativo):

   ![Configurazione delle metriche chiave che mostra le opzioni per metrica, intervallo di date principale, intervallo di date di confronto e segmento.](assets/key-metrics-config.png)

   | Opzione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Metric]** | Seleziona la metrica da esaminare. Sono supportate tutte le metriche. |
   | **[!UICONTROL Primary date range]** | L’intervallo di date corrente per la tabella a forma libera.<p>Scegli uno degli intervalli di date disponibili nella visualizzazione dati.</p> <p>Scegli [!UICONTROL **Intervallo date del pannello**] se desideri utilizzare lo stesso intervallo di date utilizzato nel pannello in cui si trova la visualizzazione.</p> |
   | **[!UICONTROL Comparison date range]** | L’intervallo di date che desideri confrontare con l’intervallo di date principale. |
   | **[!UICONTROL Filter (optional)]** | Qualsiasi segmento a cui sei interessato per questo riepilogo. |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >Quando il campo [!UICONTROL **Intervallo date principale**] è impostato su [!UICONTROL **Intervallo date pannello**], l’**[!UICONTROL Comparison date range]** può essere aggiornato automaticamente, a seconda che l’opzione **[!UICONTROL Comparison date range]** scelta sia relativa all’intervallo date principale o fisso.
   >
   >* **Relativo:** se il campo **[!UICONTROL Comparison date range]** è impostato su un’opzione relativa all’intervallo di date principale (ad esempio [!UICONTROL **Giorno precedente**], [!UICONTROL **Stesso giorno della settimana scorsa**], [!UICONTROL **Stesso giorno 4 settimane prima**] e così via), eventuali aggiornamenti al campo [!UICONTROL **Intervallo di date principale**] fanno sì che l’**[!UICONTROL Comparison date range]** venga aggiornato automaticamente al periodo immediatamente successivo all’intervallo di date del pannello.
   >* **Fisso:** se il campo [!UICONTROL **Intervallo date di confronto**] è impostato su un intervallo di date fisso (ad esempio **3 febbraio 2023**), le modifiche apportate al campo [!UICONTROL **Intervallo di date principale**] o all’intervallo date del pannello non hanno alcun effetto sull’[!UICONTROL **Intervallo date di confronto**]. Tuttavia, eventuali aggiornamenti all’intervallo di date del pannello causano l’aggiornamento automatico dell’[!UICONTROL **Intervallo di date principale**].

1. Seleziona **[!UICONTROL Build]**.

L’output del riepilogo delle metriche chiave è simile al seguente:

![Output delle metriche chiave che mostra la metrica, la variazione di riepilogo, il numero di riepilogo e i grafici a linee.](assets/key-metrics.png)

Quando visualizzi questo output, prendi in considerazione quanto segue:

* Il grafico a linee **[!UICONTROL Previous period]** (visualizzato sempre in grigio) corrisponde all’**[!UICONTROL Comparison date range]** nel passaggio di configurazione.

* Se durante la configurazione non viene specificato un intervallo di date di confronto o se questo è nascosto nelle impostazioni di visualizzazione, viene visualizzato solo il grafico a linee per l’intervallo di date principale. La variazione di riepilogo sarà nascosta.

* Da qui, puoi passare il puntatore sui grafici a linee per vedere le statistiche dei singoli giorni:


## Configurare

Dopo aver creato la visualizzazione, puoi modificare la configurazione originale.

1. Seleziona ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Configure visualization]** nella parte superiore della visualizzazione.

   Sarai riportato alla finestra di dialogo della configurazione originale.

1. Modifica le impostazioni come preferisci. Seleziona **[!UICONTROL Reset]** per ripristinare le impostazioni correnti. Seleziona **[!UICONTROL Build]** per ricreare la visualizzazione.

## Impostazioni

Come parte delle impostazioni di visualizzazione, sono disponibili impostazioni specifiche di riepilogo delle metriche chiave.

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Emphasize percent change]** | Visualizzare la modifica di riepilogo in grassetto prominente al centro della visualizzazione |
| **[!UICONTROL Emphasize number value]** | Visualizzare il numero di riepilogo in grassetto prominente al centro della visualizzazione |
| **[!UICONTROL Legend visible]** | Mostrare o nascondere la legenda nella parte inferiore della visualizzazione |
| **[!UICONTROL Show annotations]** | Mostrare o nascondere le annotazioni aggiunte da un amministratore |
| **[!UICONTROL Hide title]** | Nascondi il titolo della visualizzazione. |
| **[!UICONTROL Percentages]** | Visualizza la visualizzazione in percentuale anziché con un numero. |
| **[!UICONTROL Show trendlines]** | Mostra le linee di tendenza nella visualizzazione. |
| **[!UICONTROL Show max and min on trendlines]** | Mostrare o nascondere valori minimi e massimi nei grafici a linee principali e a linee di confronto |
| **[!UICONTROL Show comparison percentage and trendline]** | Mostra o nascondi i dati di confronto. Quando sono nascosti, non vengono visualizzati gli oggetti Grafico a linee di confronto e Variazione di riepilogo. |
| **[!UICONTROL Show total number]** | Mostrare o nascondere il numero di riepilogo |
| **[!UICONTROL Show raw difference]** | Mostra o nascondi la differenza non elaborata tra il valore totale della metrica nell’intervallo di date principale e l’intervallo di date secondario. |
| **[!UICONTROL Abbreviate value]** | Seleziona **[!UICONTROL Abbreviate value]** per abbreviare in modo intelligente il valore numerico. Se questa opzione è selezionata, immetti un numero per definire la quantità di abbreviazione. Ad esempio:<br/><table><tr><td>**Valore originale**</td><td>**Abbreviazione**</td><td>**Risultato**</td></tr><tr><td>12.011.141,25 $</td><td>Non selezionato</td><td align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su 1</td><td align="right">12 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su 2</td><td align="right">12,0 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su 2</td><td align="right">12,011 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Seleziona, imposta su 3</td><td align="right">12,011 milioni $</td></tr></table> |

## Visualizzazione Modifica

Dopo aver creato la visualizzazione, puoi comunque modificare la configurazione originale.

1. Fai clic sull’icona a forma di matita nell’angolo in alto a destra della visualizzazione (accanto all’icona a forma di ingranaggio delle impostazioni).

   ![Icona modifica visualizzazione](assets/edit-icon.png)

   Ora ritorni alla visualizzazione di configurazione originale.

1. Modifica la metrica, l’intervallo di date principale, l’intervallo di date del confronto o il filtro, come preferisci.

>[!MORELIKETHIS]
>
>[Aggiungi una visualizzazione a un pannello](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Impostazioni di visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menu di scelta rapida della visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)

