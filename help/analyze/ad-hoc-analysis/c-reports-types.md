---
description: Descrizioni dei tipi di report utilizzati in Experience Cloud.
seo-description: Descrizioni dei tipi di report utilizzati in Experience Cloud.
seo-title: Tipi di rapporti
solution: Analytics
title: Tipi di rapporti
topic: Analisi ad hoc
uuid: 357102 eb-a 172-40 ec-a 302-01 c 87 abaacb 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Tipi di rapporti

Descrizioni dei tipi di report utilizzati in Experience Cloud.

## Rapporti con classifica {#concept_E1710FFFBB334F3D9DB63A1626DBCB01}

Visualizza una tabella con elementi classificati, utilizzando numeri e percentuali nelle metriche. For example, a [!UICONTROL Pages Report] ranks the pages on your site based on traffic, and the detail table shows percentages and numbers for metrics like Page Views and Revenue. Un grafico a barre orizzontale è il tipo di grafico predefinito. I grafici presentano un colore per ogni metrica. I report Ranked possono mostrare più metriche in uno stesso report.

<!-- 

c_reports_ranked.xml

 -->

I grafici classificati sono predefiniti a cinque elementi, ma potete grafico fino a trenta elementi nelle opzioni del grafico.

## Trended Reports {#concept_65FEA92704024232BB21A5952939711F}

Consente di analizzare il modo in cui le conversioni e gli eventi puntano alla granularità temporale selezionata (Ora, Giorno, Settimana, Mese, Trimestre o Anno) durante un periodo di reporting.

<!-- 

c_reports_trended.xml

 -->

Nel grafico, l'asse verticale visualizza gli elementi tracciati. L'asse orizzontale visualizza la granularità temporale. Nella tabella è possibile impostare tendenze da una cella specifica e avviare un rapporto completo dalla cella. La data o l'ora utilizzata si basa sul valore della cella.

Puoi anche selezionare più celle e avviare un rapporto con tendenze, in base a una granularità selezionata. Quando si progetta un trend da più celle, le colonne di rapporti visualizzano dati per l'intero periodo di reporting.

A [!UICONTROL Products Report] is an example of a trended report. Puoi vedere quante entrate sono state effettuate a un prodotto durante il periodo selezionato. Se il periodo di reporting è una settimana, puoi vedere il volume di ricavi generati per ogni giorno del periodo di tempo, visualizzare un grafico tendenza per un prodotto specifico nel giorno specificato oppure aprire un rapporto con tendenze separato per la selezione.

## Trend from Cells {#task_AD9275BED5CE4D61AC25778D144406A4}

Passaggi che descrivono come avviare un rapporto tendenze da una o più celle in una tabella.

<!-- 

t_trend_row.xml

 -->

**Tendenza delle celle**

1. Apri un report con classifica.
1. In the table, locate the cell and click **[!UICONTROL Trend]**.

   ![](assets/TrendInspector_Buttcon.png)

1. To view a full report from the cell, click **[!UICONTROL Launch Trend Report]**.

   Alternatively, right-click the cell, then click **[!UICONTROL Trend Cell]**. Potete eseguire questa operazione anche dopo aver selezionato più celle.

## Totals Report {#concept_48E23FB3BCCD43DFB486A048960800A8}

<!-- 

c_reports_totals.xml

 -->

Report a livello di esecutivo che mostra le cifre sottostanti. Contiene dati per entrate totali, visualizzazioni di pagina e ordini. Puoi segmentare il rapporto e aggiungere metriche aggiuntive per visualizzare ulteriori dati.

## Flow Reports {#concept_3E417D018F1B4566973F694B01E6439F}

I rapporti sul flusso mostrano i percorsi più comuni seguiti dagli utenti in pagine, sezioni del sito e server.

<!-- 

c_reports_flow.xml

 -->

**Flusso successivo**

The [!UICONTROL Next Flow] report group has three reports: [!UICONTROL Next Page Flow], [!UICONTROL Next Section Flow], and [!UICONTROL Next Server Flow]. I rapporti di questo gruppo mostrano le pagine più comuni, le sezioni del sito e i server a cui accedono i visitatori dopo l'accesso alla pagina, alla sezione del sito o al server specificato. Questi rapporti mostrano i percorsi più comuni seguiti dal sito Web.

**Flusso precedente**

I rapporti di Flusso precedenti sono simili ai rapporti di Flusso successivo, eccetto per vedere dove i visitatori si sono spostati dopo una pagina selezionata, dove vedere dove si trovavano i visitatori prima di visitare una pagina specificata. I controlli per l'utilizzo del rapporto sono identici ai controlli per i rapporti Flusso successivo.

## Next Pages Flow {#concept_F7565234927942BEAF75D5D94A7AB47D}

