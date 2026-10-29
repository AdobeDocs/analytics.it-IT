---
title: Raccolta dati di Debug Analytics
description: Conferma che Adobe Analytics riceva i dati previsti da AppMeasurement, dall’estensione Analytics, da Web SDK, Mobile SDK e dall’API di inserimento dati.
keywords: debug, convalida, packet analyzer, packet monitor, /b/ss/, Edge Trace, Assurance, hitdebugger, report suite
feature: Implementation Basics
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 049b9b7447c7f91d67eb58fc781898b685bd9d91
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 2%
---
# Raccolta dati di Debug Analytics

Questo articolo spiega cosa controllare quando esegui il debug dei dati inviati ad Adobe Analytics. Trova il tuo metodo di implementazione nella tabella seguente e segui la relativa sezione. Se stai analizzando dati di report imprevisti, inizia con [Confronta le richieste con i report](#reports).

Per i passaggi e gli strumenti applicabili a tutte le raccolte dati di Adobe, ad esempio l&#39;acquisizione delle richieste di rete, l&#39;abilitazione della registrazione di debug e l&#39;analisi delle richieste annullate, vedere [Debug e risoluzione dei problemi di raccolta dati](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/overview).

| Metodo di implementazione | Dove visualizzare i dati ricevuti da Analytics | Linee guida |
| --- | --- | --- |
| AppMeasurement o l’estensione tag Analytics | Richieste dal browser direttamente ai server di raccolta dati di Analytics | [AppMeasurement](#appmeasurement) |
| Web SDK | Edge Trace, dopo che Edge Network converte l’evento in un hit di Analytics | [Web SDK](#web-sdk) |
| Mobile SDK | La visualizzazione Eventi di Analytics in Assurance. Se utilizzi l&#39;estensione Edge Network o Edge Bridge, attiva **[!UICONTROL Analytics Edge View]**. | [Visualizzazione eventi Adobe Analytics in Assurance](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/adobe-analytics) |
| API di inserimento dati | Richieste in uscita del server e relative risposte | [Risoluzione dei problemi relativi alle richieste API di inserimento dati](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting) |

## AppMeasurement e l’estensione Analytics {#appmeasurement}

### Trovare la richiesta {#appmeasurement-find}

[Acquisire le richieste di rete](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#web) e filtrare per `/b/ss/`. I debugger di tag come Adobe Experience Platform Debugger identificano e decodificano queste richieste per te.

Se non viene visualizzata alcuna richiesta `/b/ss/`:

* Controlla la console del browser per verificare la presenza di errori JavaScript.
* Se utilizzi l&#39;estensione tag di Analytics, verifica che il codice di incorporamento del tag sia all&#39;interno dell&#39;elemento `<head>` della pagina e che la libreria sia pubblicata nell&#39;ambiente che stai testando. [La modalità di debug dei tag](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/logging) indica se la regola che invia l&#39;hit è attivata.
* Se ospiti AppMeasurement, apri direttamente l’URL della libreria per confermare che il file viene caricato e contiene codice.
* Disattiva le estensioni del browser, ad esempio i blocchi degli annunci, che possono impedire l’invio di richieste.
* Debugger non riconosce le richieste inviate dall’interno di un iframe. Utilizza invece gli strumenti per sviluppatori del browser. Vedi [Utilizzare AppMeasurement con iFrame](../use-cases/iframe.md).

### Controlla cosa ha ricevuto Analytics {#appmeasurement-contents}

* **Suite di rapporti**: il segmento di percorso dopo `/b/ss/` elenca gli ID suite di rapporti che ricevono l&#39;hit. Conferma che siano le suite di rapporti previste, ad esempio una suite di rapporti per lo sviluppo nelle pagine di sviluppo.
* **Variabili**: le richieste non elaborate utilizzano i nomi dei parametri di query anziché i nomi delle variabili; ad esempio, eVar1 viene visualizzato come `v1` e prop1 come `c1`. Vedi il riferimento alla [variabile](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference). Quando una richiesta è troppo lunga, AppMeasurement la invia con HTTP `POST`, in modo che le variabili vengano visualizzate nel corpo della richiesta invece che nell&#39;URL.
* **Tipo di hit**: le richieste inviate da [`tl()`](../vars/functions/tl-method.md) includono il parametro `pe` e non incrementano le visualizzazioni di pagina. Le richieste inviate da [`t()`](../vars/functions/t-method.md) non includono `pe`.

Se i valori sono presenti ma errati, vedere [Risoluzione dei problemi relativi all&#39;implementazione di JavaScript](../js/troubleshooting.md) per informazioni sulle cause più comuni, ad esempio citazioni, maiuscole e spazi vuoti.

### Controlla la risposta {#appmeasurement-response}

Una risposta di `2xx` conferma solo che il server di raccolta dati ha ricevuto la richiesta e non che l&#39;hit è stato registrato. Con il tipo di risposta predefinito, una richiesta può restituire esito positivo anche quando l’hit viene rilasciato. È prevista una risposta `302` alla prima richiesta di un nuovo visitatore. Vedi [Codici di risposta HTTP](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes).

AppMeasurement invia richieste di collegamento di uscita e tutte le richieste quando [`useBeacon`](../vars/config-vars/usebeacon.md) è abilitato, con `navigator.sendBeacon()`. Gli strumenti per sviluppatori possono etichettare queste richieste come annullate anche quando il browser le ha inviate. Vedi [Richieste interrotte](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#aborted-requests).

## Web SDK {#web-sdk}

### Trovare la richiesta {#web-sdk-find}

Con Web SDK, il browser invia gli eventi ad Edge Network invece di inviarli direttamente ad Analytics, in modo che non venga visualizzata una richiesta `/b/ss/`. [Controlla la richiesta di Edge Network](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#edge-network-requests) e conferma quanto segue:

* Il parametro `configId` corrisponde a un flusso di dati in cui il servizio [Adobe Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure#analytics) è abilitato con le suite di rapporti previste.
* Il payload si qualifica come visualizzazione di pagina o evento di collegamento. Analytics ignora i payload che non contengono né dettagli di pagina né un tipo di interazione web. Vedi [Tipi di evento Edge Network in Adobe Analytics](../aep-edge/hit-types.md).

### Controlla cosa ha ricevuto Analytics {#web-sdk-contents}

Avvia un [Edge Trace](https://experienceleague.adobe.com/en/docs/experience-platform/debugger/edge-trace) e riproduce l&#39;azione. Individua la riga che inizia con **[!UICONTROL Analytics Automatic Mapping]**, quindi espandi `mappedQueryParams` e l&#39;ID suite di rapporti sotto di essa.

* **Variabili**: i valori mappati utilizzano gli stessi nomi dei parametri di query delle richieste AppMeasurement, talvolta in forma abbreviata, ad esempio `gn` per il nome della pagina e `pl` per i prodotti. Vedi [Mappatura campo oggetto XDM](../aep-edge/xdm-var-mapping.md) e [Mappatura campo oggetto dati](../aep-edge/data-var-mapping.md).
* **Dati contestuali**: i campi XDM che non sono mappati a una variabile Analytics vengono visualizzati come dati contestuali con il prefisso `c.a.x.`. Utilizza [regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) per assegnarle alle variabili.
* **Suite di rapporti**: se utilizzi le sostituzioni delle suite di rapporti, la riga di configurazione dello stream di dati in Edge Trace mostra le suite di rapporti utilizzate da Edge Network.

### Verifica elaborazione {#web-sdk-processing}

Nella sessione di Assurance aperta da Edge Trace, cerca gli eventi per `hitdebugger`. Questi eventi utilizzano il fornitore `com.adobe.analytics.hitdebugger` e i relativi payload mostrano valori dopo l&#39;elaborazione di Analytics, ad esempio Experience Cloud ID (`mcvisId`) e `pageName`.

Per informazioni dettagliate, vedere [Configurare Adobe Analytics con Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/it/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics).

## Confrontare le richieste con i rapporti {#reports}

Un hit che raggiunge Analytics non viene visualizzato immediatamente nei rapporti e i valori riportati possono differire dai valori della richiesta:

* **Latenza**: i dati completi vengono generalmente visualizzati nei rapporti circa due ore dopo la raccolta. Alcuni dati, ad esempio gli hit con marca temporale, possono richiedere più tempo. Consulta [Disponibilità e latenza dei dati](/help/technotes/latency.md).
* **Elaborazione**: le regole di elaborazione, le regole VISTA, le regole bot e altri passaggi di elaborazione possono modificare o escludere i valori dopo la raccolta. Vedi [Ordine di elaborazione per i dati in Adobe Analytics](/help/technotes/processing-order.md). I dati post-elaborati di Assurance mostrano il risultato dell’elaborazione per un singolo hit.
* **Suite di rapporti**: conferma di visualizzare la stessa suite di rapporti interessata dalla richiesta o dallo stream di dati.
* **Valori imprevisti**: se una dimensione mostra picchi o valori imprevisti, vedere [Conflitti hash](hash-collisions.md).

Per modifiche più ampie al traffico, consulta [Risoluzione dei problemi relativi a picchi e cadute nei dati](/help/technotes/event/spikes-drops.md).
