---
title: eVar per Dimension
description: Una dimensione personalizzata utilizzabile nel reporting.
feature: Dimensions
exl-id: ce7cc999-281d-4c52-b64d-d44cc320ab2d
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 4%

---

# eVar

*Questa pagina di aiuto descrive il funzionamento delle eVar come una dimensione. Per informazioni su come implementare le eVar, vedi [eVar](/help/implement/vars/page-vars/evar.md) nella guida utente Implementa .*

Le eVar sono variabili personalizzate che puoi utilizzare come desideri. Se hai [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), la maggior parte delle dimensioni specifiche della tua organizzazione si conclude come [!UICONTROL eVars]. Per impostazione predefinita, le eVar persistono oltre l’hit su cui sono impostate. Puoi personalizzarne la scadenza e l’allocazione in [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in [!UICONTROL Report suite settings].

Il numero di eVar disponibili dipende dal contratto con l’Adobe. Sono disponibili fino a 250 eVar se il contratto con Adobe lo supporta.

Il caso (superiore o inferiore) utilizzato nel reporting si basa sul primo valore registrato dal sistema backend. Questo valore potrebbe essere la prima istanza mai vista o variare su base temporale (ad esempio, mensile), a seconda della varietà e della quantità di dati associati alla suite di rapporti.

## Popolare eVar con i dati

Ogni eVar raccoglie dati dal [`v1` - `v250` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il `v1` il parametro della stringa di query raccoglie i dati per eVar1, mentre il `v222` il parametro della stringa query raccoglie i dati per eVar222.

AppMeasurement, che compila variabili JavaScript in una richiesta di immagine per la raccolta dei dati, utilizza le variabili `eVar1` - `eVar250`. Vedi [eVar](/help/implement/vars/page-vars/evar.md) nella guida utente Implementa per le linee guida di implementazione.

## Elementi Dimension

Poiché le eVar contengono stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensionali per ogni eVar. Assicurati di registrare lo scopo di ogni elemento dimensionale eVar e tipico in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).

## Funzionamento delle eVar

Quando invii dati ad Adobe Analytics, i server di raccolta dati traducono l’hit in una singola riga di dati con centinaia di colonne. Due colonne sono dedicate a ciascun eVar; uno per la raccolta diretta dei dati e l&#39;altro per i valori persistenti.

* Una colonna standard contiene i dati inviati ad Adobe dalla richiesta di immagine.
* Una colonna &quot;post&quot; contiene dati persistenti che dipendono dalla scadenza e dall’allocazione di eVar.

In quasi tutte le circostanze, il `post_evar` viene utilizzata nei rapporti.

### Collegamento delle eVar alle metriche

Gli eventi di successo e le eVar sono spesso definiti in richieste di immagini diverse. La `post_evar` Questa colonna consente ai valori di eVar di collegarsi agli eventi, mostrando i dati nel reporting. Ad esempio, visita:

1. Un visitatore arriva al tuo sito sulla tua home page.
2. Cercano &quot;gatti&quot; utilizzando la ricerca interna del tuo sito. L’implementazione utilizza eVar1 per la ricerca interna.
3. Visualizzano un prodotto e procedono attraverso il processo di pagamento.

Una versione semplificata dei dati non elaborati sarà simile alla seguente:

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* La `visitor_id` collega gli hit allo stesso visitatore. Nei dati non elaborati effettivi, i valori concatenati di `visid_high` e `visid_low` determina l&#39;ID visitatore.
* La `pagename` popola la dimensione Pagine.
* La `evar` La colonna determina gli hit quando eVar1 è stato impostato in modo esplicito.
* La `post_evar1` trasporta il valore precedente, a seconda dell’allocazione e della scadenza della variabile nelle impostazioni della suite di rapporti.
* La `event_list` contiene tutti i dati della metrica. Per questo esempio: `event1` è &quot;Ricerche&quot; e gli altri eventi sono metriche standard del carrello acquisti. In dati grezzi reali, `event_list` contiene un set di numeri delimitato da virgole con una tabella di ricerca che associa tali numeri a una metrica.

### Traduzione della raccolta dati nel reporting

Gli strumenti di Adobe Analytics, come Analysis Workspace, utilizzano questi dati raccolti. Ad esempio, se hai estratto un rapporto utilizzando eVar1 come dimensione e Ordini come metrica, visualizzerai un rapporto simile al seguente:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace richiama questo rapporto utilizzando la logica seguente:

* Osserva tutto `event_list` e scegliere tutti gli hit con `purchase` in loro.
* Tra questi risultati, visualizza il `post_evar1` valore.

### L&#39;importanza dell&#39;allocazione e della scadenza

Poiché l’allocazione e la scadenza determinano quali valori persistono, sono fondamentali per ottenere il massimo valore da un’implementazione di Analytics. Adobe consiglia vivamente di discutere all&#39;interno dell&#39;organizzazione come vengono gestiti (allocazione) più valori per ogni eVar e quando le eVar smettono di mantenere i dati (scadenza).

* Per impostazione predefinita, un eVar utilizza l’ultima allocazione. I nuovi valori sovrascrivono quelli persistenti.
* Per impostazione predefinita, un eVar utilizza una scadenza della visita. Al termine di una visita, i valori smettono di copiarsi da una riga all’altra `post_evar` colonna.

Puoi modificare l’allocazione e la scadenza di eVar in [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) nelle impostazioni della suite di rapporti.

## Valore delle eVar rispetto alle proprietà

Nella maggior parte dei casi, Adobe consiglia di utilizzare eVar, con il supporto seguente:

* Le eVar hanno un limite di 255 byte nei rapporti. Le proprietà hanno un limite di 100 byte.
* Le proprietà per impostazione predefinita non persistono oltre l’hit impostato. Le eVar hanno una scadenza personalizzata che ti consente di determinare quando un eVar non ottiene più credito per un evento successivo. Tuttavia, se utilizzi [elaborazione dei tempi di report](/help/components/vrs/vrs-report-time-processing.md), sia prop che eVar possono utilizzare un modello di attribuzione personalizzato.
* Adobe supporta fino a 250 eVar e solo 75 proprietà.

Vedi [prop](prop.md) per ulteriori confronti tra prop ed eVar.
