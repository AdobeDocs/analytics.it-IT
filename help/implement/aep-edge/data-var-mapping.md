---
title: Mappatura del campo dell’oggetto dati su Adobe Analytics
description: Visualizza i campi dell’oggetto dati mappati automaticamente da Experience Platform Edge alle variabili di Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
TQID: https://experienceleague.adobe.com/FQRTVL9KrCQktNMhpqXo0f2VSrEm2mcCNL6IAmvtrko
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 614
ht-degree: 7%

---

# Mappatura del campo dell’oggetto dati su Adobe Analytics

La tabella seguente mostra il campo dell’oggetto dati mappato automaticamente da Adobe Experience Platform Edge Network in Adobe Analytics. Se utilizzi questi percorsi dei campi dell’oggetto dati, non è necessaria alcuna configurazione aggiuntiva per inviare dati ad Adobe Analytics.

L’utilizzo di questi campi è consigliato se intendi utilizzare Customer Journey Analytics in futuro. Questo metodo di implementazione consente all’organizzazione di inviare dati ad Adobe utilizzando il Web SDK senza essere conforme a uno schema XDM. Quando la tua organizzazione è pronta per inviare dati a Adobe Experience Platform, puoi utilizzare la [mappatura dello stream di dati](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/data-prep#mapping) per puntare i campi dell&#39;oggetto dati ai rispettivi campi XDM.

## Priorità di valore

La maggior parte dei campi oggetto dati in questa tabella corrisponde a un [campo XDM mappato](xdm-var-mapping.md). Durante l’acquisizione di Adobe Analytics, i valori vengono prima mappati da XDM alle variabili Analytics. I campi degli oggetti dati riconosciuti vengono quindi mappati e sovrascrivono eventuali valori impostati in precedenza quando vengono mappati sulla stessa variabile di Analytics. Ad esempio, se `data.__adobe.analytics.events` è presente, sostituisce l&#39;intero set di eventi che sarebbero altrimenti derivati da XDM; gli eventi non vengono combinati tra le due origini. Una stringa vuota (`""`) in un campo oggetto dati svuota la variabile Analytics mappata per l&#39;hit, anche se il campo XDM corrispondente contiene un valore.

Alcuni campi dell&#39;oggetto dati supportano anche i rispettivi valori del parametro [Query](../validate/query-parameters.md) come valori abbreviati. È possibile utilizzare campi oggetto dati standard e campi oggetto dati abbreviati in modo intercambiabile, purché ciascuno di essi sia destinato a variabili univoche. Evitare di impostare contemporaneamente un campo oggetto dati standard e il relativo campo oggetto dati a sintassi abbreviata. Adobe non può garantire quale campo ha la priorità.

## Mappatura campo oggetto dati

Gli aggiornamenti precedenti a questa tabella si trovano nella [cronologia dei commit su GitHub](https://github.com/AdobeDocs/analytics.it-IT/commits/main/help/implement/aep-edge/data-var-mapping.md) di questa pagina. Analogamente alle variabili di AppMeasurement, tutti i campi degli oggetti dati fanno distinzione tra maiuscole e minuscole.

| Percorso campo oggetto dati | Variabile e descrizione di Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | La dimensione [Altezza browser](../../components/dimensions/browser-height.md). È supportato anche il campo abbreviato `data.__adobe.analytics.bh`. |
| `data.__adobe.analytics.browserWidth` | La dimensione [Larghezza browser](../../components/dimensions/browser-width.md). È supportato anche il campo abbreviato `data.__adobe.analytics.bw`. |
| `data.__adobe.analytics.campaign` | La dimensione [Codice di tracciamento](../../components/dimensions/tracking-code.md). È supportato anche il campo abbreviato `data.__adobe.analytics.v0`. |
| `data.__adobe.analytics.channel` | La dimensione [Sezione del sito](../../components/dimensions/site-section.md). È supportato anche il campo abbreviato `data.__adobe.analytics.ch`. |
| `data.__adobe.analytics.colorDepth` | La dimensione [Profondità colore](../../components/dimensions/color-depth.md). È supportato anche il campo abbreviato `data.__adobe.analytics.c`. |
| `data.__adobe.analytics.connectionType` | La dimensione [Tipo di connessione](../../components/dimensions/connection-type.md). È supportato anche il campo abbreviato `data.__adobe.analytics.ct`. |
| `data.__adobe.analytics.contextData` | [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | La dimensione [Supporto cookie](../../components/dimensions/cookie-support.md). È supportato anche il campo abbreviato `data.__adobe.analytics.k`. |
| `data.__adobe.analytics.currencyCode` | La variabile di implementazione [`currencyCode`](../vars/config-vars/currencycode.md). È supportato anche il campo abbreviato `data.__adobe.analytics.cc`. |
| `data.__adobe.analytics.dynamicVariablePrefix` | La variabile di implementazione [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md). |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [dimensioni eVar](../../components/dimensions/evar.md). Sono supportati anche i campi abbreviati `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250`. |
| `data.__adobe.analytics.events` | [Eventi personalizzati](../../components/metrics/custom-events.md). Formattare questo campo in modo simile alla variabile di implementazione [`events`](../vars/page-vars/events/events-overview.md). |
| `data.__adobe.analytics.javaEnabled` | La dimensione [Java abilitato](../../components/dimensions/java-enabled.md). È supportato anche il campo abbreviato `data.__adobe.analytics.v`. |
| `data.__adobe.analytics.latitude` | Consente di impostare le dimensioni del ciclo di vita mobile [Posizione](../../components/dimensions/lifecycle-dimensions.md). È supportato anche il campo abbreviato `data.__adobe.analytics.lat`. |
| `data.__adobe.analytics.linkName` | La dimensione [Collegamento personalizzato](../../components/dimensions/custom-link.md), [Collegamento di download](../../components/dimensions/download-link.md) o [Collegamento di uscita](../../components/dimensions/exit-link.md), a seconda del valore in `data.__adobe.analytics.linkType`. È supportato anche il campo abbreviato `data.__adobe.analytics.pev2`. |
| `data.__adobe.analytics.linkURL` | La variabile di implementazione [`linkURL`](../vars/config-vars/linkurl.md). È supportato anche il campo abbreviato `data.__adobe.analytics.pev1`. |
| `data.__adobe.analytics.linkType` | Determina il tipo di collegamento su cui è stato fatto clic. I valori validi includono `o` (Collegamenti personalizzati), `d` (Collegamenti di download) e `e` (Collegamenti di uscita). È supportato anche il campo abbreviato `data.__adobe.analytics.pe`. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) variabili di implementazione. Sono supportati anche i campi abbreviati `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3`. |
| `data.__adobe.analytics.longitude` | Guida a impostare le dimensioni del ciclo di vita mobile [Posizione](../../components/dimensions/lifecycle-dimensions.md). È supportato anche il campo abbreviato `data.__adobe.analytics.lon`. |
| `data.__adobe.analytics.pageName` | La dimensione [Pagina](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | La dimensione [URL della pagina](/help/components/dimensions/page-url.md). È supportato anche il campo abbreviato `data.__adobe.analytics.g`. |
| `data.__adobe.analytics.pageType` | La variabile di implementazione [`pageType`](../vars/page-vars/pagetype.md). |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) dimensioni. Sono supportati anche i campi abbreviati `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75`. |
| `data.__adobe.analytics.purchaseID` | La variabile di implementazione [`purchaseID`](../vars/page-vars/purchaseid.md). |
| `data.__adobe.analytics.products` | La variabile di implementazione [`products`](../vars/page-vars/products.md), con formattazione simile. |
| `data.__adobe.analytics.referrer` | La dimensione [Referrer](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | La dimensione [Risoluzione monitor](../../components/dimensions/monitor-resolution.md). È supportato anche il campo abbreviato `data.__adobe.analytics.s`. |
| `data.__adobe.analytics.server` | La dimensione [Server](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | La variabile di implementazione [`transactionID`](../vars/page-vars/transactionid.md). È supportato anche il campo abbreviato `data.__adobe.analytics.xact`. |
| `data.__adobe.analytics.zip` | La dimensione [Codice postale](../../components/dimensions/zip-code.md). |

{style="table-layout:auto"}
