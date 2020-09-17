---
description: Descrizioni dei tipi di report utilizzati in  Experience Cloud.
title: Tipi di rapporto
topic: Ad hoc analysis
uuid: 357102eb-a172-40ec-a302-01c87abaacb5
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '1669'
ht-degree: 3%

---


# Tipi di rapporto

>[!IMPORTANT]
>
> Adobe sta spostando  Ad Hoc Analysis a fine ciclo di vita il 1 marzo 2021. [Ulteriori informazioni...](https://adobe.ly/discoverworkspace).

Descrizioni dei tipi di report utilizzati in  Experience Cloud.

## Rapporti con classifica {#concept_E1710FFFBB334F3D9DB63A1626DBCB01}

Visualizza una tabella con elementi classificati, utilizzando numeri e percentuali nelle metriche. Ad esempio, una [!UICONTROL Pages Report] classifica le pagine del sito in base al traffico, e la tabella di dettaglio mostra percentuali e numeri per metriche come Visualizzazioni pagina e Entrate. Un grafico a barre orizzontale è il tipo di grafico predefinito. I grafici visualizzano un colore per ogni metrica. I report Ranked possono mostrare più metriche in uno stesso report.

<!-- 

c_reports_ranked.xml

 -->

Per impostazione predefinita, i grafici con classifica sono cinque, ma è possibile eseguire il grafico fino a trenta elementi nelle opzioni del grafico.

## Report con tendenze {#concept_65FEA92704024232BB21A5952939711F}

Consente di esaminare l&#39;andamento delle conversioni e degli eventi in un periodo di granularità temporale selezionato (ora, giorno, settimana, mese, trimestre o anno) durante un periodo di reporting.

<!-- 

c_reports_trended.xml

 -->

Nel grafico, l’asse verticale visualizza gli elementi tracciati. L’asse orizzontale visualizza la granularità del tempo. Nella tabella, è possibile eseguire tendenze da una cella specifica e avviare un rapporto completo dalla cella. La data o l&#39;ora utilizzata è basata sul valore della cella.

Potete anche selezionare più celle e avviare un rapporto con tendenze, in base a una granularità selezionata. Quando si crea una tendenza da più celle, nelle colonne del rapporto vengono visualizzati i dati per l&#39;intero periodo di reporting.

Un [!UICONTROL Products Report] è un esempio di report con tendenze. Puoi vedere quante entrate ha prodotto un prodotto durante il periodo selezionato. Se il periodo di reporting è una settimana, puoi vedere quante entrate ha generato il prodotto per ogni giorno del periodo di tempo, visualizzare un grafico delle tendenze per un prodotto specifico in quel giorno, oppure aprire un rapporto con tendenze separato per la selezione.

## Tendenza dalle celle {#task_AD9275BED5CE4D61AC25778D144406A4}

Passaggi che descrivono come avviare un rapporto sulle tendenze da una o più celle di una tabella.

<!-- 

t_trend_row.xml

 -->

**Tendenza dalle celle**

1. Aprite un report classifica.
1. Nella tabella, individuare la cella e fare clic su **[!UICONTROL Trend]**.

   ![](assets/TrendInspector_Buttcon.png)

1. Per visualizzare un rapporto completo dalla cella, fare clic su **[!UICONTROL Launch Trend Report]**.

   In alternativa, fare clic con il pulsante destro del mouse sulla cella, quindi scegliere **[!UICONTROL Trend Cell]**. È inoltre possibile eseguire questa operazione dopo aver selezionato più celle.

## Report totali {#concept_48E23FB3BCCD43DFB486A048960800A8}

<!-- 

c_reports_totals.xml

 -->

Un rapporto a livello esecutivo che mostra le cifre di fondo. Contiene dati per ricavi totali, visualizzazioni di pagina e ordini. Puoi segmentare il rapporto e aggiungere metriche aggiuntive per visualizzare dati aggiuntivi.

## Rapporti sul flusso {#concept_3E417D018F1B4566973F694B01E6439F}

I rapporti sul flusso mostrano i percorsi più comuni seguiti dagli utenti tra pagine, sezioni del sito e server.

<!-- 

c_reports_flow.xml

 -->

**Flusso successivo**

Il gruppo di [!UICONTROL Next Flow] relazioni ha tre rapporti: [!UICONTROL Next Page Flow], [!UICONTROL Next Section Flow]e [!UICONTROL Next Server Flow]. I rapporti in questo gruppo mostrano le pagine, le sezioni del sito e i server più comuni a cui ha avuto accesso un visitatore dopo l’accesso alla pagina, alla sezione del sito o al server specificato. Questi rapporti mostrano i percorsi più comuni seguiti all’interno del sito Web.

**Flusso precedente**

I rapporti sul flusso precedente sono simili ai rapporti sul flusso successivo, tranne per vedere dove sono andati i visitatori dopo una pagina selezionata, per vedere dove si trovavano i visitatori prima di visitare una pagina specifica. I controlli per l’utilizzo del rapporto sono identici ai controlli per i report Flusso successivo.

## Flusso pagine successivo {#concept_F7565234927942BEAF75D5D94A7AB47D}

Visualizza le visualizzazioni dei percorsi oppure il numero di volte e percentuali di visualizzazione di una pagina entro i limiti dei percorsi. Ad esempio, una pagina dell&#39;Informativa sulla privacy potrebbe avere 10.000 visualizzazioni totali di pagina, ma solo 500 di tali visualizzazioni si sono verificate immediatamente prima di una pagina principale. In questo caso, vedreste 500 visualizzazioni di percorso. Puoi visualizzare il rapporto a livello di visita o visitatore. Le percentuali per ogni pagina vengono visualizzate accanto al nome della pagina. La larghezza di una linea collegata a una pagina rappresenta la percentuale relativa di visite.

<!-- 

c_reports_next_page_flow.xml

 -->

Per impostazione predefinita, questo rapporto mostra le prime 10 pagine su cui gli utenti hanno eseguito il rendering dopo la pagina selezionata. Potete fare clic su qualsiasi pagina sottolineata per espandere ulteriormente il grafico. Non esiste alcun limite al numero di pagine che è possibile avere sul grafico e puoi passare il cursore del mouse su una pagina per visualizzare i dati di visita e ricavi per la pagina.

Utilizzate questo rapporto per:

* Scoprite i passaggi più frequenti dopo la visualizzazione di una pagina selezionata.
* Ottimizzate la progettazione del percorso del sito per indirizzare il traffico verso una pagina di destinazione desiderata.
* Identificate dove vanno i visitatori al posto delle pagine di obiettivi desiderate.

## Flusso server successivo {#concept_DB8C20E18AEA4051903C47A16C0E9C4E}

Visualizza i dati di navigazione tra i server del sito. Quando selezionate un nome server dal sito, il rapporto mostra il numero di visitatori che hanno navigato da tale server a ciascuno degli altri server del sito in un&#39;unica visita o tra più visite.

<!-- 

c_reports_next_server_flow.xml

 -->

Ad esempio, se disponi di dati specifici su server diversi o se hai dati con mirroring su server separati, il rapporto mostra il percorso tra i server colpiti dagli utenti. Questo vale anche per i domini all’interno del sito Web. Ad esempio, potete vedere quanti utenti sono passati da un `https://www.mysite.com` a `https://info.mysite.com` o `https://sales.mysite.com`.

## Flusso sezione successiva {#concept_7C9C8567E7DF477DA186E47DD3FD47A4}

Il [!UICONTROL Next Section Flow] rapporto è simile al [!UICONTROL Next Page Flow] rapporto. Visualizza i dati per le sezioni del sito (gruppi di pagine Web correlate). Se una pagina è contenuta in più sezioni del sito, il rapporto mostra i dati per tutte le sezioni del sito.

<!-- 

c_reports_next_section_flow.xml

 -->

Ad esempio, un rivenditore online potrebbe avere sezioni del sito per i propri prodotti e sezioni del sito per i marchi di prodotto. In questo caso, una pagina Web di un prodotto può trovarsi in più sezioni. Anche se una pagina di prodotto è stata visualizzata solo una volta, il [!UICONTROL Next Section Flow] rapporto mostra una visualizzazione di pagina per ciascuna sezione di vista associata alla pagina.

## Flusso pagina precedente {#concept_ADEAEBAE3F37401B977A27E03B5A523B}

Simile al [!UICONTROL Next Page Flow] rapporto. Il [!UICONTROL Previous Page Flow] rapporto mostra più livelli delle pagine più popolari visualizzate dai visitatori prima della pagina selezionata. Il rapporto evidenzia anche le pagine dalle quali i visitatori accedono al sito.

<!-- 

c_reports_previous_page_flow.xml

 -->

Utilizzate questo rapporto per:

* Scopri i passaggi più frequenti prima di visualizzare una pagina selezionata.
* Ottimizzate la progettazione del percorso del sito per indirizzare il traffico verso una pagina di destinazione desiderata.

## Flusso sezione precedente {#concept_30688D97B48449E1958866BAF376FA8C}

Il [!UICONTROL Previous Section Flow] rapporto è simile al [!UICONTROL Previous Page Flow] rapporto. Visualizza i dati per le sezioni del sito (gruppi di pagine Web correlate). Se una pagina è contenuta in più sezioni del sito, il rapporto mostra i dati per tutte le sezioni del sito.

<!-- 

c_reports_previous_section_flow.xml

 -->

Ad esempio, un rivenditore online potrebbe avere sezioni del sito per i propri prodotti e sezioni del sito per i marchi di prodotto. In questo caso, una pagina Web di un prodotto può trovarsi in più sezioni. Anche se una pagina di prodotto è stata visualizzata solo una volta, il [!UICONTROL Previous Section Flow] rapporto mostra una visualizzazione di pagina per ciascuna sezione di vista associata alla pagina.

## Flusso server precedente {#concept_8E43208CAF2C4C358F19D4669B73822F}

Questo rapporto mostra i dati di navigazione tra i server del sito. Quando selezionate un nome di server dal sito, il rapporto mostra il numero di visitatori che si sono spostati a tale server da ciascuno degli altri server del sito in un&#39;unica visita o tra più visite.

<!-- 

c_reports_previous_server_flow.xml

 -->

Ad esempio, se disponi di dati specifici su server diversi o se hai dati con mirroring su server separati, il rapporto mostra il percorso tra i server colpiti dagli utenti. Questo vale anche per i domini all’interno del sito Web. Ad esempio, potete vedere quanti utenti sono passati da un `www.mysite.com` a `info.mysite.com` o `sales.mysite.com`.

## Report funnel di conversione {#concept_35A2EB61E84441CBB670C2E02CA26F81}

I rapporti sul funnel di conversione mostrano le percentuali di conversione tra eventi di metrica specifici. È possibile utilizzare questo rapporto per comprendere il numero di click-through che generano vendite e il numero di unità vendute. Ad esempio, un [!UICONTROL Products Conversion] rapporto mostra la percentuale di eventi Carts relativi agli eventi Visits, quindi visualizza i totali per Ordini, Entrate e Unità in base a tali eventi.

<!-- 

c_reports_conversion_funnel.xml

 -->

Sono disponibili i seguenti rapporti funnel:

* [!UICONTROL Purchase Conversion Funnel]: Mostra visite (specifiche del rapporto), carrelli, ordini, unità e ricavi.
* [!UICONTROL Cart Conversion Funnel]: Visualizza visite (specifiche del rapporto), carrelli, Checkout, ordini e ricavi.
* [!UICONTROL Custom Event Funnel]: Visualizza gli eventi personalizzati sul sito. Per impostazione predefinita, vengono visualizzati gli eventi personalizzati da 1 a 5.
* [!UICONTROL Campaign Conversion Funnel]: Mostra Click-through, Checkout, Ordini e Entrate.

La tabella del rapporto mostra le statistiche relative alle vendite medie per click-through e alle unità medie vendute per click-through. A questi rapporti potete aggiungere metriche ed eventi personalizzati da altri gruppi di reporting. Questi funnel hanno molte somiglianze, ma si basano su variabili ed eventi diversi. Potete utilizzare questi rapporti per vedere quali percentuali e tendenze generali degli utenti attivano eventi specifici specificati. Potete vedere dove gli utenti non stanno seguendo gli eventi, il che fornisce indicazioni su quel punto specifico nel processo di conversione.

## Report Analisi sito {#concept_65694C6BDE424714B7975764F95497A4}

[!UICONTROL Site Analysis] mostra il modo in cui i visitatori si spostano tra le pagine e gli eventi specificati. Ad esempio, puoi vedere il flusso di traffico tra le pagine, l&#39;affinità tra i prodotti e i canali di marketing e il modo in cui le campagne e i canali confluiscono negli ordini dei prodotti. Puoi trascinare pagine, elementi dimensionali (ed elenchi) ed eventi delle metriche. Ogni cilindro rappresenta uno o più elementi dimensionali (pagine) o un evento. Le frecce rappresentano il flusso tra i valori del cilindro. Le metriche sono assegnate alle posizioni dei cilindri (X e Y), alla larghezza del cilindro, all’altezza del cilindro e al colore. La posizione, le dimensioni e il colore cambiano a seconda dei valori delle metriche.

<!-- 

c_reports_site_analysis.xml

 -->

Trascinate gli elementi dai riquadri degli strumenti per aggiungerli al grafico o al campo delle dimensioni.

Fare clic con il pulsante destro del mouse sui cilindri per modificarli o rimuoverli.

<!-- Meike, UICONTROL and DNL stripped from tables. Re-add. -->

| Opzione | Descrizione |
|--- |--- |
| Mostra analisi del sito in (visita o visitatore) | Consente di passare da Visita a Visitatore per analizzare il percorso dei visitatori. Queste impostazioni consentono di comprendere il coinvolgimento dei visitatori a livello di visitatore, tra più visite. I rapporti Analisi sito, Flusso e Abbandono sono abilitati per il percorso del visitatore. Modificando questa impostazione si riavvia il rapporto, vincolando i dati alla selezione. |
| Aggiungi punto di controllo | Visualizza l&#39;Editor punti di controllo, dal quale è possibile selezionare dimensioni o eventi da aggiungere allo schermo. |
| Sostituisci grafico | Sostituisce il grafico Analisi sito con i punti di controllo aggiunti all&#39;editor. |
| Adatta allo schermo | Ripristina la visualizzazione originale di un grafico. |
| Vista aerea | Fornisce una visualizzazione in discesa del grafico. |
| Attiva/disattiva griglia | Attiva o disattiva la griglia. |
| Dimensione | L&#39;elemento su cui si sta effettuando il reporting. Trascinate l’elemento dagli Dimension. |

| Opzione | Descrizione |
|--- |--- |
| Modificare | Consente di aggiungere o rimuovere pagine da un cilindro. |
| Rimuovi | Consente di rimuovere un cilindro. |
| Rapporti | Consente di avviare un altro rapporto dal cilindro. |
| Salva grafico con nome | Consente di salvare il grafico come .png o .jpg. Se modificate i controlli del grafico (angolo grafico, dimensioni) prima di salvare, le modifiche vengono mantenute nell’output. |
| Copia grafico negli Appunti | Copia il grafico da incollare in un’altra applicazione. Se modificate i controlli del grafico (angolo grafico, dimensioni) prima di salvare, le modifiche vengono mantenute nell’output. |
