---
description: Panoramica dei dati raccolti da Adobe Analytics e altre considerazioni sulla privacy.
keywords: privacy
title: Panoramica sulla privacy
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 04f8602ccfa7fd2d1d2f3c56f477aeee3739c563
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 3%

---

# Panoramica sulla privacy

Adobe desidera abilitare la tua organizzazione in modo da poter rispettare le leggi e le normative sulla privacy applicabili. Consulta [Privacy di Adobe Experience Cloud](https://www.adobe.com/it/privacy/experience-cloud.html) per ulteriori informazioni. Per quanto riguarda Adobe Analytics, Adobe agisce come &quot;responsabile del trattamento dei dati&quot; e tu sei il &quot;titolare del trattamento&quot; (o equivalente in base alle leggi applicabili sulla privacy e la protezione dei dati). È compito dell’organizzazione divulgare in che modo utilizza i prodotti e i servizi di Adobe, in quanto l’organizzazione controlla esclusivamente l’implementazione delle soluzioni di Adobe. La tua organizzazione è responsabile del rispetto della tua informativa sulla privacy, del contratto di assistenza con Adobe e di tutte le leggi applicabili.

L’Adobe consiglia vivamente di attenersi ai seguenti concetti generali:

* **Se raccogli dati personali, accertati di rispettare le leggi e le normative sulla privacy.** Le variabili personalizzate ti consentono di raccogliere praticamente tutto ciò a cui puoi accedere; tuttavia, devi anche considerare l’informativa sulla privacy della tua organizzazione e le leggi applicabili.
* **Fornisci ai clienti informazioni sulla privacy facili da trovare e da comprendere per la tua organizzazione.** Informazioni utili includono collegamenti di rinuncia, come vengono utilizzati i dati di navigazione e come utilizzi o prevedi di utilizzare i servizi di Adobe.
* **Stai attento alle leggi locali e alle leggi internazionali che ti riguardano.** Se la tua organizzazione opera su scala globale, possono essere applicate alcune leggi internazionali.

## Disaggregazione della raccolta dati

Adobe offre più librerie di raccolta dati per facilitare l’invio di dati ad Adobe. Alcuni esempi degni di nota:

* **AppMeasurement**: libreria progettata per inviare dati direttamente ad Adobe Analytics.
* **SDK per web**: libreria progettata per inviare dati alla rete Edge di Adobe Experience Platform, che in seguito li inoltra ad Adobe Analytics.
* **Tag**: interfaccia utente basata su web che consente di configurare l’implementazione senza richiedere l’accesso al codice sorgente di un sito web o di un’app oltre l’implementazione iniziale dei tag. Le estensioni sono disponibili sia per AppMeasurement che per Web SDK.

Adobe Analytics può raccogliere i seguenti tipi di dati:

| Tipo di dati | Dettagli | Variabili di esempio contenenti questi dati |
| --- | --- | --- |
| Nomi di pagina o URL di pagine web sul sito | Raccolto sempre affinché Adobe Analytics funzioni. Per ogni hit è necessario un URL o un nome di pagina. | [Pagina](../components/dimensions/page.md), [URL della pagina](../components/dimensions/page-url.md) |
| Dati temporizzati | Raccolto sempre affinché Adobe Analytics funzioni. Per la raccolta dei dati è necessaria una marca temporale e i dati basati sul tempo derivano dalla marca temporale. | [Tempo trascorso sulla pagina](../components/dimensions/time-spent-on-page.md), [Ora del giorno](../components/dimensions/hour-of-day.md), [AM/PM](../components/dimensions/am-pm.md), [Giorno feriale/Fine settimana](../components/dimensions/weekday-weekend.md), [Giorno della settimana](../components/dimensions/day-of-week.md), [Mese dell’anno](../components/dimensions/month-of-year.md) |
| Dati da pagine web su altri siti | L’Adobe non può raccogliere dati su siti non affiliati in cui non è possibile modificare il codice sorgente del sito web o dell’app. Le librerie di raccolta dati raccolgono l’URL di riferimento per impostazione predefinita quando un visitatore arriva al tuo sito web. Puoi personalizzare l’implementazione per raccogliere i dati nelle stringhe di query dopo l’arrivo dei visitatori del sito web o dell’app. | [Referrer](../components/dimensions/referrer.md), [Dominio di riferimento](../components/dimensions/referring-domain.md) |
| ID visitatore anonimo | Le librerie di raccolta dati generano e fanno riferimento a un ID visitatore per ogni browser che visita il sito. Questo ID è memorizzato in un cookie. Se per qualsiasi motivo una libreria di raccolta dati non può impostare i cookie, utilizza un metodo di fallback per l’identificazione dei visitatori che utilizza l’indirizzo IP e la stringa dell’agente utente. Consulta [Cookie di Adobe Analytics e del browser](cookies/cookies.md) per ulteriori informazioni. | [Visitatori univoci](../components/metrics/unique-visitors.md) |
| ID visitatore identificabile | L’Adobe non raccoglie automaticamente gli ID visitatore personalizzati. Tuttavia, puoi personalizzare l’implementazione per raccogliere questi dati. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| Termini di ricerca esterni | I dati di ricerca esterna includono parole chiave provenienti da motori di ricerca. Le librerie di raccolta dati cercano questi dati in base all’URL di riferimento. Tuttavia, molti moderni motori di ricerca non includono più queste informazioni. | [Parola chiave di ricerca](../components/dimensions/search-keyword.md) |
| Termini di ricerca interni | I dati di ricerca interni includono parole chiave provenienti dalle funzionalità di ricerca del sito web o dell’app. L’Adobe non raccoglie automaticamente i dati di ricerca interni. Tuttavia, puoi personalizzare l’implementazione per raccogliere questi dati. Questa procedura è comune per le organizzazioni che utilizzano Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Specifiche del computer e del browser | AppMeasurement raccoglie automaticamente i suggerimenti del browser a bassa entropia, ad esempio il tipo di browser, il tipo di sistema operativo e se il dispositivo è desktop o mobile. La configurazione personalizzata è necessaria per raccogliere hint ad alta entropia, ad esempio la versione/build specifica del browser, il modello del dispositivo o la versione del sistema operativo. Consulta [Panoramica degli hint client](client-hints.md) per ulteriori informazioni. | [Browser](../components/dimensions/browser.md), [Sistema operativo](../components/dimensions/operating-systems.md), [Dimensioni per dispositivi mobili](../components/dimensions/mobile-dimensions.md), [Risoluzione monitor](../components/dimensions/monitor-resolution.md) |
| Informazioni di geolocalizzazione | Adobe offre la possibilità di abilitare o disabilitare la raccolta di dati di geolocalizzazione per ciascun sito web o app (a livello di suite di rapporti). La raccolta dati di geolocalizzazione è attivata per impostazione predefinita. Le librerie di raccolta dati includono la geolocalizzazione, se abilitata. | [Città](../components/dimensions/cities.md), [Aree geografiche](../components/dimensions/regions.md), [Paesi](../components/dimensions/countries.md) |
| Indirizzo IP | Adobe offre la possibilità di oscurare l’ultimo ottetto o di oscurare completamente l’indirizzo IP del visitatore durante la memorizzazione di questi dati. Per impostazione predefinita, l’impostazione dell’indirizzo IP dei clienti EMEA è completamente offuscata. Indipendentemente dall’impostazione di offuscamento, l’indirizzo IP non è disponibile come dimensione in Adobe Analytics; è incluso solo in [Feed dati](../export/analytics-data-feed/data-feed-overview.md). | Nessuno |
| Informazioni sul modulo fornite sul sito | Tutti i tipi di implementazione richiedono la configurazione per raccogliere questi dati. Puoi includere questi dati nelle variabili personalizzate. | [eVar](../components/dimensions/evar.md) |
| Annunci o collegamenti selezionati sul sito | Raccolto per impostazione predefinita se si utilizza una libreria di raccolta dati. Quando abiliti Activity Map, sono disponibili informazioni aggiuntive, ad esempio la posizione dei clic. | [Activity Map](../analyze/activity-map/activity-map.md), [Collegamento di uscita](../components/dimensions/exit-link.md), [Collegamento di download](../components/dimensions/download-link.md) |
| Prodotti acquistati sul sito | Tutti i tipi di implementazione richiedono la configurazione per raccogliere questi dati. Adobe offre diverse variabili predefinite per raccogliere queste informazioni. | [Prodotto](../components/dimensions/product.md), [Ordini](../components/metrics/orders.md), [Ricavi](../components/metrics/revenue.md) |

{style="table-layout:auto"}

Consulta il menu di navigazione in [Panoramica sui Dimension](../components/dimensions/overview.md) e [Panoramica delle metriche](../components/metrics/overview.md) per altre variabili in cui Adobe può potenzialmente raccogliere i dati.

## Percorsi di elaborazione dati

Adobe gestisce tre posizioni di elaborazione dei dati per Adobe Analytics. Questi siti ricevono dati non elaborati e li elaborano in una suite di rapporti ottimizzata per l’archiviazione dei dati e il recupero dei rapporti. Queste posizioni di elaborazione dei dati risiedono in **Oregon**, **Londra**, e **Singapore**. Consulta [Panoramica sulla sicurezza di Adobe Analytics](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf) per ulteriori informazioni.
