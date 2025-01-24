---
description: Utilizza la visualizzazione di riepilogo delle metriche chiave per confrontare le prestazioni delle metriche in due timeline.
title: Riepilogo delle metriche chiave
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 55%

---

# Riepilogo delle metriche chiave {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Riepilogo delle metriche chiave"
>abstract="Crea una visualizzazione che combina grafici a linee, a variazione di riepilogo e a numero di riepilogo. Utilizza questa visualizzazione per confrontare la tendenza delle metriche importanti tra due periodi di tempo."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo documenta la visualizzazione del riepilogo delle metriche chiave in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulta [Riepilogo delle metriche chiave](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/key-metric) per_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**versione del Customer Journey Analytics** di questo articolo._

>[!ENDSHADEBOX]

La visualizzazione [!UICONTROL Key metric summary] ti consente di vedere come si presenta una metrica importante in un singolo arco temporale. Consente inoltre di confrontare le prestazioni delle metriche in due archi temporali. Fornisce i vantaggi di più visualizzazioni combinate in un’unica visualizzazione:

* Visualizzazioni di **[!UICONTROL Line]** che mostrano la tendenza della metrica per gli intervalli di date principali e di confronto

* **[!UICONTROL Summary percent change]** che mostra l’aumento o la diminuzione della metrica tra gli intervalli di date principali e di confronto

* Valore totale corrente ([!UICONTROL **numero di riepilogo**]) per la metrica

## Casi d’uso

Questa visualizzazione tratta diversi casi d’uso comuni, tra cui:

* Un analista che cerca di capire l’aspetto della creazione di opportunità questo mese rispetto allo stesso arco temporale dello scorso anno.

* Un addetto al marketing che esplora in che modo la generazione di lead per uno specifico tipo di lead è cambiata da questo mese all’ultimo mese.

* Un dirigente che vuole capire come sono cambiate le prenotazioni da questo trimestre all’ultimo trimestre.

## Configurare il riepilogo delle metriche chiave

1. Trascina visualizzazione **[!UICONTROL Key metric summary]** dal menu **[!UICONTROL Visualizations]** nella barra a sinistra in un pannello.

   ![](assets/key-metric-config.png)

1. Configura la visualizzazione con le seguenti opzioni:

   | Impostazione di configurazione | Definizione |
   | --- | --- |
   | **[!UICONTROL Metric]** | Seleziona la metrica da esaminare. Sono supportate tutte le metriche. |
   | **[!UICONTROL Primary date range]** | L’intervallo di date corrente per la tabella a forma libera.<p>Scegli uno degli intervalli di date disponibili nella suite di rapporti.</p> <p>Scegli [!UICONTROL **Intervallo date pannello**] se desideri utilizzare lo stesso intervallo di date utilizzato nel pannello in cui si trova la visualizzazione.</p> |
   | **[!UICONTROL Comparison date range]** | L’intervallo di date che desideri confrontare con l’intervallo di date principale. |
   | **[!UICONTROL Segment (optional)]** | Qualsiasi segmento al quale sei interessato per questo riepilogo. |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >Quando il campo [!UICONTROL **Intervallo date primario**] è impostato su [!UICONTROL **Intervallo date pannello**], **[!UICONTROL Comparison date range]** può essere aggiornato automaticamente, a seconda che l&#39;opzione **[!UICONTROL Comparison date range]** scelta sia relativa all&#39;intervallo date primario o fissa.
   >
   >* **Relativo:** Se il campo **[!UICONTROL Comparison date range]** è impostato su un&#39;opzione relativa all&#39;intervallo di date primario (ad esempio [!UICONTROL **Giorno precedente**], [!UICONTROL **Stesso giorno della settimana scorsa**], [!UICONTROL **Stesso giorno 4 settimane prima**] e così via), eventuali aggiornamenti al campo [!UICONTROL **Intervallo di date primario**] fanno sì che **[!UICONTROL Comparison date range]** venga aggiornato automaticamente al periodo immediatamente successivo all&#39;intervallo di date del pannello.
   >* **Fisso:** se il campo [!UICONTROL **Intervallo date di confronto**] è impostato su un intervallo di date fisso (ad esempio **3 febbraio 2023**), le modifiche apportate al campo [!UICONTROL **Intervallo date principale**] o all&#39;intervallo date del pannello non hanno alcun effetto sull&#39;[!UICONTROL **Intervallo date di confronto**]. Tuttavia, eventuali aggiornamenti all&#39;intervallo di date del pannello causano l&#39;aggiornamento automatico dell&#39;[!UICONTROL **Intervallo di date principale**].

