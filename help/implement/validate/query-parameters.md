---
title: Parametri query della raccolta dati
description: Elenca tutti i parametri della stringa di query utilizzati nelle richieste di immagini.
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/aB92GXPxYSkjcDD9wi0vj47jijqndMbOGaECvXs38-Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 1067
ht-degree: 42%

---

# Parametri query della raccolta dati

Nella tabella seguente sono elencati tutti i parametri delle stringhe di query utilizzati da Adobe nelle richieste di immagini. Queste informazioni sono utili per il debug con [analizzatori di pacchetti](packet-monitor.md), quando [richieste di immagini a codifica fissa](../other/hardcoded.md) o quando si utilizzano [variabili dinamiche](../vars/page-vars/dynamic-variables.md).

| Parametro | Variabile di implementazione di Analytics | Descrizione |
| --- | --- | --- |
| `aamlh` | Nessuno | Hint posizione Audience Manager Identifica il data center regionale utilizzato per la sincronizzazione Audience Manager ID tramite il servizio ID visitatore. |
| `aamb` | Nessuno | Blob di Audience Manager Dati del profilo Audience Manager codificati trasmessi durante la sincronizzazione ID tramite il servizio ID visitatore. |
| `aid` | Nessuno | ID visitatore Analytics legacy, memorizzato nel cookie `s_vi`. Sostituito dal parametro `mid` nelle implementazioni moderne. |
| `AQB` | Nessuno | Indica l’inizio di una stringa di query di richiesta immagine. |
| `AQE` | Nessuno | Indica la fine di una richiesta di immagine, ovvero che la richiesta non è stata troncata. |
| `bh` | Nessuno | Altezza browser (in pixel). Utilizzato nella dimensione [[!UICONTROL Browser height]](/help/components/dimensions/browser-height.md). |
| `bw` | Nessuno | Larghezza browser (in pixel). Utilizzato nella dimensione [[!UICONTROL Browser width]](/help/components/dimensions/browser-width.md). |
| `c` | Nessuno | Qualità del colore (in bit). Utilizzato nella dimensione [[!UICONTROL Color depth]](/help/components/dimensions/color-depth.md). |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indica l’inizio delle variabili di dati di contesto. Non contiene mai un valore. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indica la fine delle variabili di dati di contesto. Non contiene mai un valore. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Prop](/help/components/dimensions/prop.md), o variabili di traffico personalizzate. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Tipo di valuta utilizzato nell’hit. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Non più in uso.** Il numero di periodi in un dominio. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Codifica dei caratteri della richiesta di immagine. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Il ciclo di vita dei cookie del visitatore. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Utilizzato nella dimensione [[!UICONTROL Site sections]](/help/components/dimensions/site-section.md). |
| `cp` | [`customerPerspective`](../vars/page-vars/customerperspective.md) | Specifica se si è verificato un hit in un&#39;app mobile mentre l&#39;app era in primo piano o in background. Utilizzato nella dimensione [[!UICONTROL Hit type]](/help/components/dimensions/hit-type.md). |
| `ct` | Nessuno | Utilizzato nella dimensione [[!UICONTROL Connection type]](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indica cosa utilizzare per le variabili dinamiche. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Sintassi abbreviata per il parametro `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Elenco di eventi separato da virgole sulla pagina. Utilizzato dalla maggior parte delle [metriche](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | L’URL corrente della pagina, fino a 255 byte. Utilizzato nella dimensione [[!UICONTROL Page URL]](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../vars/page-vars/pageurl.md) | Gli URL più lunghi di 255 byte vengono suddivisi. I primi 255 byte vengono visualizzati nel parametro `g` e tutti i byte rimanenti vengono visualizzati nel parametro `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Sintassi abbreviata per il parametro `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Sintassi abbreviata per il parametro `pageType`. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Prefisso per diverse variabili che rappresentano [Hint client](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/page-variables.md#retired-page-variables) | **Non più in uso.** Dimensioni gerarchiche. |
| `hp` | Nessuno | **Non più in uso.** Nelle versioni precedenti di Adobe Analytics, determinava se l’URL corrente era la pagina home del browser. |
| `j` | Nessuno | **Non più in uso.** La versione JavaScript installata nel browser. |
| `k` | Nessuno | Utilizzato nella dimensione [[!UICONTROL Cookie support]](/help/components/dimensions/cookie-support.md). |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variabili elenco. |
| `lat` | Nessuno | **Non più in uso.** Latitudine. Impostato dalle implementazioni legacy di mobile SDK; le implementazioni mobili correnti inviano la geolocalizzazione tramite flussi di dati. |
| `lon` | Nessuno | **Non più in uso.** Longitudine. Impostato dalle implementazioni legacy di mobile SDK; le implementazioni mobili correnti inviano la geolocalizzazione tramite flussi di dati. |
| `lrt` | Nessuno | La “tempistica dell’ultima richiesta”, che è la durata del ciclo di andata e ritorno per l’ultima richiesta, in millisecondi. Viene inviato solo quando vengono inviate più richieste da una singola pagina, ad esempio in un’applicazione a pagina singola. |
| `mcorgid` | Nessuno | L’ID organizzazione IMS, che identifica l’organizzazione nel servizio ID visitatore. |
| `mid` | Nessuno | Utilizzato nella dimensione [[!UICONTROL Experience Cloud Visitor ID]](/help/components/dimensions/experience-cloud-visitor-id.md). |
| `ms_a` | Nessuno | Impostato da Media SDK su `1` quando i contenuti multimediali in streaming tracciati sono audio anziché video. |
| `ndh` | Nessuno | Aggiunto da AppMeasurement a ogni richiesta di immagine generata. Poiché le richieste hardcoded in genere la omettono, la sua presenza indica che l’hit proviene da AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Non più in uso.** Consente di determinare dove vengono impostati i cookie. |
| `oi` | Nessuno | **Non più in uso.** Istanza oggetto per l&#39;ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificatore oggetto per l’ultima pagina. Utilizzato nella versione corrente di Activity Map. |
| `oidt` | Nessuno | **Non più in uso.** Tipo di identificatore oggetto per l&#39;ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `ot` | Nessuno | **Non più in uso.** Nome oggetto per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `p` | Nessuno | **Non più in uso.** Elenco dei plug-in utilizzati nel browser. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Utilizzato nella dimensione [[!UICONTROL Page]](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Utilizzato nella dimensione [[!UICONTROL Pages not found]](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Nessuno | Flag di reindirizzamento verifica cookie persistenti. Impostato dai server di raccolta dati di Adobe per i nuovi visitatori e sempre impostato su `true`. Quando il supporto dei cookie di un nuovo visitatore è sconosciuto, il server di raccolta dati reindirizza a se stesso la richiesta di immagine con questo flag per confermare che il controllo persistente dei cookie si è già verificato. Questo parametro impedisce reindirizzamenti infiniti se il visitatore rifiuta i cookie. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Determina il tipo di hit. I valori validi includono `lnk_o` ([[!UICONTROL Custom link]](/help/components/dimensions/custom-link.md)), `lnk_d` ([[!UICONTROL Download link]](/help/components/dimensions/download-link.md)), `lnk_e` ([[!UICONTROL Exit link]](/help/components/dimensions/exit-link.md)) e `tnt` (hit di Analytics for Target). |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | URL in cui si è verificato il collegamento personalizzato. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Il nome descrittivo del [collegamento personalizzato](/help/components/dimensions/custom-link.md). |
| `pev3` | Nessuno | **Non più in uso.** Attività cardine tracciate nelle versioni precedenti dei rapporti video. |
| `pf` | Nessuno | Flag della piattaforma; solo per Adobe. Non modificare. |
| `pid` | Nessuno | **Non più in uso.** Identificatore della pagina per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `pidt` | Nessuno | **Non più in uso.** Tipo di identificatore della pagina per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Sintassi abbreviata per il parametro `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variabile dei prodotti. Utilizzato nelle dimensioni [[!UICONTROL Product]](/help/components/dimensions/product.md) e [[!UICONTROL Category]](/help/components/dimensions/category.md). |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Utilizzato nella dimensione [[!UICONTROL Purchase ID]](/help/components/dimensions/purchase-id.md). |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL di provenienza dell’hit. Utilizzato nelle dimensioni delle origini di traffico, ad esempio [[!UICONTROL Referrer]](/help/components/dimensions/referrer.md) e [[!UICONTROL Referring domain]](/help/components/dimensions/referring-domain.md). |
| `s` | Nessuno | Risoluzione dello schermo, in `width x height`. Utilizzato nella dimensione [[!UICONTROL Monitor resolutions]](/help/components/dimensions/monitor-resolution.md). |
| `sdid` | Nessuno | ID dati supplementari. Collega più hit che descrivono lo stesso evento, ad esempio gli hit di Analytics e di Target in un&#39;integrazione di [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html). |
| `server` | [`server`](../vars/page-vars/server.md) | Utilizzato nella dimensione [[!UICONTROL Server]](/help/components/dimensions/server.md). |
| `sv` | [`server`](../vars/page-vars/server.md) | Sintassi abbreviata per il parametro `server`. |
| `state` | [`state`](../vars/page-vars/page-variables.md#retired-page-variables) | **Non più in uso.** Acquisito lo stato statunitense in cui un visitatore è entrato, in genere tramite un modulo di spedizione o di fatturazione. |
| `t` | Nessuno | Data/ora generata dell’hit. Utilizza il formato `dd/mm/yyyy hh:mm:ss w o`.<br>-`dd/mm/yyyy hh:mm:ss` è data/ora in JavaScript. Il mese `0` è gennaio, mentre il mese `11` è dicembre.<br>-`w` è il giorno della settimana. `0` è domenica, mentre `6` è sabato.<br>- `o` è l&#39;offset GMT negativo in minuti. Ad esempio: `420` è GMT-7. |
| `tnt` | Nessuno | Payload di dati di destinazione utilizzato nelle integrazioni [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html). Inviato quando `pe=tnt`. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | La marca temporale personalizzata impostata con l’hit. Generalmente utilizzata per il tracciamento offline. |
| `u` | Nessuno | **Non più in uso.** Marcatore account utilizzato nelle versioni precedenti di Activity Map. |
| `v` | Nessuno | Utilizzato nella dimensione [[!UICONTROL Java enabled]](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | Utilizzato nella dimensione [[!UICONTROL Tracking code]](/help/components/dimensions/tracking-code.md). |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md) o dimensioni di conversione personalizzate. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variabile di sostituzione dell’ID visitatore. |
| `vidn` | Nessuno | Impostato dai server di raccolta dati di Adobe per i nuovi visitatori, che accompagna il parametro `pccr` nella richiesta di immagine reindirizzata. Contiene il valore ID visitatore memorizzato nel cookie visitatore. |
| `vmf` | [`visitorMigrationServer`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Non più in uso.** Server di migrazione dei visitatori utilizzato durante la migrazione dai cookie di terze parti a quelli di prime parti. |
| `vmt` | [`visitorMigrationKey`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **Non più in uso.** Chiave di migrazione del visitatore, che ha aiutato a migrare le implementazioni da cookie di terze parti a cookie di prime parti. |
| `vvp` | Nessuno | **Non più in uso.** Provider di variabili utilizzato in Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Utilizzato con Origini dati per collegare dati online e offline. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Utilizzato nella dimensione [Codice postale](/help/components/dimensions/zip-code.md). |
