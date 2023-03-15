---
title: eVar (dimensione)
description: Una dimensione personalizzata che puoi utilizzare nel reporting.
feature: Dimensions
exl-id: ce7cc999-281d-4c52-b64d-d44cc320ab2d
source-git-commit: 68389772dec0420a66767bb0af9dea3122e1cb0f
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 13%

---

# eVar 

*Questa pagina della guida descrive il funzionamento delle eVar come dimensione. Per informazioni su come implementare le eVar, consulta [eVar](/help/implement/vars/page-vars/evar.md) nella guida utente Implementa.*

Le eVar sono variabili personalizzate che puoi utilizzare come desideri. Se si dispone di [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), la maggior parte delle dimensioni specifiche dell’organizzazione finiscono per essere [!UICONTROL eVars]. Per impostazione predefinita, le eVar persistono oltre l’hit su cui sono impostate. Puoi personalizzarne la scadenza e l’allocazione in [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) in [!UICONTROL Report suite settings].

Il numero di eVar disponibili dipende dal contratto con Adobe. Se il contratto con Adobe lo supporta, sono disponibili fino a 250 eVar.

La maiuscola o minuscola utilizzata nei rapporti si basa sul primo valore registrato dal sistema backend. Questo valore potrebbe essere la prima istanza mai vista o variare su base temporale (ad esempio, mensile), a seconda della varietà e della quantità di dati associati alla suite di rapporti.

## Popolare le eVar con i dati

Ogni eVar raccoglie dati dalla [`v1` - `v250` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il `v1` parametro stringa query raccoglie dati per eVar1, mentre il parametro `v222` il parametro della stringa di query raccoglie i dati per eVar222.

AppMeasurement, che compila variabili JavaScript in una richiesta di immagine per la raccolta dati, utilizza le variabili `eVar1` - `eVar250`. Consulta [eVar](/help/implement/vars/page-vars/evar.md) nella Guida utente di implementazione per le linee guida sull’implementazione.

## Elementi dimensionali

Poiché le eVar contengono stringhe personalizzate nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali per ogni eVar. Assicurati di registrare lo scopo di ogni elemento dimensionale eVar e tipico in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).

## Funzionamento delle eVar

Quando invii dati ad Adobe Analytics, i server di raccolta dati traducono l’hit in un’unica riga di dati con centinaia di colonne. A ogni eVar sono dedicate due colonne, una per la raccolta diretta dei dati e l’altra per i valori persistenti.

* Una colonna standard contiene i dati inviati all’Adobe dalla richiesta di immagine.
* Una colonna &quot;post&quot; contiene dati persistenti, che dipendono dalla scadenza e dall’allocazione dell’eVar.

In quasi tutte le circostanze, il `post_evar` Nei rapporti viene utilizzata la colonna.

### Come le eVar si legano alle metriche

Gli eventi di successo e le eVar sono spesso definiti in diverse richieste di immagini. Il `post_evar` consente ai valori eVar di collegarsi agli eventi, mostrando i dati nel reporting. Effettua la seguente visita ad esempio:

1. Un visitatore arriva al tuo sito sulla tua home page.
2. Cercano &quot;gatti&quot; usando la ricerca interna del tuo sito. La tua implementazione utilizza eVar1 per le ricerche interne.
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

* Il `visitor_id` la colonna collega gli hit allo stesso visitatore. Nei dati non elaborati effettivi, i valori concatenati di `visid_high` e `visid_low` determina l’ID visitatore.
* Il `pagename` compila la dimensione Pagine.
* Il `evar` determina gli hit quando eVar1 è stato impostato esplicitamente.
* Il `post_evar1` riporta il valore precedente, a seconda dell’allocazione e della scadenza della variabile in impostazioni della suite di rapporti.
* Il `event_list` contiene tutti i dati delle metriche. Per questo esempio, `event1` è &quot;Searches&quot; (Ricerche), mentre gli altri eventi sono metriche standard del carrello. Nei dati non elaborati effettivi, `event_list` contiene un set di numeri delimitato da virgole con una tabella di ricerca che lega tali numeri a una metrica.

### Traduzione della raccolta dati nel reporting

Gli strumenti di Adobe Analytics, come Analysis Workspace, utilizzano questi dati raccolti. Ad esempio, se hai estratto un rapporto utilizzando eVar1 come dimensione e Ordini come metrica, visualizzerai un rapporto simile al seguente:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace estrae questo rapporto utilizzando la seguente logica:

* Cerca in tutto `event_list` e preleva tutti gli hit con `purchase` in essi.
* Di questi risultati, visualizza `post_evar1` valore.

### Importanza dell&#39;assegnazione e della scadenza

Poiché l’allocazione e la scadenza determinano quali valori persistono, sono vitali per ottenere il massimo valore da un’implementazione di Analytics. Adobe consiglia vivamente di discutere all’interno dell’organizzazione come vengono gestiti più valori per ogni eVar (allocazione) e quando le eVar cessano di mantenere i dati persistenti (scadenza).

* Per impostazione predefinita, un eVar utilizza l’ultima allocazione. I nuovi valori sovrascrivono quelli persistenti.
* Per impostazione predefinita, un eVar utilizza una scadenza di visita. Al termine di una visita, i valori non vengono più copiati di riga in riga nella sezione `post_evar` colonna.

Puoi modificare l’allocazione e la scadenza di eVar in [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) nelle impostazioni della suite di rapporti.

## Valore delle eVar rispetto alle proprietà

L’Adobe consiglia di utilizzare le eVar nella maggior parte dei casi, supportate tramite i seguenti elementi:

* Le eVar hanno un limite di 255 byte nei rapporti. Le proprietà hanno un limite di 100 byte.
* Le proprietà per impostazione predefinita non persistono oltre l’hit impostato. Le eVar hanno una scadenza personalizzata, che consente di determinare quando a un eVar non viene più attribuito il merito per un evento successivo. Tuttavia, se usa [elaborazione dell’ora rapporto](/help/components/vrs/vrs-report-time-processing.md), sia prop che eVar possono utilizzare un modello di attribuzione personalizzato.
* Adobe supporta fino a 250 eVar e solo 75 prop.

Consulta [prop](prop.md) per ulteriori confronti tra prop ed eVar.