Visualizza le visualizzazioni dei percorsi o il numero di volte e percentuali in cui una pagina è stata visualizzata entro i limiti dei percorsi. Ad esempio, una pagina Informativa sulla privacy potrebbe avere 10,000 visualizzazioni di pagina totali, ma solo il 500 di tali visualizzazioni si è verificato immediatamente prima di una home page. In questo caso, visualizzerai visualizzazioni di percorso 500. Puoi visualizzare il rapporto a livello di visita o di visitatore. Le percentuali per ogni pagina sono visualizzate accanto al nome della pagina. La larghezza di una riga collegata a una pagina rappresenta la percentuale relativa di visite.

<!-- 

c_reports_next_page_flow.xml

 -->

Per impostazione predefinita, questo rapporto visualizza le prime 10 pagine che gli utenti hanno visitato dopo la pagina selezionata. Potete fare clic su una pagina sottolineata per espandere ulteriormente il grafico. Non esiste alcun limite al numero di pagine che puoi includere sul grafico, e puoi passare il cursore sopra una pagina per visualizzare i dati relativi alle visite e alle entrate per la pagina.

Utilizzate questo rapporto per:

* Scopri i passaggi che vengono eseguiti più frequentemente dopo la visualizzazione di una pagina selezionata.
* Ottimizzate la progettazione del percorso del sito per un funnel del traffico verso una pagina obiettivo desiderata.
* Identificare dove vanno i visitatori rispetto alle pagine obiettivo desiderate.

## Next Server Flow {#concept_DB8C20E18AEA4051903C47A16C0E9C4E}

Visualizza i dati di navigazione tra i server sul sito. Quando selezionate un nome di server dal sito, il rapporto mostra il numero di visitatori che si spostano da tale server a ogni altro server sul sito in una singola visita o in più visite.

<!-- 

c_reports_next_server_flow.xml

 -->

Ad esempio, se avete dati specifici su server diversi o se avete eseguito il mirroring di dati su server separati, il rapporto mostra il percorso tra i server che gli utenti raggiungono. Ciò vale anche per i domini all'interno del sito Web. For example, you can see how many users went from a `https://www.mysite.com` to `https://info.mysite.com` or `https://sales.mysite.com`.

## Next Section Flow {#concept_7C9C8567E7DF477DA186E47DD3FD47A4}

[!UICONTROL Next Section Flow] Il rapporto è simile al [!UICONTROL Next Page Flow] rapporto. Visualizza i dati per Sezioni del sito (gruppi di pagine Web correlate). Se una pagina è contenuta in più sezioni del sito, il rapporto visualizza i dati per tutte le sezioni del sito.

<!-- 

c_reports_next_section_flow.xml

 -->

Ad esempio, un retailer online potrebbe avere sezioni di siti per i prodotti e sezioni del sito per i marchi di prodotto. In questo caso, una pagina Web di prodotto può essere suddivisa in più sezioni. Though a product page has only been viewed once, the [!UICONTROL Next Section Flow] report shows a page view for each sight section associated with the page.

## Previous Page Flow {#concept_ADEAEBAE3F37401B977A27E03B5A523B}

Similar to the [!UICONTROL Next Page Flow] report. [!UICONTROL Previous Page Flow] Il rapporto visualizza più livelli delle pagine più popolari visualizzate dalla pagina prima della pagina selezionata. Il rapporto evidenzia inoltre le pagine da cui i visitatori accedono al sito.

<!-- 

c_reports_previous_page_flow.xml

 -->

Utilizzate questo rapporto per:

* Scopri i passaggi più frequenti prima di visualizzare una pagina selezionata.
* Ottimizzate la progettazione del percorso del sito per un funnel del traffico verso una pagina obiettivo desiderata.

## Previous Section Flow {#concept_30688D97B48449E1958866BAF376FA8C}

[!UICONTROL Previous Section Flow] Il rapporto è simile al [!UICONTROL Previous Page Flow] rapporto. Visualizza i dati per Sezioni del sito (gruppi di pagine Web correlate). Se una pagina è contenuta in più sezioni del sito, il rapporto visualizza i dati per tutte le sezioni del sito.

<!-- 

c_reports_previous_section_flow.xml

 -->

Ad esempio, un retailer online potrebbe avere sezioni di siti per i prodotti e sezioni del sito per i marchi di prodotto. In questo caso, una pagina Web di prodotto può essere suddivisa in più sezioni. Though a product page has only been viewed once, the [!UICONTROL Previous Section Flow] report shows a page view for each sight section associated with the page.

## Previous Server Flow {#concept_8E43208CAF2C4C358F19D4669B73822F}

Questo rapporto mostra i dati di navigazione tra i server sul sito. Quando selezionate un nome di server dal sito, il rapporto mostra il numero di visitatori che si sono spostati su tale server da ogni altro server sul sito in una singola visita o in più visite.

<!-- 

c_reports_previous_server_flow.xml

 -->

Ad esempio, se avete dati specifici su server diversi o se avete eseguito il mirroring di dati su server separati, il rapporto mostra il percorso tra i server che gli utenti raggiungono. Ciò vale anche per i domini all'interno del sito Web. For example, you can see how many users went from a `www.mysite.com` to `info.mysite.com` or `sales.mysite.com`.

