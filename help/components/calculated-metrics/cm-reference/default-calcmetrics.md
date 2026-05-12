---
description: Adobe fornisce varie metriche calcolate che puoi utilizzare. In questa pagina sono elencate tali metriche e i loro utilizzi previsti.
title: Metriche calcolate predefinite
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
TQID: https://experienceleague.adobe.com/91Q7PzYSgj-Wam7DZhSAQ9rdm-I2HJK-qq2IZA0hy-M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 1be0f3577403db7cf9bd40ef9e7c4bfcfa6c0b17
workflow-type: tm+mt
source-wordcount: 779
ht-degree: 51%

---

# Metriche calcolate predefinite

Adobe Analytics fornisce varie metriche calcolate per coprire i casi d’uso più comuni. Queste metriche calcolate sono disponibili per impostazione predefinita in Analysis Workspace.

Di seguito è riportato un elenco di ogni metrica calcolata fornita da Adobe, con la relativa funzione prevista e la formula sottostante utilizzata per calcolarla:

>[!NOTE]
>
>Oltre alle metriche calcolate predefinite descritte in questa pagina, puoi anche aggiungere ulteriori metriche calcolate a una suite di rapporti.
>
>Puoi:
>
> * Aggiungere le metriche calcolate predefinite per i servizi multimediali in streaming, come descritto in [Metriche calcolate](https://experienceleague.adobe.com/en/docs/media-analytics/using/reporting/calculated-metrics)
> * Creare metriche calcolate personalizzate da metriche esistenti, come descritto in [Metriche calcolate e metriche calcolate avanzate](/help/components/calculated-metrics/cm-overview.md).
>

>[!TIP]
>
>Utilizza il [Dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) per esaminare in modo più approfondito la definizione di una metrica calcolata predefinita e i singoli componenti che la compongono.
>



| Nome della metrica calcolata | Funzione | Formula |
| --- | --- | --- |
| Clic sui collegamenti di acquisizione | Numero di volte in cui le persone fanno clic su un collegamento progettato per incrementare il traffico al sito. | `[Campaign Click-throughs]` |
| Azioni | Numero totale di azioni eseguite nell&#39;app | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| Utenti dell’app | Numero totale di utenti di un’app mobile | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Durata media delle sessioni (dispositivi mobili) | Tempo medio trascorso dai visitatori sul sito durante una singola sessione. | Vuoto |
| Tempo medio sul sito | Il tempo medio trascorso da un visitatore sul sito prima di partire o di allontanarsi. | `[Average Time Spent on Site (Seconds)]` |
| Percentuale di rimbalzi | Il rapporto tra le visite che contenevano esattamente un hit e il numero di visite su quella pagina. Questa metrica può aiutarti a capire quali elementi dimensionali hanno il tasso di mancato recapito più alto o a vedere un tasso di mancato recapito totale aggregato del tuo sito nel tempo. | `[Bounces] / [Entries]` |
| Percentuale visualizzazioni pagina bot | Il rapporto tra le visualizzazioni di pagina dei bot e il numero totale di visualizzazioni di pagina. | `[Bot Page Views] / [Page Views]` |
| Velocità dei contenuti | La velocità con cui vengono creati e pubblicati nuovi contenuti sul sito e la rapidità con cui generano il coinvolgimento degli utenti. | `[Page Views] / [Visits]` |
| Tasso di conversione | Percentuale di visitatori che hanno eseguito un’azione desiderata, ad esempio un acquisto. | `[Orders] / [Visits]` |
| Tasso di ingresso | Percentuale di visitatori che sono entrati nel sito da una determinata pagina, rispetto al numero totale di sessioni sul sito. | `[Entries] / [Visits]` |
| Visitatori univoci stimati (ITP 2.1) | Per i visitatori ITP (utenti nei browser Safari), dividi Visitatori univoci per 2 o meno. Questa metrica calcolata presuppone che tu sia impostato su cookie utilizzando JavaScript lato client (non utilizzando un’implementazione CNAME). Le implementazioni che impostavano i cookie utilizzando JavaScript lato client erano interessate a partire da ITP 2.1. Per ulteriori informazioni, consulta [Intelligent tracking prevent](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Copertura ID Experience Cloud | Percentuale di visitatori che hanno un ID Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Tasso di uscita | Percentuale di visitatori che abbandonano il sito dopo aver visualizzato una determinata pagina. | `[Exits] / [Visits]` |
| Visitatori univoci ITP 2.1 / Visitatori univoci | La percentuale di visitatori univoci che utilizzano un browser soggetta alle limitazioni dei cookie ITP 2.1. | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| Assistenza ordini | Numero di volte in cui un canale o un’origine ha contribuito al percorso di acquisto di un cliente, senza però portare all’acquisto finale. | `[Orders (Visit Participation)] - [Orders]` |
| Ordini / Visite | Percentuale di visite al sito che comportano una transazione completata. | `[Orders] / [Visits]` |
| Ordini / Visitatore | Numero medio di ordini o transazioni generati da ogni singolo visitatore del sito | `[Orders] / [Unique Visitors]` |
| Visualizzazioni pagina / Visitatori univoci stimati (ITP 2.1) | Numero medio di pagine visualizzate per visitatori univoci stimati (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Visualizzazioni di pagina / Visitatori univoci | Numero medio di pagine visualizzate da ogni visitatore univoco del sito. | `[Page Views] / [Unique Visitors]` |
| Visualizzazioni/visite pagina | Numero medio di pagine visualizzate da un utente durante una singola visita al sito. | `[Page Views] / [Visits]` |
| Velocità della pagina | Il numero di visualizzazioni di pagina aggiuntive generate da un contenuto. Questa metrica può essere utile per determinare quali contenuti determinano un coinvolgimento aggiuntivo. | `[Page Views] / [Visits]` |
| Ricaricamenti / Visualizzazioni pagina | Percentuale di visualizzazioni pagina che hanno comportato un ricaricamento o un aggiornamento della pagina. | `[Reloads] / [Page Views]` |
| Entrate / Ordine | Importo medio delle entrate generate da ogni transazione o ordine completato sul sito. | `[Revenue] / [Orders]` |
| Entrate / Visite | Importo medio delle entrate generate da una singola visita al sito. | `[Revenue] / [Visits]` |
| Entrate / Visitatore | Importo medio delle entrate generate da ogni singolo visitatore del sito. | `[Revenue] / [Unique Visitors]` |
| Visualizzazioni stato | Numero di visualizzazioni ai diversi stati o schermate dell’app | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| Tempo trascorso/Utente (stato) | Il periodo di tempo che il visitatore medio trascorre in un particolare stato mentre è sul sito | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Visitatori univoci / Visitatori univoci che ritornano dopo 7 giorni | Percentuale di visitatori univoci che ritornano dopo un periodo di almeno 7 giorni. | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| Utenti (dispositivi mobili) | Numero totale di utenti di un’app mobile | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Visite / Visitatori | Numero medio di visite che un visitatore univoco effettua sul sito. | `[Visits] / [Unique Visitors]` |
| Tasso di rimbalzi ponderato | Funzione | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
