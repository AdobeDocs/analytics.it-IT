---
title: eVar
description: Una dimensione personalizzata che potete utilizzare nel reporting.
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---


# eVar

*Questa pagina della guida descrive il funzionamento delle eVar come una dimensione. Per informazioni su come implementare le eVar, vedi[eVar](/help/implement/vars/page-vars/evar.md)nella guida per l&#39;utente Implementa.*

Le eVar sono variabili personalizzate che potete utilizzare come desiderate. Se si dispone di un documento [di progettazione di una](/help/implement/prepare/solution-design.md)soluzione, la maggior parte delle dimensioni specifiche per l&#39;organizzazione vengono visualizzate come eVar. Per impostazione predefinita, le eVar persistono oltre l’hit impostato. Puoi personalizzarne la scadenza e l’allocazione nelle variabili [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione nelle impostazioni della suite di rapporti.

Il numero di eVar disponibili dipende dal contratto con Adobe. Se il contratto con Adobe lo supporta, sono disponibili fino a 250 eVar.

## Compilazione di eVar con i dati

Ogni eVar raccoglie i dati dalla [`v1` - `v250` stringa](/help/implement/validate/query-parameters.md) di query nelle richieste di immagini. Ad esempio, il parametro della stringa di `v1` query raccoglie i dati per eVar1, mentre il parametro della stringa di `v222` query raccoglie i dati per eVar222.

AppMeasurement, che compila le variabili JavaScript in una richiesta di immagine per la raccolta dei dati, utilizza le variabili `eVar1` - `eVar250`. Consulta [eVar](/help/implement/vars/page-vars/evar.md) nella guida per l’utente Implementa per le linee guida di implementazione.

## Valori dimensione

Poiché le eVar contengono stringhe personalizzate nell&#39;implementazione, l&#39;organizzazione determina i valori di dimensione per ogni eVar. Accertatevi di registrare lo scopo di ogni eVar e i valori dimensionali tipici in un documento [di progettazione della](/help/implement/prepare/solution-design.md)soluzione.

## Funzionamento delle eVar

Quando invii dati ad Adobe Analytics, i server di raccolta dati traducono l’hit in una singola riga di dati con centinaia di colonne. A ciascuna eVar sono dedicate due colonne; uno per la raccolta diretta dei dati e l&#39;altro per i valori persistenti.

* Una colonna standard contiene i dati inviati ad Adobe dalla richiesta di immagini.
* Una colonna &quot;post&quot; contiene dati persistenti, che dipendono dalla scadenza e dall&#39;allocazione dell&#39;eVar.

In quasi tutte le circostanze, la `post_evar` colonna viene utilizzata nei report.

### Collegamento delle eVar alle metriche

Gli eventi di successo e le eVar vengono spesso definiti in diverse richieste di immagini. La `post_evar` colonna consente ai valori eVar di collegarsi agli eventi, mostrando i dati nel reporting. Ad esempio, visita:

1. Un visitatore arriva sul sito nella pagina principale.
2. Cercano &quot;gatti&quot; utilizzando la ricerca interna del tuo sito. La tua implementazione utilizza eVar1 per la ricerca interna.
3. Visualizzano un prodotto e procedono attraverso il processo di estrazione.

Una versione semplificata dei dati non elaborati sarà simile a quella riportata di seguito:

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* La `visitor_id` colonna associa gli hit allo stesso visitatore. Nei dati non elaborati, i valori concatenati di `visid_high` e determinano `visid_low` l’ID visitatore.
* La `pagename` colonna compila la dimensione Pagine.
* La `evar` colonna determina gli hit quando eVar1 è stato impostato in modo esplicito.
* Il `post_evar1` valore precedente dipende dall&#39;allocazione e dalla scadenza della variabile nelle impostazioni della suite di rapporti.
* La `event_list` colonna contiene tutti i dati delle metriche. Ad esempio, `event1` è &#39;Searches&#39;, e gli altri eventi sono metriche standard del carrello. Nei dati non elaborati, `event_list` contiene un set di numeri delimitati da virgole con una tabella di ricerca che associa tali numeri a una metrica.

### Conversione della raccolta dati in reporting

Gli strumenti di Adobe Analytics, come Analysis Workspace, consentono di estrarre i dati raccolti. Ad esempio, se hai estratto un rapporto utilizzando eVar1 come dimensione e Ordini come metrica, visualizzerai un rapporto simile al seguente:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace estrae questo rapporto utilizzando la seguente logica:

* Osserva tutti `event_list` i valori e scopri tutti gli hit con `purchase` essi.
* Tra questi hit, visualizza il `post_evar1` valore.

### L&#39;importanza dell&#39;allocazione e della scadenza

Poiché l&#39;allocazione e la scadenza determinano quali valori persistono, sono essenziali per ottenere il massimo valore da un&#39;implementazione di analisi. Adobe consiglia vivamente di discutere all&#39;interno dell&#39;organizzazione di come vengono gestiti più valori per ciascuna eVar (allocazione) e quando le eVar interrompono i dati persistenti (scadenza).

* Per impostazione predefinita, una eVar utilizza l&#39;ultima allocazione. I nuovi valori sovrascrivono i valori persistenti.
* Per impostazione predefinita, una eVar utilizza una scadenza della visita. Al termine di una visita, i valori cessano di essere copiati da una riga all’altra nella `post_evar` colonna.

Puoi modificare l&#39;allocazione e la scadenza dell&#39;eVar in Variabili [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione nelle impostazioni della suite di rapporti.

## Valore delle eVar sulle proprietà

Nella maggior parte dei casi, Adobe consiglia di utilizzare le eVar, supportate tramite le seguenti operazioni:

* Le eVar hanno un limite di 255 byte nei report. Le proprietà hanno un limite di 100 byte.
* Per impostazione predefinita, le proprietà non persistono oltre l’hit impostato. Le eVar hanno una scadenza personalizzata, che consente di determinare quando un&#39;eVar non ottiene più credito per un evento successivo. Tuttavia, se utilizzate l&#39;elaborazione [del tempo del](/help/components/vrs/vrs-report-time-processing.md)rapporto, sia le prop che le eVar possono utilizzare un modello di attribuzione personalizzato.
* Adobe supporta fino a 250 eVar e solo 75 prop.

Consultate [prop](prop.md) per ulteriori confronti tra prop ed eVar.