## Conversion Funnel Reports {#concept_35A2EB61E84441CBB670C2E02CA26F81}

I rapporti funnel di conversione mostrano percentuali di conversione tra eventi di metrica specifici. Puoi utilizzare questo rapporto per comprendere il numero di click-through che generano vendite e il numero di unità vendute. For example, a [!UICONTROL Products Conversion] report shows the percent of Carts events related to Visits events, and then displays totals for Orders, Revenue, and Units based on those events.

<!-- 

c_reports_conversion_funnel.xml

 -->

Sono disponibili i seguenti rapporti funnel:

* [!UICONTROL Purchase Conversion Funnel]: Mostra visite (specifici per report), carrelli, ordini, unità e guadagni.
* [!UICONTROL Cart Conversion Funnel]: Visualizza Visite (specifici per report), carrelli, pagamenti, ordini e guadagni.
* [!UICONTROL Custom Event Funnel]: Visualizza eventi personalizzati sul sito. Per impostazione predefinita, mostra eventi personalizzati 1-5.
* [!UICONTROL Campaign Conversion Funnel]: Mostra i click-through, i pagamenti, gli ordini e le entrate.

La tabella report mostra le statistiche relative alle vendite medie per click-through e le unità medie vendute per click-through. Potete aggiungere metriche e eventi personalizzati da altri gruppi di rapporti a tali rapporti. Questi funnel hanno numerose similarità, ma si basano su variabili ed eventi diversi. Potete utilizzare questi report per vedere quali percentuali e tendenze generali degli utenti attivano eventi specifici da voi specificati. Potete vedere dove gli utenti non seguono gli eventi, che forniscono indicazioni su tale punto specifico nel processo di conversione.

## Site Analysis Report {#concept_65694C6BDE424714B7975764F95497A4}

[!UICONTROL Site Analysis] visualizza il modo in cui i visitatori si spostano tra pagine ed eventi specifici. Ad esempio, potete vedere il flusso di traffico tra le pagine, l'affinità tra prodotti e canali di marketing e il modo in cui campagne e canali fanno fluire gli ordini dei prodotti. Puoi trascinare pagine, elementi dimensionali (ed elenchi) e eventi di metrica. Ogni cilindro rappresenta uno o più elementi dimensione (pagine) o un evento. Le frecce rappresentano il flusso tra i valori del cilindro. Le metriche sono assegnate alle posizioni cilindro (X e Y), alla larghezza cilindrica, all'altezza cilindrica e al colore. La posizione, le dimensioni e il colore variano a seconda dei valori delle metriche.

<!-- 

c_reports_site_analysis.xml

 -->

Trascinate gli elementi dai riquadri degli strumenti per aggiungerli al grafico o al campo delle dimensioni.

Fate clic con il pulsante destro del mouse sui cilindri per modificarli o rimuoverli.

<!-- Meike, UICONTROL and DNL stripped from tables. Re-add. -->

| Opzione | Descrizione |
|--- |--- |
| Mostra analisi sito in (Visita o Visitatore) | Consente di passare da Visita a Visitatore per analizzare il percorso dei visitatori. Queste impostazioni consentono di comprendere il coinvolgimento dei visitatori a livello di visitatore, tra le visite. I rapporti Analisi sito, Flusso e Abbandono sono abilitati per i percorsi dei visitatori. Modificando questa impostazione si ripristina il rapporto, vincolando i dati alla selezione. |
| Aggiungi punto di controllo | Visualizza l'Editor di Checkpoint da cui è possibile selezionare dimensioni o eventi da aggiungere alla visualizzazione. |
| Replace Chart (Sostituisci grafico) | Sostituisce il grafico Analisi sito con i punti di controllo aggiunti all'editor. |
| Adatta allo schermo | Ripristina la visualizzazione originale di un grafico. |
| Visualizzazione aerea | Fornisce una visualizzazione in alto del grafico. |
| Attiva/disattiva griglia | Attiva o disattiva la griglia. |
| Dimensione | L'elemento di cui state effettuando il reporting. Trascinate l'elemento da Dimensioni. |

| Opzione | Descrizione |
|--- |--- |
| Modificare       | Consente di aggiungere o rimuovere pagine a un cilindro. |
| Rimuovi | Consente di rimuovere un cilindro. |
| Rapporti | Consente di avviare un altro report dal cilindro. |
| Salva grafico come | Consente di salvare il grafico come. png o. jpg. Se modificate i controlli del grafico (angolo grafico, dimensioni) prima di salvare, le modifiche vengono mantenute nell'output. |
| Copia grafico negli Appunti | Copia il grafico da incollare in un'altra applicazione. Se modificate i controlli del grafico (angolo grafico, dimensioni) prima di salvare, le modifiche vengono mantenute nell'output. |
