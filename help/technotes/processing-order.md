---
title: Ordine di elaborazione per dati in Adobe Analytics
description: Scopri l’ordine dei componenti e dei servizi che elaborano i dati in Adobe Analytics.
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: 6c947812d4fd8bc2ee951a5933c6e3b6d8ca1a6b
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 35%

---

# Ordine di elaborazione per dati in Adobe Analytics

Adobe offre diversi modi per modificare o intervenire sui dati prima che vengano visualizzati nel reporting. Questa pagina mostra l’ordine in cui diverse funzioni di Adobe Analytics elaborano i dati. È possibile utilizzare questo elenco per risolvere eventuali incongruenze nei dati o per determinare la funzione migliore da utilizzare quando sono necessarie modifiche dei dati.

![Elaborazione immagine ordine](assets/processing-order.png)

## Dati prima dell’invio ad Adobe

Prima dell’invio dei dati ad Adobe, in genere avviene una compilazione lato client utilizzando uno dei seguenti metodi:

* **AppMeasurement**: un file JavaScript ospitato sul tuo sito e a cui si fa riferimento in ogni pagina. I dati vengono inviati direttamente ad Adobe Analytics.
* **Adobe Experience Platform Web SDK**: un file JavaScript ospitato sul tuo sito e a cui si fa riferimento in ogni pagina. I dati vengono inviati a Adobe Experience Platform Edge Network.
* **Tag nella raccolta dati di Adobe Experience Platform**: un file JavaScript a cui si fa riferimento in ogni pagina, contenente regole create all&#39;interno dell&#39;interfaccia utente di raccolta dati. L’estensione Adobe Analytics offre un modo più semplice per implementare AppMeasurement. L’estensione Web SDK offre un modo più semplice per implementare Web SDK.
* **API**: sia AppMeasurement che Edge Network offrono metodi programmatici per inviare dati ad Adobe. AppMeasurement offre l&#39;[API di inserimento dati](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) e l&#39;[API di inserimento dati in blocco](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/); Edge Network offre l&#39;[API di raccolta dati](https://developer.adobe.com/data-collection-apis/docs/).

Se invii dati ad Edge Network, puoi configurarlo per l’inoltro di dati ad Adobe Analytics (nonché a molte altre soluzioni Adobe Experience Cloud). Indipendentemente dal metodo di implementazione, i dati hit raccolti arrivano ai server di elaborazione Adobe Analytics in un formato che può essere analizzato.

## Pre-elaborazione nella raccolta Adobe Analytics

Quando i dati arrivano ad Adobe Analytics, entrano in una fase di pre-elaborazione:

1. [**Variabili dinamiche**](/help/implement/vars/page-vars/dynamic-variables.md): se una variabile dinamica viene visualizzata in una qualsiasi parte di una richiesta di immagine, il valore viene copiato e trattato come un valore indipendente da qui in avanti.
1. [**Offuscamento IP (ultimo ottetto)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): se la suite di rapporti è configurata per offuscare solo l&#39;ultimo ottetto, tale offuscamento si applica qui. L’omissione dell’IP (rimozione dell’IP) si verifica più avanti nella pipeline di elaborazione.
1. **Tabelle di ricerca**: le dimensioni che si basano su tabelle di ricerca interne di Adobe (ad esempio, la dimensione [Browser](/help/components/dimensions/browser.md)) vengono associate al valore corrispondente.
1. [**Esclusione IP**](/help/admin/tools/exclude-ip.md): tutti gli indirizzi IP che escludi esplicitamente dal reporting vengono contrassegnati durante questo passaggio.
1. [**Regole bot**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md): applica un filtro bot standard o personalizzato per escludere tali dati dal reporting.
1. **Dati di geolocalizzazione**: vengono compilate dimensioni che si basano sulla ricerca degli indirizzi IP (ad esempio, la dimensione [Paesi](/help/components/dimensions/countries.md)).
1. [**Regole di elaborazione**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md): regole personalizzate applicate ai dati dalla tua organizzazione. Include la mappatura di [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) alle rispettive variabili di Analytics.
1. [**Regole VISTA**](vista.md): regole flessibili personalizzate applicate ai tuoi dati da un consulente di Adobe. Potenzialmente, le regole VISTA possono essere eseguite prima o dopo le regole di elaborazione, a seconda delle esigenze della tua organizzazione. La maggior parte delle regole VISTA viene generalmente eseguita dopo le regole di elaborazione, ma ogni organizzazione viene impostata in modo diverso. Contatta il team del tuo account Adobe per ulteriori informazioni sulle regole VISTA esistenti.
1. **Conversione valuta**: se l&#39;hit contiene un [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) diverso dalla valuta della suite di rapporti, tutte le variabili di valuta applicabili vengono convertite utilizzando il tasso di cambio del giorno corrente.
1. [**Codice postale**](/help/components/dimensions/zip-code.md): la dimensione &#39;Codice postale&#39; viene popolata in base alle impostazioni della suite di rapporti.

