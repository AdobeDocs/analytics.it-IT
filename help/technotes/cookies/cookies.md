---
title: Cookie di Adobe Analytics e del browser
description: Scopri come le misure di prevenzione del tracciamento influiscono sui cookie di terze parti e di prima parte impostati da Adobe Analytics.
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
role: Admin
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '1914'
ht-degree: 0%

---

# Cookie di Adobe Analytics e del browser

Questo documento spiega come le principali misure di prevenzione del tracciamento dei browser influiscono sui cookie di terze parti e di prima parte impostati da Adobe Analytics. Include informazioni sul programma ITP (Intelligent Tracking Prevention) di Apple e sulle limitazioni di Chrome sui cookie di terze parti tramite l’attributo SameSite.

## In che modo i browser hanno limitato l’utilizzo dei cookie?

>[!NOTE]
>[Analytics tra dispositivi](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html#cda) e [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html#comparing-cja-to-traditional-adobe-analytics) può unire i cookie utilizzando un ID persona, ad esempio un ID di accesso con hash, se disponibile.

### Limitazioni dei cookie di terze parti

I cookie utilizzati in un contesto di terze parti sono diventati ampiamente obsoleti. Firefox e Safari hanno iniziato a bloccare i cookie di terze parti per impostazione predefinita a partire rispettivamente dal 2019 e dal 2020. Chrome ha annunciato piani per interrompere il supporto dei cookie di terze parti a partire dal 2023. In tal caso, i cookie di terze parti saranno effettivamente inutilizzabili.

Inoltre, Chrome attualmente consente il funzionamento dei cookie in un contesto di terze parti solo se l’attributo &quot;SameSite&quot; è impostato su None e i cookie sono etichettati come sicuri, il che significa che possono essere utilizzati solo tramite HTTPS. Ulteriori informazioni sono disponibili nella sezione &quot;[Cos’è l’attributo per cookie SameSite e come influisce su Analytics?](#samesite-effect)&quot;

#### Quale Adobe influisce sui cookie di terze parti?

Il servizio ID visitatore utilizza il &quot;[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)Cookie &quot; per fornire un identificatore permanente ai visitatori tra domini diversi del cliente. Il servizio ID Analytics legacy, il cookie &quot;s_vi&quot;, è impostato come cookie di terze parti per le implementazioni che non utilizzano un dominio di raccolta CNAME personalizzato.

Nei browser in cui i cookie di terze parti sono bloccati, il tracciamento tra domini diversi non è disponibile.

### Limitazioni dei cookie di prime parti {#limitations-first-party-cookies}

I cookie di prime parti sono consentiti su tutti i principali browser. Tuttavia, Apple limita la durata dei cookie di prime parti impostati da Adobe tramite il proprio programma di tracciamento intelligente (ITP). Questo problema riguarda Safari e tutti i browser su iOS e iPadOS.

I cookie di prime parti di Adobe sono limitati alla scadenza di 7 giorni o, per i click-through che Apple determina provenire dai tracker, a una scadenza di 24 ore. Con una scadenza di 7 giorni, se un utente visita il tuo sito e restituisce entro sette giorni, la data di scadenza del cookie viene estesa di altri sette giorni. Tuttavia, se un utente visita il sito e ritorna tra otto giorni, viene trattato come un nuovo utente nella seconda visita.

Attualmente, i criteri ITP si applicano a tutti i cookie di prime parti impostati da Adobe, sia che si utilizzi il servizio ID visitatore che l’ID Analytics legacy (&quot;s_vi&quot; cookie). A un certo punto, questi criteri si applicavano solo ai cookie impostati lato client e non a quelli impostati lato server tramite un’implementazione CNAME. Nel novembre 2020, tuttavia, ITP è stato aggiornato per essere applicato anche alle implementazioni CNAME.

#### Calendario delle principali modifiche apportate ai criteri ITP {#ITP-timeline}

* Febbraio 2019 con [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/): la scadenza dei cookie lato client era limitata a sette giorni
* Aprile 2019 con [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/): i cookie lato client erano limitati a 24 ore per i clic degli annunci quando il dominio di riferimento era a) coinvolto nel tracciamento tra siti diversi e b) l’URL finale conteneva una stringa di query e/o un identificatore di frammento.
* Novembre 2020 con [CNAME Cloaking e difesa del tracciamento dei rimbalzi](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/): le limitazioni ITP sono state estese alle implementazioni CNAME.