1. Seleziona **[!UICONTROL Build]**.

## Visualizza l’output

L’output deve essere simile al seguente:

![](assets/key-metric-output.png)

Quando visualizzi l’output, tieni presente quanto segue:

* Il grafico a linee **[!UICONTROL Previous period]** (sempre visualizzato in grigio) corrisponde a **[!UICONTROL Comparison date range]** nel passaggio di configurazione.

* Se durante la configurazione non viene specificato un intervallo di date di confronto o se questo è nascosto nelle impostazioni di visualizzazione, viene visualizzato solo il grafico a linee per l’intervallo di date principale. La modifica di riepilogo è nascosta.

* Da qui, puoi passare il cursore del mouse sui grafici a linee per vedere le statistiche dei singoli giorni:

![](assets/key-metric-output2.png)

## Impostazioni di visualizzazione

Il riepilogo delle metriche chiave offre diverse impostazioni flessibili per consentire una migliore generazione di rapporti e comunicazioni di metriche importanti. È possibile accedere alle impostazioni tramite l’icona a forma di ingranaggio nell’angolo in alto a destra della visualizzazione.

![](assets/key-metric-settings.png)

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Emphasize percent change]** | Visualizzare la modifica di riepilogo in grassetto prominente al centro della visualizzazione |
| **[!UICONTROL Emphasize number value]** | Visualizzare il numero di riepilogo in grassetto prominente al centro della visualizzazione |
| **[!UICONTROL Legend visible]** | Mostrare o nascondere la legenda nella parte inferiore della visualizzazione |
| **[!UICONTROL Show annotations]** | Mostrare o nascondere le annotazioni aggiunte da un amministratore |
| **[!UICONTROL Show sparklines]** | Mostra o nascondi i grafici a linee nella parte inferiore del grafico. Quando è nascosta, la legenda non fa più riferimento visivamente alle linee |
| **[!UICONTROL Show min and max on sparklines]** | Mostrare o nascondere valori minimi e massimi nei grafici a linee principali e a linee di confronto |
| **[!UICONTROL Show comparison]** | Mostra o nascondi i dati di confronto. Quando sono nascosti, gli oggetti grafico a linee di confronto e di riepilogo delle modifiche sono nascosti. |
| **[!UICONTROL Show total number]** | Mostrare o nascondere il numero di riepilogo |
| **[!UICONTROL Show raw difference]** | Mostra o nascondi la differenza non elaborata tra il valore totale della metrica nell’intervallo di date principale e l’intervallo di date secondario. |
| **[!UICONTROL Abbreviate value]** | Abbrevia i valori numerici per semplificare le informazioni comunicate (ad esempio, 20.000 -> 20K) |

## Visualizzazione Modifica

Dopo aver creato la visualizzazione, puoi comunque modificare la configurazione originale.

1. Fai clic sull’icona a forma di matita nell’angolo in alto a destra della visualizzazione (accanto all’icona a forma di ingranaggio delle impostazioni).

   ![](assets/edit-icon.png)

   Ora ritorni alla visualizzazione di configurazione originale.

1. Modifica la metrica, l’intervallo di date primario, l’intervallo di date del confronto o il segmento come preferisci.
