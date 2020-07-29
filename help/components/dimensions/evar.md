---
title: eVar
description: Una dimensione personalizzata che potete utilizzare nel reporting.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 0%

---


# eVar

*Questa pagina della guida descrive il funzionamento delle eVar come una dimensione. Per informazioni su come implementare le eVar, vedi[eVar](/help/implement/vars/page-vars/evar.md)nella guida per l&#39;utente Implementa.*

Le eVar sono variabili personalizzate che potete utilizzare come desiderate. Se si dispone di un documento [di progettazione di una](/help/implement/prepare/solution-design.md)soluzione, la maggior parte delle dimensioni specifiche per l&#39;organizzazione vengono visualizzate come eVar. Per impostazione predefinita, le eVar persistono oltre l’hit impostato. Puoi personalizzarne la scadenza e l’allocazione nelle variabili [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione nelle impostazioni della suite di rapporti.

Il numero di eVar disponibili dipende dal contratto con  Adobe. Sono disponibili fino a 250 eVar se il contratto con  Adobe lo supporta.

Le eVar non fanno distinzione tra maiuscole e minuscole. Se inviate lo stesso valore in casi diversi (ad esempio `"DOG"` e `"Dog"`),  Analysis Workspace li raggruppa nello stesso elemento dimensione. Viene utilizzato il caso del primo valore visualizzato all&#39;inizio del mese di segnalazione. Data warehouse mostra il primo valore rilevato durante il periodo di richiesta.

## Compilazione di eVar con i dati

Ogni eVar  raccoglie i dati dalla stringa [`v1` - `v250` query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il parametro della stringa di `v1` query raccoglie i dati per  eVar1, mentre il parametro della stringa di `v222` query raccoglie i dati per  eVar222.

AppMeasurement, che compila le variabili JavaScript in una richiesta di immagine per la raccolta dei dati, utilizza le variabili `eVar1` - `eVar250`. Consulta [eVar](/help/implement/vars/page-vars/evar.md) nella guida per l&#39;implementazione.

## Elementi Dimension

Poiché le eVar contengono stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensione per ciascun eVar . Accertatevi di registrare lo scopo di ogni elemento di dimensione  e tipico in un documento [di progettazione di una](/help/implement/prepare/solution-design.md)soluzione.

## Funzionamento delle eVar

Quando si inviano dati ad  Adobe Analytics, i server di raccolta dati traducono l&#39;hit in una singola riga di dati con centinaia di colonne. Due colonne sono dedicate a ciascun eVar ; uno per la raccolta diretta dei dati e l&#39;altro per i valori persistenti.

* Una colonna standard contiene i dati inviati al Adobe  dalla richiesta di immagine.
* Una colonna &quot;post&quot; contiene dati persistenti, che dipendono dalla scadenza e dall&#39;allocazione del eVar .

In quasi tutte le circostanze, la `post_evar` colonna viene utilizzata nei report.

### Collegamento delle eVar alle metriche

Gli eventi di successo e le eVar vengono spesso definiti in diverse richieste di immagini. La `post_evar` colonna consente  valori di eVar per collegarsi agli eventi, mostrando i dati nel reporting. Ad esempio, visita:

1. Un visitatore arriva sul sito nella pagina principale.
2. Cercano &quot;gatti&quot; utilizzando la ricerca interna del tuo sito. La tua implementazione utilizza  eVar1 per la ricerca interna.
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
* La `evar` colonna determina gli hit quando  eVar 1 è stato impostato in modo esplicito.
* Il `post_evar1` valore precedente dipende dall&#39;allocazione e dalla scadenza della variabile nelle impostazioni della suite di rapporti.
* La `event_list` colonna contiene tutti i dati delle metriche. Ad esempio, `event1` è &#39;Searches&#39;, e gli altri eventi sono metriche standard del carrello. Nei dati non elaborati, `event_list` contiene un set di numeri delimitati da virgole con una tabella di ricerca che associa tali numeri a una metrica.

### Conversione della raccolta dati in reporting

Gli strumenti in  Adobe Analytics, come  Analysis Workspace, funzionano con questi dati raccolti. Ad esempio, se hai estratto un rapporto utilizzando 1 come dimensione e Ordini come metrica, visualizzerai un rapporto simile al seguente:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

 Analysis Workspace estrae questo rapporto utilizzando la seguente logica:

* Osserva tutti `event_list` i valori e scopri tutti gli hit con `purchase` essi.
* Tra questi hit, visualizza il `post_evar1` valore.

### L&#39;importanza dell&#39;allocazione e della scadenza

Poiché l&#39;allocazione e la scadenza determinano quali valori persistono, sono essenziali per ottenere il massimo valore da un&#39;implementazione di analisi.  Adobe consiglia vivamente di discutere all&#39;interno dell&#39;organizzazione come vengono gestiti più valori per ciascun eVar  (allocazione) e quando le eVar interrompono i dati persistenti (scadenza).

* Per impostazione predefinita, un eVar  utilizza l&#39;ultima allocazione. I nuovi valori sovrascrivono i valori persistenti.
* Per impostazione predefinita, un eVar  utilizza una scadenza della visita. Al termine di una visita, i valori cessano di essere copiati da una riga all’altra nella `post_evar` colonna.

Puoi modificare &#39;allocazione e la scadenza del eVar in Variabili [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione nelle impostazioni della suite di rapporti.

## Valore delle eVar sulle proprietà

 Adobe consiglia di utilizzare le eVar nella maggior parte dei casi, supportate tramite quanto segue:

* Le eVar hanno un limite di 255 byte nei report. Le proprietà hanno un limite di 100 byte.
* Per impostazione predefinita, le proprietà non persistono oltre l’hit impostato. Le eVar hanno una scadenza personalizzata, che consente di determinare quando un eVar  non riceve più credito per un evento successivo. Tuttavia, se utilizzate l&#39;elaborazione [del tempo del](/help/components/vrs/vrs-report-time-processing.md)rapporto, sia le prop che le eVar possono utilizzare un modello di attribuzione personalizzato.
*  Adobe supporta fino a 250 eVar e solo 75 prop.

Consultate [prop](prop.md) per ulteriori confronti tra prop ed eVar.
