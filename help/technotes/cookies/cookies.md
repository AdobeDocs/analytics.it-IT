---
title: Cookie di Adobe Analytics e del browser
description: Scopri come le misure di prevenzione del tracciamento influiscono sui cookie di terze parti e di prime parti impostati da Adobe Analytics.
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
role: Admin
source-git-commit: ac9221bd7d9397ed0f085245663f1f0056f7d68f
workflow-type: tm+mt
source-wordcount: '1909'
ht-degree: 100%

---

# Cookie di Adobe Analytics e del browser

Questo documento spiega come le principali misure di prevenzione del tracciamento dei browser influiscono sui cookie di terze parti e di prime parti impostati da Adobe Analytics. Include informazioni sul programma ITP (Intelligent Tracking Prevention) di Apple e sulle limitazioni di Chrome sui cookie di terze parti tramite l’attributo SameSite.

## In che modo i browser hanno limitato l’utilizzo dei cookie?

>[!NOTE]
>[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=it#cda) e [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it#comparing-cja-to-traditional-adobe-analytics) possono unire i cookie utilizzando un ID persona, ad esempio un ID di accesso con hash, se disponibile.

### Limitazioni dei cookie di terze parti

I cookie utilizzati in un contesto di terze parti sono diventati ampiamente obsoleti. Firefox e Safari hanno iniziato a bloccare i cookie di terze parti per impostazione predefinita a partire dal 2019 e dal 2020, rispettivamente. Chrome ha annunciato piani per interrompere il supporto dei cookie di terze parti a partire dal 2023. Quando succederà, i cookie di terze parti saranno effettivamente inutilizzabili.

Inoltre, Chrome attualmente consente il funzionamento dei cookie in un contesto di terze parti solo se l’attributo “SameSite” è impostato su Nessuno e i cookie sono etichettati come sicuri, ovvero che possono essere utilizzati solo tramite HTTPS. Ulteriori informazioni sono disponibili nella sezione “[Che cos’è l’attributo dei cookie SameSite e come influisce su Analytics?](#samesite-effect)”

#### Quali cookie di terze parti di Adobe sono interessati?

Il servizio ID visitatore utilizza il cookie “[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=it)” per fornire un identificatore permanente ai visitatori tra domini diversi del cliente. Il servizio ID Analytics legacy, il cookie “s_vi”, è impostato come cookie di terze parti per le implementazioni che non utilizzano un dominio di raccolta CNAME personalizzato.

Sui browser in cui i cookie di terze parti vengono bloccati, il tracciamento tra domini diversi non sarà disponibile.

### Limitazioni dei cookie di prime parti {#limitations-first-party-cookies}

I cookie di prime parti sono consentiti su tutti i principali browser. Tuttavia, Apple limita la durata dei cookie di prime parti impostati da Adobe tramite il proprio programma Intelligent Tracking Prevention (ITP). Questo problema riguarda Safari e tutti i browser su iOS e iPadOS.

I cookie di prime parti di Adobe sono limitati alla scadenza di 7 giorni o, per i click-through che Apple determina provenire dai tracker, a una scadenza di 24 ore. Con una scadenza di 7 giorni, se un utente visita il tuo sito e ritorna entro sette giorni, la data di scadenza del cookie viene estesa di altri sette giorni. Tuttavia, se un utente visita il sito e ritorna entro otto giorni, nella seconda visita viene trattato come un nuovo utente.

Attualmente, i criteri ITP si applicano a tutti i cookie di prime parti impostati da Adobe, sia che si utilizzi il servizio ID visitatore che l’ID Analytics legacy (“s_vi&quot; cookie”). In un certo periodo, questi criteri si applicavano solo ai cookie impostati lato client e non a quelli impostati lato server tramite un’implementazione CNAME. Nel novembre 2020, tuttavia, il programma ITP è stato aggiornato per essere applicato anche alle implementazioni CNAME.

#### Timeline delle principali modifiche apportate ai criteri ITP {#ITP-timeline}

* Febbraio 2019 con [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/): la scadenza dei cookie lato client era limitata a sette giorni
* Aprile 2019 con [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/): i cookie lato client erano limitati a 24 ore per i clic sugli annunci quando il dominio di riferimento era a) coinvolto nel tracciamento tra siti diversi e b) l’URL finale conteneva una stringa di query e/o un identificatore di frammento.
* Novembre 2020 con [CNAME Cloaking and Bounce Tracking Defense](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/): le limitazioni ITP sono state estese alle implementazioni CNAME.

