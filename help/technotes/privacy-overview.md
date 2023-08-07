---
description: Panoramica dei dati raccolti da Adobe Analytics e altre considerazioni sulla privacy.
keywords: privacy
title: Panoramica sulla privacy
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: ee0bf5beeac3c9780eb0c8420845114f7e840aec
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 12%

---

# Panoramica sulla privacy

I visitatori possono saperne di più sulle finalità per cui Adobe utilizza le informazioni raccolte nel [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy.html). È compito dell’organizzazione divulgare in che modo utilizza i prodotti e i servizi Adobe, in quanto l’organizzazione controlla esclusivamente l’implementazione dei servizi di Adobe. La tua organizzazione è responsabile del rispetto della tua informativa sulla privacy, del contratto di assistenza con Adobe e di tutte le leggi applicabili.

L’Adobe consiglia vivamente di attenersi ai seguenti concetti generali:

* **Evita di raccogliere informazioni personali in Adobe Analytics.** Le variabili personalizzate ti consentono di raccogliere praticamente tutto ciò a cui puoi accedere; tuttavia, devi anche considerare l’informativa sulla privacy della tua organizzazione e le leggi applicabili.
* **Fornisci ai visitatori informazioni facili da trovare e da comprendere sulle informazioni di rinuncia.** Consentire loro di rinunciare a qualsiasi cosa non sia strettamente necessaria. La maggior parte dei paesi dell’Unione europea non considera strettamente necessari i cookie di analisi.

## Disaggregazione della raccolta dati

Adobe Analytics raccoglie o può raccogliere automaticamente i seguenti tipi di dati:

| Tipo di dati | Dettagli | Variabili di esempio contenenti questi dati |
| --- | --- | --- |
| Nomi di pagina o URL di pagine web sul sito | Sempre raccolti. Per ogni hit è necessario specificare l’URL o il nome della pagina. | [Pagina](../components/dimensions/page.md), [URL della pagina](../components/dimensions/page-url.md) |
| Dati temporizzati | Sempre raccolti. La marca temporale è necessaria per la raccolta dei dati e i dati basati sul tempo derivano dalla marca temporale. | [Tempo trascorso sulla pagina](../components/dimensions/time-spent-on-page.md), [Ora del giorno](../components/dimensions/hour-of-day.md), [AM/PM](../components/dimensions/am-pm.md), [Giorno feriale/Fine settimana](../components/dimensions/weekday-weekend.md), [Giorno della settimana](../components/dimensions/day-of-week.md), [Mese dell’anno](../components/dimensions/month-of-year.md) |
| Dati da pagine web su altri siti | L’Adobe non può raccogliere dati su siti non affiliati in cui non è possibile modificare il codice sorgente del sito web. L’AppMeasurement raccoglie automaticamente l’URL di riferimento quando un visitatore arriva al tuo sito web. Puoi personalizzare l’implementazione per raccogliere i dati all’interno delle stringhe di query dopo che queste sono arrivate sul sito. | [Referrer](../components/dimensions/referrer.md), [Dominio di riferimento](../components/dimensions/referring-domain.md) |
| ID visitatore anonimo | AppMeasurement genera e fa riferimento automaticamente a un ID visitatore per ogni browser che visita il tuo sito. Questo ID è memorizzato in un cookie. Se i cookie non sono disponibili per una determinata implementazione, Adobe Analytics utilizza un metodo di fallback per l’identificazione dei visitatori che utilizza l’indirizzo IP e la stringa dell’agente utente. Consulta [Cookie di Adobe Analytics e del browser](cookies/cookies.md) per ulteriori informazioni. | [Visitatori univoci](../components/metrics/unique-visitors.md) |
| ID visitatore identificabile | L’Adobe non raccoglie automaticamente gli ID visitatore personalizzati. Tuttavia, puoi personalizzare l’implementazione per raccogliere questi dati. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| Termini di ricerca esterni | L’AppMeasurement tenta di raccogliere automaticamente questi dati in base all’URL di riferimento. Tuttavia, molti moderni motori di ricerca non includono più queste informazioni. | [Parola chiave di ricerca](../components/dimensions/search-keyword.md) |
| Termini di ricerca interni | L’Adobe non raccoglie automaticamente i dati di ricerca interni. Tuttavia, puoi personalizzare l’implementazione per raccogliere questi dati ed è una pratica comune per le organizzazioni che utilizzano Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Specifiche del computer e del browser | AppMeasurement raccoglie automaticamente i suggerimenti del browser a bassa entropia, ad esempio il tipo di browser, il tipo di sistema operativo e se il dispositivo è desktop o mobile. La configurazione è necessaria per raccogliere hint ad alta entropia, ad esempio la versione/build specifica del browser, il modello del dispositivo o la versione del sistema operativo. Consulta [Panoramica degli hint client](client-hints.md) per ulteriori informazioni. | [Browser](../components/dimensions/browser.md), [Sistema operativo](../components/dimensions/operating-systems.md), [Dimensioni per dispositivi mobili](../components/dimensions/mobile-dimensions.md), [Risoluzione monitor](../components/dimensions/monitor-resolution.md) |
| Informazioni di geolocalizzazione | Adobe offre la possibilità di abilitare o disabilitare la raccolta di dati di geolocalizzazione per ciascun sito web o app (a livello di suite di rapporti). Molti tipi di implementazione, tra cui AppMeasurement, raccolgono automaticamente questi dati. | [Città](../components/dimensions/cities.md), [Aree geografiche](../components/dimensions/regions.md), [Paesi](../components/dimensions/countries.md) |
| Indirizzo IP | Adobe offre la possibilità di oscurare l’ultimo ottetto o di oscurare completamente l’indirizzo IP del visitatore durante l’archiviazione di tali dati. Per impostazione predefinita, i clienti EMEA hanno in genere un indirizzo IP completamente oscurato. L’indirizzo IP non è disponibile come dimensione in Adobe Analytics; è incluso solo nei dati non elaborati ([Feed dati](../export/analytics-data-feed/data-feed-overview.md)). | Nessuno |
| Informazioni sul modulo fornite sul sito | Tutti i tipi di implementazione richiedono la configurazione per raccogliere questi dati. Puoi includere questi dati nelle variabili personalizzate. | [eVar](../components/dimensions/evar.md) |
| Annunci o collegamenti selezionati sul sito | Raccolto automaticamente se si utilizza AppMeasurement. Con l’Activity Map abilitata sono disponibili informazioni aggiuntive, ad esempio la posizione dei clic. | [Activity Map](../analyze/activity-map/activity-map.md), [Collegamento di uscita](../components/dimensions/exit-link.md), [Collegamento di download](../components/dimensions/download-link.md) |
| Prodotti acquistati sul sito | Tutti i tipi di implementazione richiedono la configurazione per raccogliere questi dati. Adobe offre diverse variabili predefinite per memorizzare queste informazioni. | [Prodotto](../components/dimensions/product.md), [Ordini](../components/metrics/orders.md), [Ricavi](../components/metrics/revenue.md) |

{style="table-layout:auto"}

Consulta il menu di navigazione in [Panoramica sui Dimension](../components/dimensions/overview.md) e [Panoramica delle metriche](../components/metrics/overview.md) per altre variabili in cui Adobe può potenzialmente raccogliere i dati.