## Fase &quot;mid-value&quot; della pipeline di raccolta dati

Al termine della pre-elaborazione, diverse funzioni utilizzano questa forma di dati parzialmente elaborata, nota come &quot;valori medi&quot;. Prima che i dati vengano inviati ovunque, viene applicata un’elaborazione specifica per il valore intermedio:

1. [**Regole di elaborazione del canale di marketing a livello di hit**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md): queste regole di elaborazione vengono eseguite in modo specifico per il connettore Source di Analytics. Poiché non esiste ancora un contesto a livello di visita o visitatore, queste regole di elaborazione presuppongono che un hit non sia il primo hit di una visita. I risultati dell&#39;esecuzione delle regole di elaborazione per un hit sono disponibili in `channel.typeAtSource` e `channel._id`.
1. [**Offuscamento IP (rimuovere IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): se la suite di rapporti è configurata per offuscare completamente un indirizzo IP, tale offuscamento si applica qui (solo per i valori medi).

A questo punto, i dati con valore intermedio vengono inviati alla rispettiva funzione:

* [**API Livestream**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/): connettere un&#39;applicazione al servizio livestream di Adobe per un flusso di dati durante la raccolta.
* [**Connettore Source Analytics**](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/analytics): acquisisce i dati della suite di rapporti di Adobe Analytics in un set di dati Adobe Experience Platform.
* [**Rapporti in tempo reale**](/help/components/c-real-time-reporting/realtime.md): fornisce fino a tre rapporti in tempo reale configurabili in Analysis Workspace.

## Elaborazione a livello di visita e visitatore

Fino a questo punto, un determinato hit non ha alcuna conoscenza o contesto degli hit raccolti prima o dopo di esso. Questa fase di elaborazione popola i campi a livello di visita e visitatore.

1. [**Visita + definizione visitatore**](/help/implement/id/overview.md): l&#39;hit viene identificato in base alle variabili visitatore contenute.
1. [**Numero di visite**](/help/components/dimensions/visit-number.md): in base ad altre visite per il visitatore identificato, viene calcolato il numero di visite.
1. **Deduplicazione eventi**: se l&#39;hit contiene una [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) o [serializzazione eventi](/help/implement/vars/page-vars/events/event-serialization.md) duplicata, tali ID vengono verificati e contrassegnati rispettivamente.
1. [**Regole di elaborazione del canale di marketing a livello di visita**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md): ogni hit viene eseguito tramite le regole di elaborazione del canale di marketing e i relativi dettagli di canale e canale vengono determinati se l&#39;hit corrisponde a una regola. Queste regole popolano le dimensioni [Canale di marketing](/help/components/dimensions/marketing-channel.md) e [Dettagli canale di marketing](/help/components/dimensions/marketing-detail.md) disponibili in Analysis Workspace.
1. **Persistenza variabile**: per le dimensioni con persistenza (ad esempio [eVar](/help/components/dimensions/evar.md)), tale valore viene determinato in questo passaggio. In generale, la maggior parte dei valori `post` sono impostati qui.
1. **ID transazione**: se l&#39;hit contiene un nuovo valore [`transactionID`](/help/implement/vars/page-vars/transactionid.md), viene memorizzata una &quot;istantanea&quot; di tutti i valori supportati. Quando un caricamento origine dati contiene un ID transazione corrispondente, tutti i valori supportati da questa istantanea vengono inclusi nella riga dell&#39;origine dati.
1. [**Offuscamento IP (rimuovere IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): se la suite di rapporti è configurata per offuscare completamente un indirizzo IP, tale offuscamento si applica qui al termine di tutte le altre elaborazioni.

A questo punto, il singolo hit viene registrato nelle tabelle di dati della suite di rapporti. Dopo l’intervallo di [latenza](latency.md) standard, questo diviene disponibile nel reporting.

## Modifica dei dati dopo l’elaborazione

I dati in Adobe Analytics sono per lo più permanenti. Tuttavia, esistono alcune funzioni che possono consentire la modifica o la rimozione selettiva dei dati:

* [**API Data Repair**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): modifica determinate colonne o elimina le righe di dati desiderate.
* [**Governance dei dati**](/help/technotes/privacy/privacy-overview.md): soddisfa le richieste di privacy per eliminare definitivamente i dati.
* [**Classificazioni**](/help/components/classifications/classifications-overview.md): crea dimensioni basate su regole o dati caricati che ti consentono di organizzare i dati in modo diverso. I dati sottostanti della suite di rapporti non vengono modificati, pertanto puoi modificare o sovrascrivere liberamente i dati di classificazione.
* [**Suite di rapporti virtuali**](/help/components/vrs/vrs-about.md): crea una visualizzazione alternativa della suite di rapporti che può modificare il timeout della visita.