I criteri ITP sono in continua evoluzione. Per criteri più recenti, consulta la documentazione di Apple [Prevenzione del tracciamento in Webkit](https://webkit.org/tracking-prevention).

#### Quali cookie di prime parti di Adobe sono interessati?

Tutti i cookie di prime parti impostati da Adobe e le librerie JavaScript correlate sono interessati dai criteri ITP:

* [Cookie “AMCV”](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=it) impostati dalla libreria del servizio ID visitatore di Adobe Experience Cloud (ECID)
* La versione legacy del [cookie “s_vi”](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) di Analytics quando è configurato con la raccolta dati di prime parti mediante un CNAME
* La versione legacy del [cookie “s_fid”](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) di Analytics, ovvero il cookie di fallback utilizzato quando non è possibile impostare “s_vi”

#### Qual è l’impatto del programma ITP su Safari per Analytics?

L’impatto delle limitazioni ITP può variare in modo significativo, a seconda del comportamento degli utenti. Sono interessati solo i visitatori che utilizzano un browser con funzionalità ITP (ad esempio, Safari) e che ritornano dopo sette giorni di assenza. Se i visitatori non utilizzano un browser ITP o tornano entro sette giorni, la funzionalità non ha alcun effetto su di loro. Per comprendere l’entità dell’impatto di questa limitazione, è importante esaminare i propri dati in Analytics. Per suggerimenti su come misurare l’impatto sui siti, consulta la sezione “[Come posso scoprire se le modifiche di Safari influiscono sulla mia azienda?](#measure-itp-effect)”

Se queste limitazioni influiscono sui dati, vedrai:

1. un numero maggiore di visitatori in qualità di visitatori di ritorno che vengono trattati come nuovi visitatori perché i loro cookie sono scaduti. Sono interessate anche tutte le metriche basate sulla metrica Visitatore (come Vendite per visitatore).
2. Modifiche dell’attribuzione. L’attribuzione si basa sul collegamento degli eventi di conversione alle attività precedenti dello stesso visitatore. Una volta scaduto il cookie, gli eventi successivi vengono associati a un nuovo visitatore. Le attività del nuovo visitatore non possono essere collegate a quelle del visitatore precedente.

>[!NOTE]
>
>Al momento, le tecnologie ITP non si applicano ai browser incorporati nelle app mobili.

## Qual è la differenza tra cookie di terze parti e cookie di prime parti?

### Cookie di terze parti

I cookie di terze parti non vengono creati dai siti web visitati dagli utenti.

Anche se i browser al momento trattano tutti i cookie di terze parti nello stesso modo e li memorizzano, i cookie di terze parti possono comportarsi in modi diversi. Con l’implementazione dei cookie di terze parti di Analytics di un cliente, i browser memorizzano l’ID [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=it) di Adobe come cookie di terze parti, ma il client effettua chiamate solo ad Adobe e non a domini di terze parti troppo sconosciuti o sospetti. Questo cookie fornisce identificatori permanenti tra domini diversi e consente contenuti protetti (HTTPS). Per ulteriori informazioni, consulta [Cookie e Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=it).

All’interno delle implementazioni di Analytics, i cookie di terze parti vengono utilizzati per il tracciamento tra domini diversi e per casi di utilizzo pubblicitari, inclusi gli annunci di retargeting. I cookie di terze parti ti consentono di identificare i visitatori quando visitano diversi domini di tua proprietà o quando vengono visualizzati annunci su siti che non possiedi.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### Cookie di prime parti

I cookie di prime parti sono specifici del dominio e vengono creati dai siti web dei clienti e memorizzati nei browser client quando gli utenti visitano i siti web. In genere, tutti i browser accettano i cookie di prime parti, anche se [Safari limita la scadenza di alcuni tipi di cookie di prime parti](#limitations-first-party-cookies).

All’interno delle implementazioni di Analytics, i cookie di prime parti vengono utilizzati per identificare gli utenti quando si trovano sul sito e quindi supportano tutte le analisi delle attività degli utenti. Non è necessario utilizzare cookie di terze parti per comprendere le attività sul sito.

Per ulteriori informazioni, consulta [Informazioni sui cookie di prime parti](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it).

![Confronto tra cookie](/help/technotes/assets/cookies2.png)

## Che cos’è l’attributo per cookie SameSite e come influisce sui cookie di Analytics? {#samesite-effect}

Con il rilascio del browser Chrome 80 a febbraio 2020, e delle versioni successive dei browser Firefox e Edge, l’attributo per cookie SameSite applica la specifica per tre valori diversi che determinano se i cookie possono essere utilizzati in un contesto di terze parti:

* `None`: questa impostazione abilita l’accesso tra siti e consente il passaggio dei cookie in un contesto di terze parti. Per specificare questo attributo, è necessario specificare anche `Secure` e tutte le richieste del browser devono seguire HTTPS. Ad esempio, quando imposti il cookie, associ i valori dell’attributo come segue: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Se non etichettati correttamente, i cookie non sono utilizzabili dai browser più recenti e vengono rifiutati.

* `Lax`: consente l’invio di richieste tra siti con cookie dello stesso sito solo per la navigazione di livello superiore con metodi HTTP *sicuri* (sola lettura, ad esempio `GET`).

* `Strict`: il cookie dello stesso sito non viene inviato per richieste di siti web di terze parti. Il cookie viene inviato solo se il sito del cookie corrisponde al sito nella barra URL.

Il comportamento predefinito in queste versioni del browser consiste nel trattare i cookie che non hanno un attributo `SameSite` specifico uguale a `SameSite=Lax`.

### In che modo Analytics gestisce gli attributi dei cookie SameSite?

Per chi utilizza il servizio ID visitatore, i cookie hanno le proprietà `SameSite=None` e `secure` impostate come predefinite, che consente a questi cookie di supportare casi di utilizzo di terze parti.

Per chi utilizza gli identificatori legacy di Analytics (cookie `s_vi` e `s_fid`), i cookie sono impostati anche per abilitare casi d’uso di terze parti con domini di raccolta standard: `adobedc.net`, `2o7.net` e `omtrdc.net`. Per chi utilizza un’implementazione CNAME, Analytics imposta `SameSite=Lax`.

>[!NOTE]
>
>Se possiedi più domini e utilizzi lo stesso CNAME per la raccolta dati in tutti i tuoi domini, verrà trattato come cookie di terze parti per gli altri domini. Se utilizzi gli identificatori Analytics legacy, potrebbe essere utile aggiornare le impostazioni su `SameSite=None` in modo che questi cookie possano essere condivisi tra i siti. Per ulteriori informazioni, consulta “[Modificare il valore SameSite quando si utilizza un CNAME per più domini](#samesite-one-cname)” nella sezione successiva.

Per i browser identificati da Google come cookie gestiti non correttamente quando `SameSite` è impostato su `None`, `SameSite` viene invece lasciato non impostato.

Nella tabella seguente sono riassunti gli attributi per i cookie di Analytics:

![Tabella cookie](/help/technotes/assets/cookies1.png)

### In che modo i requisiti dell’indirizzo del sito per l’attributo SameSite possono essere soddisfatti?

#### Distribuire su tutte le pagine del sito con HTTPS

Conferma che la configurazione JavaScript utilizzi HTTPS per tutte le chiamate ai servizi Adobe.

Se il sito utilizza il servizio ID visitatore di Experience Cloud, il servizio reindirizza le chiamate HTTP di terze parti al relativo endpoint HTTPS, che può aumentare la latenza ma significa che non è necessario modificare la configurazione.

#### Modificare il valore SameSite quando si utilizza un CNAME per più domini {#samesite-one-cname}

>[!NOTE]
>
>Le seguenti informazioni si riferiscono solo ai siti che non utilizzano il servizio ID visitatore di Experience Cloud.

Se disponi di un’implementazione CNAME impostata nello stesso dominio del sito web, il cookie viene creato in un contesto di prime parti e non è necessario apportare modifiche.

Tuttavia, se possiedi più domini e utilizzi lo stesso CNAME per la raccolta di dati su tutti i domini, allora il cookie viene trattato come cookie di terze parti per gli altri domini. Con Chrome 80 e versioni successive, non è più visibile su tali altri domini. Per uniformare il comportamento su tutti i browser, Analytics ha impostato esplicitamente il valore `SameSite` di questo cookie su `Lax`. Se utilizzi questo cookie in un contesto di terze parti semplice, devi impostare il cookie con il valore `SameSite=None`, il che significa anche che devi sempre utilizzare HTTPS. Se non lo hai già fatto, contatta l’Assistenza clienti di Adobe per far sì che il valore SameSite venga modificato per i CNAME protetti.

## Come posso determinare se le modifiche di Safari influiscono sulla mia azienda? {#measure-itp-effect}

Adobe consiglia ai clienti di misurare l’impatto all’interno della propria azienda prima di modificare la raccolta dei dati. Puoi utilizzare Analysis Workspace per misurare l’impatto della prevenzione del tracciamento ITP sulla tua attività individuale:

* Misura la percentuale di traffico proveniente da browser gestiti da ITP:

   1. Crea un segmento per vedere quanti visitatori utilizzano una piattaforma ITP.

      >[!NOTE]
      >
      >I browser specifici interessati da ITP dipendono dall’utilizzo o meno di un’implementazione CNAME. Consulta “[Timeline delle principali modifiche apportate ai criteri ITP](#ITP-timeline)” per maggiori dettagli.

      ![Segmento per i visitatori ITP](/help/technotes/assets/itp-visitor-segment.png)

   2. Applica il segmento al numero di visite per comprendere l’utilizzo relativo di Safari nella tua base utenti. Questo ti consente di creare una tabella come questa:

      ![Percentuale di visite da parte dei visitatori ITP](/help/technotes/assets/visits-vs-safari-visits.png)

* Misura la percentuale di visitatori che utilizzano browser non Safari e che non ritornano entro sette giorni. Se i visitatori non Safari ritornano ripetutamente entro sette giorni, il traffico Safari potrebbe non essere influenzato in modo significativo.

   1. Crea un segmento per il traffico non Safari come quello seguente.

      ![Segmento per i visitatori che ritornano dopo sette giorni](/help/technotes/assets/visits-after-seven-days.png)

   2. Applica il segmento al numero di visite per comprendere l’utilizzo relativo di Safari nella tua base utenti. Questo ti consente di creare una tabella come questa:

      ![Percentuale di visitatori che ritorna dopo sette giorni](/help/technotes/assets/percent-visits-after-seven-days.png)

### Modi per regolare i dati durante la generazione rapporti

Se la tua azienda è interessata dalla prevenzione del tracciamento ITP, puoi prendere in considerazione le seguenti misure per adeguare i dati durante la generazione rapporti.

* Crea un segmento per filtrare gli utenti ITP.

  ![Segmento per visitatori non ITP](/help/technotes/assets/non-itp-visitor-segment.png)

* Crea una metrica calcolata per regolare l’inflazione dei visitatori noti.

  ![Metrica calcolata per la rettifica in base all’inflazione dei visitatori](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Opzioni per attenuare l’effetto delle limitazioni dei cookie del browser](cookieless.md)
>[Impatto del nuovo framework per la trasparenza del tracciamento delle app di Apple su Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