I criteri ITP sono in continua evoluzione. Per informazioni aggiornate, consulta la documentazione di Apple [Prevenzione del tracciamento in Webkit](https://webkit.org/tracking-prevention).

#### Quale Adobe influisce sui cookie di prime parti?

Tutti i cookie di prime parti impostati da Adobe e le librerie JavaScript correlate sono interessati dai criteri ITP:

* [Cookie AMCV](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) impostato dalla libreria del servizio ID visitatore di Adobe Experience Cloud (ECID)
* La versione precedente di Analytics [Cookie &quot;s_vi&quot;](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) quando è configurato con la raccolta dati di prime parti utilizzando un CNAME
* La versione precedente di Analytics [Cookie &quot;s_fid&quot;](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it), che è il cookie di fallback utilizzato quando non è possibile impostare &quot;s_vi&quot;

#### Qual è l’impatto di ITP su Safari per Analytics?

L’impatto delle limitazioni ITP può variare in modo significativo, a seconda del comportamento degli utenti. Sono interessati solo i visitatori che utilizzano un browser interessato da ITP (ad esempio, Safari) e che ritornano dopo sette giorni di assenza. Se i visitatori non utilizzano un browser ITP o tornano entro sette giorni, l’operazione non ha alcun effetto su di loro. È importante esaminare i propri dati in Analytics per comprendere l’entità dell’impatto di questa limitazione. Per suggerimenti su come misurare l’impatto sui siti, consulta la sezione &quot;[Come posso determinare se le modifiche di Safari influiscono sulla mia attività?](#measure-itp-effect)&quot;

Se queste limitazioni influiscono sui dati, vedrai:

1. Un numero maggiore di visitatori conta i visitatori di ritorno che vengono trattati come nuovi visitatori perché i loro cookie sono scaduti. Sono interessate anche tutte le metriche basate sulla metrica Visitatore (come Vendite per visitatore).
2. Modifiche all’attribuzione. L’attribuzione si basa sul collegamento degli eventi di conversione alle attività precedenti dello stesso visitatore. Una volta scaduto il cookie, gli eventi successivi vengono associati a un nuovo visitatore. Le attività del nuovo visitatore non possono essere collegate a quelle del visitatore precedente.

>[!NOTE]
>
>Le tecnologie ITP attualmente non si applicano ai browser incorporati nelle app mobili.

## Qual è la differenza tra cookie di terze parti e cookie di prima parte?

### Cookie di terze parti

I cookie di terze parti non vengono creati dai siti web visitati dagli utenti.

Anche se i browser al momento trattano tutti i cookie di terze parti nello stesso modo e li memorizzano, i cookie di terze parti possono comportarsi in modi diversi. Con l’implementazione dei cookie di terze parti di Analytics di un cliente, i browser memorizzano l’Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=it) ID come cookie di terze parti, ma il client effettua chiamate solo ad Adobi e non a domini di terze parti troppo sconosciuti o sospetti. Questo cookie fornisce identificatori permanenti tra domini diversi e consente contenuti protetti (HTTPS). Per ulteriori informazioni, consulta [Cookie e il servizio Experienci Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html).

All’interno delle implementazioni di Analytics, i cookie di terze parti vengono utilizzati per il tracciamento tra domini diversi e per casi di utilizzo pubblicitari, inclusi gli annunci di retargeting. I cookie di terze parti ti consentono di identificare i visitatori quando visitano diversi domini di tua proprietà o quando vengono visualizzati annunci su siti di tua proprietà.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### Cookie di prime parti

I cookie di prime parti sono specifici del dominio e vengono creati dai siti web dei clienti e memorizzati nei browser client quando gli utenti visitano i siti web. Tutti i browser generalmente accettano i cookie di prime parti, anche se [Safari limita la scadenza di alcuni tipi di cookie di prima parte](#limitations-first-party-cookies).

All’interno delle implementazioni di Analytics, i cookie di prime parti vengono utilizzati per identificare gli utenti quando si trovano sul sito e quindi supportano tutte le analisi delle attività degli utenti. Non è necessario utilizzare cookie di terze parti per comprendere le attività sul sito.

Per ulteriori informazioni, consulta [Informazioni sui cookie di prime parti](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it).

![Confronto dei cookie](/help/technotes/assets/cookies2.png)

## Cos’è l’attributo per cookie SameSite e come influisce sui cookie di Analytics? {#samesite-effect}

Con il rilascio del browser Chrome 80 a febbraio 2020, e delle versioni successive dei browser Firefox e Edge, l’attributo per cookie SameSite applica la specifica per tre valori diversi che determinano se i cookie possono essere utilizzati in un contesto di terze parti:

* `None`: questa impostazione abilita l’accesso tra siti e consente il passaggio dei cookie in un contesto di terze parti. Per specificare questo attributo, è necessario specificare anche `Secure` e tutte le richieste del browser devono seguire HTTPS. Ad esempio, quando imposti il cookie, associ i valori dell’attributo come segue: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Se non etichettati correttamente, i cookie non sono utilizzabili dai browser più recenti e vengono rifiutati.

* `Lax`: consente l’invio di richieste tra siti con cookie dello stesso sito solo per la navigazione di livello superiore con *sicuro* (sola lettura, ad esempio `GET`) Metodi HTTP.

* `Strict`: il cookie dello stesso sito non viene inviato per richieste di siti web di terze parti. Il cookie viene inviato solo se il sito per il cookie corrisponde al sito nella barra degli URL.

Il comportamento predefinito in queste versioni del browser consiste nel trattare i cookie che non hanno specificato `SameSite` attributo uguale a `SameSite=Lax`.

### In che modo Analytics gestisce gli attributi dei cookie SameSite?

Per i clienti che utilizzano il servizio ID visitatore, i cookie hanno le proprietà `SameSite=None` e `secure` è impostato per impostazione predefinita e consente a questi cookie di supportare casi di utilizzo di terze parti.

Per i clienti che utilizzano gli identificatori legacy di Analytics (&quot;s_vi&quot; e &quot;s_fid&quot; cookie), i cookie sono impostati anche per abilitare casi di utilizzo di terze parti con domini di raccolta standard: adobedc.net, 2o7.net e omtrdc.net. Per i clienti che utilizzano un’implementazione CNAME, Analytics imposta `SameSite=Lax`.

>[!NOTE]
>
>Se possiedi più domini e utilizzi lo stesso CNAME per la raccolta dati in tutti i tuoi domini, il cookie viene trattato come un cookie di terze parti su tali altri domini. Se utilizzi gli identificatori Analytics precedenti, potrebbe essere utile aggiornare le impostazioni su `SameSite=None` in modo che questi cookie possano essere condivisi tra i siti. Consulta &quot;[Modificare il valore SameSite quando si utilizza un CNAME per più domini](#samesite-one-cname)&quot; nella sezione successiva per ulteriori informazioni.

Per i browser identificati da Google come cookie con gestione errata quando `SameSite` è impostato su `None`, `SameSite` viene invece lasciato non impostato.

Nella tabella seguente sono riepilogati gli attributi SameSite per i cookie di Analytics:

![Tabella cookie](/help/technotes/assets/cookies1.png)

### In che modo i requisiti dell&#39;indirizzo del sito per l&#39;attributo SameSite possono essere soddisfatti?

#### Distribuisci tutte le pagine del sito con HTTPS

Conferma che la configurazione JavaScript utilizzi HTTPS per tutte le chiamate ai servizi Adobe.

Se il sito utilizza il servizio ID visitatore di Experience Cloud, il servizio reindirizza le chiamate HTTP di terze parti al relativo endpoint HTTPS, il che può aumentare la latenza ma significa che non è necessario modificare la configurazione.

#### Modificare il valore SameSite quando si utilizza un CNAME per più domini {#samesite-one-cname}

>[!NOTE]
>
>Le seguenti informazioni si riferiscono solo ai siti che non utilizzano il servizio ID visitatore di Experience Cloud.

Se disponi di un’implementazione CNAME impostata nello stesso dominio del sito web, il cookie viene creato in un contesto di prime parti e non è necessario apportare modifiche.

Tuttavia, se possiedi più domini e utilizzi lo stesso CNAME per la raccolta dati in tutti i tuoi domini, il cookie viene trattato come un cookie di terze parti su tali altri domini. Con Chrome 80 e versioni successive, non è più visibile su questi altri domini. Per rendere il comportamento più simile in tutti i browser, Analytics ha impostato esplicitamente il `SameSite` valore di questo cookie per `Lax`. Se utilizzi questo cookie in un contesto di terze parti semplice, devi impostare il cookie con `SameSite=None` , il che significa anche che devi sempre utilizzare HTTPS. Se non lo hai già fatto, contatta l’Assistenza clienti di Adobe per far sì che il valore SameSite venga modificato per i CNAME protetti.

## Come posso determinare se le modifiche di Safari influiscono sulla mia attività? {#measure-itp-effect}

L’Adobe consiglia ai clienti di misurare l’impatto all’interno della propria azienda prima di modificare la raccolta dei dati. Puoi utilizzare Analysis Workspace per misurare l’impatto della prevenzione del tracciamento ITP sulla tua attività individuale:

* Misura la percentuale di traffico proveniente da browser gestiti da ITP:

   1. Crea un segmento per vedere quanti visitatori utilizzano una piattaforma ITP.

      >[!NOTE]
      >
      >I browser specifici interessati da ITP dipendono dall’utilizzo o meno di un’implementazione CNAME. Consulta &quot;[Calendario delle principali modifiche apportate ai criteri ITP](#ITP-timeline)&quot; per maggiori dettagli.

      ![Segmento per i visitatori ITP](/help/technotes/assets/itp-visitor-segment.png)

   2. Applica il segmento al numero di visite per comprendere l’utilizzo relativo di Safari nella tua base di utenti. Questo ti consente di creare una tabella come questa:

      ![Percentuale di visite da parte dei visitatori ITP](/help/technotes/assets/visits-vs-safari-visits.png)

* Misura la percentuale di visitatori che utilizzano browser non Safari e che non ritornano entro sette giorni. Se i visitatori non Safari ritornano ripetutamente entro sette giorni, il traffico Safari potrebbe non essere influenzato in modo significativo.

   1. Crea un segmento come quello seguente per il traffico non Safari.

      ![Segmento per i visitatori che ritornano dopo sette giorni](/help/technotes/assets/visits-after-seven-days.png)

   2. Applica il segmento al numero di visite per comprendere l’utilizzo relativo di Safari nella tua base di utenti. Questo ti consente di creare una tabella come questa:

      ![Percentuale di visitatori che ritornano dopo sette giorni](/help/technotes/assets/percent-visits-after-seven-days.png)

### Modi per regolare i dati durante il reporting

Se la tua azienda è interessata dalla prevenzione del tracciamento ITP, puoi prendere in considerazione le seguenti misure per adeguare i dati durante la generazione del rapporto.

* Crea un segmento per filtrare gli utenti ITP.

  ![Segmento per visitatori non ITP](/help/technotes/assets/non-itp-visitor-segment.png)

* Crea una metrica calcolata per regolare l’inflazione dei visitatori noti.

  ![Metrica calcolata per la rettifica in base all’inflazione dei visitatori](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Opzioni per attenuare l’effetto delle limitazioni dei cookie del browser](cookieless.md)
>[Impatto del nuovo framework per la trasparenza del tracciamento delle app di Apple su Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
