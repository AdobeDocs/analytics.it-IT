---
description: Adobe fornisce varie metriche calcolate che puoi utilizzare. In questa pagina sono elencate tali metriche e i loro utilizzi previsti.
title: Funzioni di base di riferimento
feature: Calculated Metrics
exl-id: 1a49435c-96d1-4617-bd1a-a5d3b74e3ebd
source-git-commit: 2874ea66765e650a92bc39537d6a9eb8cebcd6a4
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 7%

---

# Metriche calcolate predefinite

Adobe Analytics fornisce diverse metriche calcolate per coprire i casi d’uso più comuni. Queste metriche calcolate sono disponibili per impostazione predefinita in Analysis Workspace.

Di seguito è riportato un elenco di ogni metrica calcolata fornita da Adobe, con la relativa funzione prevista e la formula sottostante utilizzata per calcolarla:

>[!NOTE]
>
>Oltre alle metriche calcolate predefinite descritte in questa pagina, puoi anche aggiungere ulteriori metriche calcolate a una suite di rapporti.
>
>È possibile:
> * Aggiungere metriche calcolate predefinite per Streaming Media, come descritto in [Metriche calcolate](/https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Creare metriche calcolate personalizzate dalle metriche esistenti, come descritto in [Metriche calcolate e metriche calcolate avanzate (derivate)](/help/components/c-calcmetrics/cm-overview.md).



| Nome della metrica calcolata | Funzione | Formula |
|---------|----------|---------|
| Percentuale non recapitate | Il rapporto tra le visite che contenevano esattamente un hit e il numero di visite su quella pagina. Questo può aiutarti a capire quali elementi dimensionali hanno il tasso di mancato recapito più alto o a vedere un tasso di mancato recapito totale aggregato del tuo sito nel tempo. | Percentuale non recapitate |
| Ricavi / Visitatore | L’importo medio dei ricavi generati da ogni singolo visitatore del sito. | <p>Ricavi</p><p>/</p><p>Visitatori univoci</p> |
| Ordini / Visitatore | Numero medio di ordini o transazioni generati da ogni singolo visitatore del sito | <p>Ordini predefiniti</p><p>/</p><p>Visitatore</p> |
| Ricavi/visite | L’importo medio dei ricavi generati da una singola visita al sito. | <p>Ricavi</p><p>/</p><p>Visite univoche</p> |
| Ricavi/Ordine | L&#39;importo medio dei ricavi generati da ogni transazione o ordine completato sul sito. | <p>Ricavi</p><p>/</p><p>Ordine</p> |
| Ordini/Visite | Percentuale di visite al sito che risultano in una transazione completata. | <p>Ordine</p><p>/</p><p>Visite</p> |
| Visualizzazioni pagina/Visite | Il numero medio di pagine visualizzate da un utente durante una singola visita al sito. | <p>Visualizzazioni pagina</p><p>/</p><p>Visite</p> |
| Visite/Visitatore | Il numero medio di visite effettuate da un visitatore univoco al sito. | <p>Visite</p><p>/</p><p>Visitatori univoci</p> |
| Ricarica/Visualizzazioni pagina | Percentuale di visualizzazioni di pagina che hanno portato a un ricaricamento o aggiornamento della pagina. | <p>Ricariche</p><p>/</p><p>Visualizzazioni pagina</p> |
| Percentuale rimbalzo ponderato | Funzione | if(visite>percentile(visite),bouncerate,0) |
| Ordina assistenze | Il numero di volte in cui un canale o un’origine ha contribuito al percorso di un cliente per effettuare un acquisto, ma non ha prodotto l’acquisto finale. | <p>Ordini (partecipazione\|visita)</p><p>-</p><p>Ordini</p> |
| Frequenza di uscita | La percentuale di visitatori che abbandonano il sito dopo aver visualizzato una pagina particolare. | <p>Uscite</p><p>/</p><p>Visite</p> |
| Tasso di ingresso | La percentuale di visitatori che sono entrati nel sito in una determinata pagina rispetto al numero totale di sessioni sul sito. | <p>Voci</p><p>/</p><p>Visite</p> |
| Tempo medio sul sito | Il tempo medio trascorso da un visitatore sul sito prima di partire o di allontanarsi. | Tempo medio trascorso sul sito (secondi) |
| Tempo trascorso/utente (stato) | Il periodo di tempo che il visitatore medio trascorre in un particolare stato mentre è sul sito | Metrica Tempo trascorso per visitatore (secondi) + segmento app mobile |
| Utenti (dispositivi mobili) | Numero totale di utenti di un’app mobile | Metrica Visitatori univoci + segmento Utenti app mobili |
| Utenti dell’app | Numero totale di utenti di un’app mobile | Metrica Visitatori univoci + segmento app mobile |
| Visualizzazioni stato | Numero di visualizzazioni ai diversi stati o schermate dell’app | Metrica Visualizzazioni pagina + Segmento app mobile |
| Azioni | Numero totale di azioni eseguite nell&#39;app | Metrica Istanze di collegamento personalizzate + Ha un segmento Azione |
| Clic sui collegamenti di acquisizione | Il numero di volte in cui le persone fanno clic su un collegamento progettato per indirizzare il traffico verso il sito. | Metrica dei click-through di Campaign |
| Velocità pagina | Il numero di visualizzazioni di pagina aggiuntive generate da un contenuto. Questo può aiutarti a determinare quali contenuti favoriscono un coinvolgimento aggiuntivo. | <p>Visualizzazioni pagina</p><p>/</p><p>Visite</p> |
| Tasso di conversione | Percentuale di visitatori che hanno intrapreso un’azione desiderata, ad esempio un acquisto. | <p>Ordini</p><p>/</p><p>Visite</p> |
| Lunghezza media sessione (mobile) | La quantità media di tempo che i visitatori trascorrono sul sito durante una singola sessione. | Vuoto |
| Copertura ID Experience Cloud | La percentuale di visitatori che hanno un ID Experience Cloud. | <p>Visitatori con Experience Cloud ID</p><p>/</p><p>Visitatori univoci</p> |
| Velocity contenuto | La velocità con cui i nuovi contenuti vengono creati e pubblicati sul sito e la velocità con cui generano coinvolgimento degli utenti. | <p>Visualizzazioni pagina</p><p>/</p><p>Visite</p> |
| ITP 2.1 Visitatori univoci / Visitatori univoci | La percentuale di visitatori univoci che utilizzano un browser soggetta alle limitazioni dei cookie ITP 2.1. In altre parole, i clienti che non utilizzano un’implementazione CNAME. Questo vale per i clienti che impostano i cookie tramite JavaScript lato client. | <p>Metrica Visitatori univoci + segmento Visitatori ITP</p><p>/</p><p>Visitatori univoci</p> |
| Visitatori univoci/Visitatori univoci che ritornano dopo 7 giorni | La percentuale di visitatori univoci che ritornano dopo un periodo di 7 o più giorni. | <p>Metrica Visitatori univoci + Utenti che ritornano dopo il segmento 7 giorni</p><p>/</p><p>Visitatori univoci</p> |
| Visualizzazioni pagina/Visitatore univoco | Il numero medio di pagine visualizzate per ogni visitatore univoco del sito. | <p>Visualizzazioni pagina</p><p>/</p><p>Visitatori univoci</p> |
| Visite / Visitatori | Il numero medio di visite effettuate da un visitatore univoco al sito. | <p>Visite</p><p>/</p><p>Visitatori univoci</p> |
| Visitatori univoci stimati (ITP 2.1) | <p>Per i visitatori ITP (utenti nei browser Safari), dividi Visitatori univoci per 2 o meno.</p><p>Ciò presuppone che tu stia impostando i cookie utilizzando JavaScript lato client (non utilizzando un’implementazione CNAME). Le implementazioni che impostavano i cookie utilizzando JavaScript lato client erano interessate a partire da ITP 2.1. Consulta: [https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)</p> | <p>Metrica Visitatori univoci + Segmento Visitatori ITP (implementazioni ITP 2.1 e non CNAME)</p><p>/</p><p>Metrica Visitatori univoci + Segmento Visitatori non ITP (implementazioni ITP 2.1 e non CNAME)</p> |
| Visualizzazioni di pagina/Visitatori univoci stimati (ITP 2.1) | Il numero medio di pagine visualizzate per Visitatori univoci stimati (ITP 2.1). | <p>Metrica Visitatori univoci + Segmento Visitatori ITP (implementazioni ITP 2.1 e non CNAME)</p><p>/</p><p>Metrica Visitatori univoci + Segmento Visitatori non ITP (implementazioni ITP 2.1 e non CNAME)</p> |

{style="table-layout:auto"}
