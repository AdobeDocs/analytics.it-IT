---
title: eVar (dimensione)
description: Una dimensione personalizzata che puoi utilizzare nel reporting.
feature: Dimensions
exl-id: ce7cc999-281d-4c52-b64d-d44cc320ab2d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: ht
source-wordcount: '822'
ht-degree: 100%

---

# eVar

*Questa pagina della guida descrive il funzionamento delle eVar come [dimensione](overview.md). Per informazioni su come implementare le eVar, consulta [eVar](/help/implement/vars/page-vars/evar.md) nella Guida utente per l’implementazione.*

Le eVar sono variabili personalizzate che puoi utilizzare come desideri. Se si dispone di un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), la maggior parte delle dimensioni specifiche per l’organizzazione finiscono per essere [!UICONTROL eVars], oltre alla dimensione predefinita disponibile con Adobe Analytics, come “Nome pagina”, “Dominio di riferimento”, “Canale”. Per ulteriori informazioni, consulta [Panoramica delle dimensioni](overview.md).

Per impostazione predefinita, le eVar persistono oltre l’hit su cui sono impostate. Puoi personalizzarne la scadenza e l’allocazione in [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) nelle [!UICONTROL Report suite settings]. Consulta il seguente esempio di definizioni eVar nell’interfaccia delle variabili di conversione.

![Esempi di eVar](assets/evars-sample.png)

Il numero di eVar disponibili dipende dal contratto con Adobe. Se il contratto con Adobe lo supporta, sono disponibili fino a 250 eVar.

La lettera (maiuscola o la minuscola) utilizzata nei rapporti si basa sul primo valore registrato dal sistema backend. Questo valore potrebbe essere la prima istanza mai vista o variare su base temporale (ad esempio, mensilmente), a seconda della varietà e della quantità di dati associati alla suite di rapporti.

## Popolare le eVar con i dati

Ogni eVar raccoglie dati dalla stringa di query [`v1` - `v250`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il parametro della stringa di query `v1` raccoglie i dati per eVar1, mentre il parametro della stringa di query `v222` raccoglie i dati per eVar222.

AppMeasurement, che compila variabili JavaScript in una richiesta di immagine per la raccolta dati, utilizza le variabili `eVar1` - `eVar250`. Per le linee guida all’implementazione, consulta [eVar](/help/implement/vars/page-vars/evar.md) nella Guida utente per l’implementazione.

## Elementi dimensionali

Poiché le eVar contengono stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensionali di ciascuna eVar. Assicurati di registrare lo scopo di ogni eVar e degli elementi dimensionali tipici in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).

## Funzionamento delle eVar

Quando invii dati ad Adobe Analytics, i server di raccolta dati traducono l’hit in un’unica riga di dati con centinaia di colonne. A ogni eVar sono dedicate due colonne, una per la raccolta dati diretta e l’altra per i valori persistenti.

* Una colonna standard contiene i dati inviati ad Adobe dalla richiesta di immagine.
* Una colonna “post” contiene dati persistenti, che dipendono dalla scadenza e dall’allocazione dell’eVar.

In quasi tutte le circostanze, viene usata la colonna `post_evar` nei rapporti.

### Come collegare le eVar alle metriche

Gli eventi di successo e le eVar sono definiti spesso in diverse richieste di immagini. La colonna `post_evar` consente ai valori eVar di collegarsi agli eventi, mostrando i dati nel reporting. Considera per esempio la seguente visita:

1. Un visitatore arriva sulla pagina Home del tuo sito.
2. Cerca “gatti” usando la ricerca interna del tuo sito. L’implementazione utilizza eVar1 per la ricerca interna.
3. Visualizza un prodotto e procede al processo di pagamento.

Una versione semplificata dei dati non elaborati sarà simile alla seguente:

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` | | | |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` | | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` | | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` | | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` | | `cats` | `purchase` |

* La colonna `visitor_id` collega gli hit allo stesso visitatore. Nei dati non elaborati effettivi, i valori concatenati di `visid_high` e `visid_low` determinano l’ID visitatore.
* La colonna `pagename` popola la dimensione Pagine.
* La colonna `evar` determina gli hit quando eVar1 è stata impostata esplicitamente.
* Il `post_evar1` riporta il valore precedente, a seconda dell’allocazione e della scadenza della variabile impostate nelle impostazioni della suite di rapporti.
* La colonna `event_list` contiene tutti i dati delle metriche. Per questo esempio, `event1` è “Ricerche”, mentre gli altri eventi sono metriche standard del carrello. Nei dati non elaborati effettivi, `event_list` contiene un set di numeri delimitato da virgole con una tabella di ricerca che collega tali numeri a una metrica.

### Traduzione della raccolta dati nel reporting

Gli strumenti di Adobe Analytics, come Analysis Workspace, smaltiscono questi dati raccolti. Ad esempio, se hai estratto un rapporto utilizzando eVar1 come dimensione e Ordini come metrica, visualizzerai un report simile al seguente:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace estrae questo report utilizzando la seguente logica:

* Cerca in tutti i valori `event_list` e preleva tutti gli hit con `purchase` in essi.
* Di questi hit, visualizza il valore `post_evar1`.

### Importanza dell’allocazione e della scadenza

Poiché l’allocazione e la scadenza determinano quali valori persistono, sono vitali per ottenere il massimo valore da un’implementazione di Analytics. Adobe consiglia vivamente di discutere all’interno dell’organizzazione come vengono gestiti più valori per ogni eVar (allocazione) e quando le eVar cessano di mantenere i dati persistenti (scadenza).

* Per impostazione predefinita, un’eVar utilizza l’ultima allocazione. I nuovi valori sovrascrivono quelli persistenti.
* Per impostazione predefinita, un’eVar utilizza una scadenza di visita. Al termine di una visita, i valori non vengono più copiati di riga in riga nella colonna `post_evar`.

Puoi cambiare allocazione e scadenza delle eVar in [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) nelle impostazioni delle suite di rapporti.

## Valore delle eVar rispetto alle prop

Adobe consiglia di utilizzare le eVar nella maggior parte dei casi, supportate tramite i seguenti elementi:

* Le eVar hanno un limite di 255 byte nei rapporti. Le prop hanno un limite di 100 byte.
* Le prop non persistono oltre l’hit impostato per impostazione predefinita. Le eVar hanno una scadenza personalizzata, che consente di determinare quando a un’eVar non viene più attribuito il credito per un evento successivo. Tuttavia, se usi l’[elaborazione al momento del rapporto](/help/components/vrs/vrs-report-time-processing.md), sia le prop che le eVar possono utilizzare un modello di attribuzione personalizzato.
* Adobe supporta fino a 250 eVar e solo 75 prop.

Consulta [prop](prop.md) per ulteriori confronti tra prop ed eVar.
