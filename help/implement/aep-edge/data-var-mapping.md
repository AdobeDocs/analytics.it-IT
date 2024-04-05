---
title: Mappatura della variabile dell’oggetto dati su Adobe Analytics
description: Visualizza i campi dell’oggetto dati Experience Platform Edge mappati automaticamente sulle variabili di Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 97d830653bfb9ad68d1d885dd8dff0ecf49055d7
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 5%

---

# Mappatura della variabile dell’oggetto dati su Adobe Analytics

La tabella seguente mostra le variabili dell’oggetto dati mappate automaticamente da Adobe Experience Platform Edge Network in Adobe Analytics. Se utilizzi questi percorsi dei campi dell’oggetto dati, non è necessaria alcuna configurazione aggiuntiva per inviare dati ad Adobe Analytics.

L’utilizzo di questi campi è consigliato se intendi utilizzare il Customer Journey Analytics in futuro. Questo metodo di implementazione consente all’organizzazione di inviare dati ad Adobe utilizzando l’SDK web senza essere conforme a uno schema XDM. Quando la tua organizzazione è pronta per inviare dati a Adobe Experience Platform, puoi utilizzare [Mappatura dello stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/data-prep.html#mapping) per puntare i campi oggetto dati ai rispettivi campi XDM.

## Priorità di valore

La maggior parte dei campi oggetto dati in questa tabella coincidono con un [campo XDM mappato](xdm-var-mapping.md). Se imposti entrambi i `data` campo oggetto e il relativo campo XDM, il campo oggetto dati ha la priorità. Se utilizzi sia il campo oggetto XDM che il campo oggetto dati, l’Adobe consiglia di impostare eventi personalizzati utilizzando il campo oggetto dati. Se il campo `data.__adobe.analytics.events` sovrascrive tutti i campi oggetto XDM relativi agli eventi di e-commerce e personalizzati.

Alcuni campi dell’oggetto dati supportano anche i rispettivi [Valore parametro query](../validate/query-parameters.md) come valori abbreviati. È possibile utilizzare campi oggetto dati standard e campi oggetto dati abbreviati in modo intercambiabile, purché ciascuno di essi sia destinato a variabili univoche. Evitare di impostare contemporaneamente un campo oggetto dati standard e il relativo campo oggetto dati a sintassi abbreviata. L&#39;Adobe non può garantire quale campo ha la priorità.

## Mappatura campo oggetto dati

Gli aggiornamenti precedenti a questa tabella si trovano nella [cronologia dei commit su GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md) di questa pagina.

| Percorso campo oggetto dati | Variabile e descrizione di Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | Il [Altezza browser](../../components/dimensions/browser-height.md) dimensione. Campo abbreviato `data.__adobe.analytics.bh` è supportato anche. |
| `data.__adobe.analytics.browserWidth` | Il [Larghezza browser](../../components/dimensions/browser-width.md) dimensione. Campo abbreviato `data.__adobe.analytics.bw` è supportato anche. |
| `data.__adobe.analytics.campaign` | Il [Codice di tracciamento](../../components/dimensions/tracking-code.md) dimensione. Campo abbreviato `data.__adobe.analytics.v0` è supportato anche. |
| `data.__adobe.analytics.channel` | Il [Sezione del sito](../../components/dimensions/site-section.md) dimensione. Campo abbreviato `data.__adobe.analytics.ch` è supportato anche. |
| `data.__adobe.analytics.colorDepth` | Il [Profondità colore](../../components/dimensions/color-depth.md) dimensione. Campo abbreviato `data.__adobe.analytics.c` è supportato anche. |
| `data.__adobe.analytics.connectionType` | Il [Tipo di connessione](../../components/dimensions/connection-type.md) dimensione. Campo abbreviato `data.__adobe.analytics.ct` è supportato anche. |
| `data.__adobe.analytics.contextData` | [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | Il [Supporto per cookie](../../components/dimensions/cookie-support.md) dimensione. Campo abbreviato `data.__adobe.analytics.k` è supportato anche. |
| `data.__adobe.analytics.currencyCode` | Il [`currencyCode`](../vars/config-vars/currencycode.md) variabile di implementazione Campo abbreviato `data.__adobe.analytics.cc` è supportato anche. |
| `data.__adobe.analytics.dynamicVariablePrefix` | Il [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) variabile di implementazione |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) dimensioni. Campi abbreviati `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` sono supportati anche. |
| `data.__adobe.analytics.events` | [Eventi personalizzati](../../components/metrics/custom-events.md). Formatta questo campo in modo simile al [`events`](../vars/page-vars/events/events-overview.md) variabile di implementazione |
| `data.__adobe.analytics.javaEnabled` | Il [Java abilitato](../../components/dimensions/java-enabled.md) dimensione. Campo abbreviato `data.__adobe.analytics.v` è supportato anche. |
| `data.__adobe.analytics.latitude` | Aiuta a impostare [Posizione](../../components/dimensions/lifecycle-dimensions.md) dimensioni del ciclo di vita mobile. Campo abbreviato `data.__adobe.analytics.lat` è supportato anche. |
| `data.__adobe.analytics.linkName` | Il [Collegamento personalizzato](../../components/dimensions/custom-link.md), [Collegamento di download](../../components/dimensions/download-link.md), o [Collegamento di uscita](../../components/dimensions/exit-link.md) a seconda del valore in `data.__adobe.analytics.linkType`. Campo abbreviato `data.__adobe.analytics.pev2` è supportato anche. |
| `data.__adobe.analytics.linkURL` | Il [`linkURL`](../vars/config-vars/linkurl.md) variabile di implementazione Campo abbreviato `data.__adobe.analytics.pev1` è supportato anche. |
| `data.__adobe.analytics.linkType` | Determina il tipo di collegamento su cui è stato fatto clic. I valori validi includono `o` (Collegamenti personalizzati), `d` (Collegamenti di download) e `e` (Collegamenti di uscita). Campo abbreviato `data.__adobe.analytics.pe` è supportato anche. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) variabili di implementazione. Campi abbreviati `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` sono supportati anche. |
| `data.__adobe.analytics.longitude` | Guida alla configurazione di [Posizione](../../components/dimensions/lifecycle-dimensions.md) dimensioni del ciclo di vita mobile. Campo abbreviato `data.__adobe.analytics.lon` è supportato anche. |
| `data.__adobe.analytics.pageName` | La dimensione [Pagina](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | Il [URL della pagina](/help/components/dimensions/page-url.md) dimensione. Campo abbreviato `data.__adobe.analytics.g` è supportato anche. |
| `data.__adobe.analytics.pageType` | Il [`pageType`](../vars/page-vars/pagetype.md) variabile di implementazione |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) dimensioni. Campi abbreviati `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` sono supportati anche. |
| `data.__adobe.analytics.purchaseID` | Il [`purchaseID`](../vars/page-vars/purchaseid.md) variabile di implementazione |
| `data.__adobe.analytics.products` | Il [`products`](../vars/page-vars/products.md) variabile di implementazione, seguendo una formattazione simile. |
| `data.__adobe.analytics.referrer` | La dimensione [Referrer](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | Il [Risoluzione monitor](../../components/dimensions/monitor-resolution.md) dimensione. Campo abbreviato `data.__adobe.analytics.s` è supportato anche. |
| `data.__adobe.analytics.server` | La dimensione [Server](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | Il [`transactionID`](../vars/page-vars/transactionid.md) variabile di implementazione Campo abbreviato `data.__adobe.analytics.xact` è supportato anche. |
| `data.__adobe.analytics.zip` | Il [Codice postale](../../components/dimensions/zip-code.md) dimensione. |

{style="table-layout:auto"}
