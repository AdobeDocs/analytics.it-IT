---
title: Cookie di Adobe Analytics e browser
description: Scopri in che modo le misure di prevenzione del tracking influiscono sui cookie di terze parti e di prima parte impostati da Adobe Analytics.
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '1985'
ht-degree: 1%

---

# Cookie di Adobe Analytics e browser

Questo documento spiega in che modo le misure di prevenzione del tracciamento dei principali browser influiscono sui cookie di terze parti e di prima parte impostati da Adobe Analytics. Include informazioni sul programma ITP (Intelligent Tracking Prevention) di Apple e sulle limitazioni di Chrome sui cookie di terze parti tramite l’attributo SameSite.

## In che modo i browser hanno limitato l’utilizzo dei cookie?

>[!NOTE]
>[Analisi multidispositivo](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en#cda) e [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#comparing-cja-to-traditional-adobe-analytics) può eseguire unioni tra i cookie utilizzando un ID persona, ad esempio un ID di accesso con hash, se disponibile.

### Limitazioni dei cookie di terze parti

I cookie utilizzati in un contesto di terze parti sono ampiamente obsoleti. Firefox e Safari hanno iniziato a bloccare i cookie di terze parti per impostazione predefinita a partire rispettivamente dal 2019 e dal 2020. Chrome ha annunciato piani per smettere di supportare i cookie di terze parti nel 2023. In tal caso, i cookie di terze parti saranno di fatto inutilizzabili.

Inoltre, Chrome attualmente consente ai cookie di funzionare in un contesto di terze parti solo se l’attributo &quot;SameSite&quot; è impostato su Nessuno e se l’attributo è etichettato come sicuro, il che significa che possono essere utilizzati solo tramite HTTPS. Ulteriori informazioni sono disponibili nella sezione &quot;[Cos’è l’attributo cookie SameSite e come influisce su Analytics?](#samesite-effect)&quot;

#### Quali cookie di terze parti di Adobe sono interessati?

Il servizio ID visitatore utilizza il[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)&quot; cookie per fornire un identificatore permanente per i visitatori tra domini cliente diversi. Il servizio Analytics ID legacy, il cookie &quot;s_vi&quot;, è impostato come cookie di terze parti per le implementazioni che non utilizzano un dominio di raccolta CNAME personalizzato.

Nei browser in cui i cookie di terze parti sono bloccati, il tracciamento tra domini diversi non è disponibile.

### Limitazioni dei cookie di prime parti {#limitations-first-party-cookies}

I cookie di prime parti sono consentiti su tutti i principali browser. Tuttavia, Apple limita la durata di vita dei cookie di prime parti impostati da Adobe tramite il proprio programma di monitoraggio intelligente (ITP). Questo riguarda Safari e tutti i browser su iOS e iPadOS.

I cookie di prime parti di Adobe sono limitati a una scadenza di 7 giorni oppure, per i click-through che Apple determina provenienti dai tracker, a una scadenza di 24 ore. Con una scadenza di 7 giorni, se un utente visita il tuo sito e ritorna entro sette giorni, la data di scadenza del cookie viene estesa di altri sette giorni. Tuttavia, se un utente visita il sito e ritorna in otto giorni, viene trattato come un nuovo utente alla seconda visita.

Attualmente, i criteri ITP si applicano a tutti i cookie di prime parti impostati da Adobe, sia che tu stia utilizzando il servizio ID visitatore sia l’ID Analytics legacy (&quot;s_vi&quot; cookie). A un certo punto, questi criteri si applicano solo ai cookie impostati sul lato client e non ai cookie impostati sul lato server tramite un’implementazione CNAME. Nel novembre 2020, tuttavia, ITP è stato aggiornato per applicarlo anche alle implementazioni CNAME.

#### Tempistica delle principali modifiche alla politica ITP {#ITP-timeline}

* Febbraio 2019 con [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/): I cookie lato client erano limitati a una scadenza di sette giorni
* Aprile 2019 con [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/): I cookie lato client erano limitati a 24 ore per i clic degli annunci quando il dominio di riferimento era a) coinvolto nel tracciamento tra siti e b) l&#39;URL finale conteneva una stringa di query e/o un identificatore di frammento.
* Novembre 2020 con [Difesa di tracciamento dei messaggi CNAME e messaggi non recapitati](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/): Le limitazioni ITP sono state estese alle implementazioni CNAME.

Le politiche ITP si evolvono frequentemente. Per i criteri più recenti, consulta Apple [Prevenzione del tracciamento in Webkit](https://webkit.org/tracking-prevention).

#### Quali cookie di prime parti di Adobe sono interessati?

Tutti i cookie di prime parti impostati da Adobe e le relative librerie JavaScript sono interessati dai criteri ITP:

* [Cookie &quot;AMCV&quot;](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) impostato dalla libreria del servizio ID visitatori di Adobe Experience Cloud (ECID)
* legacy di Analytics [Cookie &quot;s_vi&quot;](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) quando è configurato con raccolta dati di prime parti utilizzando un CNAME
* legacy di Analytics [Cookie &quot;s_fid&quot;](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html), che è il cookie di fallback utilizzato quando non è possibile impostare &quot;s_vi&quot;

#### Qual è l’impatto di ITP su Safari per Analytics?

L’impatto delle limitazioni ITP può variare in modo significativo, a seconda del comportamento degli utenti. Sono interessati solo i visitatori che utilizzano un browser con impatto ITP (ad esempio, Safari) e ritornano dopo un’assenza di sette giorni. Se i visitatori non utilizzano un browser ITP o ritornano entro sette giorni, non riceveranno alcun cambiamento. È importante esaminare i propri dati in Analytics per comprendere l’entità dell’impatto di questa limitazione. Per suggerimenti su come misurare l’impatto sui siti, consulta &quot;[Come posso determinare se le modifiche di Safari influiscono sulla mia azienda?](#measure-itp-effect)&quot;

Se queste limitazioni influiscono sui dati, vedrai:

1. I visitatori incrementati vengono conteggiati come visitatori di ritorno e vengono trattati come nuovi visitatori perché i loro cookie sono scaduti. Sono interessate anche tutte le metriche basate sulla metrica Visitatore (ad esempio Vendite per visitatore).
2. Modifiche all’attribuzione. L’attribuzione si basa sul collegamento di eventi di conversione ad attività precedenti da parte dello stesso visitatore. Una volta scaduto il cookie, gli eventi successivi vengono associati a un nuovo visitatore. Le attività del nuovo visitatore non possono essere legate alle attività del visitatore precedente.

>[!NOTE]
>
>Le tecnologie ITP attualmente non si applicano ai browser incorporati nelle app mobili.

## Qual è la differenza tra cookie di terze parti e cookie di prima parte?

### Cookie di terze parti

I cookie di terze parti non vengono creati dai siti web visitati dagli utenti.

Anche se i browser trattano tutti i cookie di terze parti allo stesso modo e li memorizzano, i cookie di terze parti possono comportarsi in modi diversi. Con l’implementazione di cookie di terze parti di Analytics di un cliente, i browser memorizzano l’Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=it) ID come cookie di terze parti, ma il cliente effettua chiamate solo ad Adobe e non a domini di terze parti troppo sconosciuti o sospetti. Questo cookie fornisce identificatori permanenti tra i domini e consente contenuti protetti (HTTPS). Per ulteriori informazioni, consulta [Cookie e il servizio Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html).

Nelle implementazioni di Analytics, i cookie di terze parti vengono utilizzati per il tracciamento tra domini diversi e per i casi di utilizzo pubblicitario, inclusi gli annunci di retargeting. I cookie di terze parti ti consentono di identificare i visitatori che visitano diversi domini di tua proprietà o che vengono visualizzati annunci su siti di tua proprietà.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### Cookie di prime parti

I cookie di prime parti sono specifici del dominio e vengono creati dai siti web dei clienti e memorizzati nei browser client quando gli utenti visitano i siti web. Tutti i browser generalmente accettano i cookie di prime parti, anche se [Safari limita la scadenza di alcuni tipi di cookie di prime parti](#limitations-first-party-cookies).

Nelle implementazioni di Analytics, i cookie di prime parti vengono utilizzati per identificare gli utenti quando si trovano sul tuo sito e supportano quindi tutte le analisi dell’attività dell’utente. Non è necessario utilizzare cookie di terze parti per comprendere l’attività sul sito.

Per ulteriori informazioni, consulta [Informazioni sui cookie di prime parti](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it).

![Confronto tra cookie](/help/technotes/assets/cookies2.png)

## Cos’è l’attributo cookie SameSite e come influisce sui cookie di Analytics? {#samesite-effect}

Con il rilascio del browser Chrome 80 a febbraio 2020 e versioni successive di browser Firefox e Edge, l’attributo per cookie SameSite impone la specifica per tre valori diversi che determinano se i cookie possono essere utilizzati in un contesto di terze parti:

* `None`: Questa impostazione consente l’accesso intersito e consente il passaggio dei cookie in un contesto di terze parti. Per specificare questo attributo, è inoltre necessario specificare `Secure` e tutte le richieste del browser devono seguire HTTPS. Ad esempio, quando imposti il cookie, coppia i valori dell’attributo come segue: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Se non etichettati correttamente, i cookie sono inutilizzabili per i browser più recenti e vengono rifiutati.

* `Lax`: Consente l’invio di richieste intersito con cookie dello stesso sito solo per la navigazione di livello superiore con *sicuro* (sola lettura, ad esempio `GET`) Metodi HTTP.

* `Strict`: Il cookie dello stesso sito non viene inviato per richieste di siti web di terze parti. Il cookie viene inviato solo se il sito del cookie corrisponde al sito nella barra degli URL.

Il comportamento predefinito in queste versioni del browser consiste nel trattare i cookie privi di specifiche `SameSite` attributo uguale a `SameSite=Lax`.

### In che modo Analytics gestisce gli attributi dei cookie SameSite?

Per i clienti che utilizzano il servizio ID visitatori, i cookie hanno le proprietà `SameSite=None` e `secure` impostato per impostazione predefinita, che consente a questi cookie di supportare casi d’uso di terze parti.

Per i clienti che utilizzano gli identificatori legacy di Analytics ( cookie &quot;s_vi&quot; e &quot;s_fid&quot;), i cookie sono impostati anche per abilitare i casi di utilizzo di terze parti con domini di raccolta standard: adobedc.net, 2o7.net e omtrdc.net. Per i clienti che utilizzano un’implementazione CNAME, i set di Analytics `SameSite=Lax`.

>[!NOTE]
>
>Se possiedi più domini e utilizzi lo stesso CNAME per la raccolta dati in tutti i tuoi domini, il cookie viene trattato come cookie di terze parti per gli altri domini. Se utilizzi gli identificatori legacy di Analytics, puoi aggiornare l’impostazione in `SameSite=None` affinché questi cookie possano essere condivisi tra i siti. Vedere &quot;[Modificare il valore SameSite quando si utilizza un CNAME per più domini](#samesite-one-cname)&quot; nella sezione successiva per ulteriori informazioni.

Per i browser che Google ha identificato come gestione errata dei cookie quando `SameSite` è impostato su `None`, `SameSite` viene invece lasciato non impostato.

La tabella seguente riepiloga gli attributi SameSite per i cookie di Analytics:

![Tabella cookie](/help/technotes/assets/cookies1.png)

### Come posso specificare i requisiti dell&#39;indirizzo del sito per l&#39;attributo SameSite?

#### Distribuire tutte le pagine del sito con HTTPS

Verifica che la tua configurazione JavaScript utilizzi HTTPS per tutte le chiamate ai servizi Adobe.

Se il sito utilizza il servizio ID visitatore di Experience Cloud, il servizio reindirizzerà le chiamate HTTP di terze parti al suo endpoint HTTPS, che può aumentare la latenza ma significa che non è necessario modificare la configurazione.

#### Modificare il valore SameSite quando si utilizza un CNAME per più domini {#samesite-one-cname}

>[!NOTE]
>
>Le informazioni seguenti riguardano solo i siti che non utilizzano il servizio ID visitatore di Experience Cloud.

Se disponi di un’implementazione CNAME impostata nello stesso dominio del sito web, il cookie viene creato in un contesto di prima parte e non è necessario apportare modifiche.

Tuttavia, se possiedi più domini e utilizzi lo stesso CNAME per la raccolta dati in tutti i tuoi domini, il cookie viene trattato come cookie di terze parti per gli altri domini. Con Chrome 80 e versioni successive, non è più visibile su questi altri domini. Per fare in modo che il comportamento sia più simile in tutti i browser, Analytics ha impostato esplicitamente la variabile `SameSite` valore di questo cookie in `Lax`. Se utilizzi questo cookie in un contesto di terze parti descrittivo, devi avere il cookie impostato con il `SameSite=None` che significa anche che devi sempre utilizzare HTTPS. Se non lo hai già fatto, contatta l’Assistenza clienti Adobe per far sì che il valore SameSite venga modificato per i CNAME protetti.

## Come posso determinare se le modifiche di Safari influiscono sulla mia azienda? {#measure-itp-effect}

L’Adobe consiglia ai clienti di misurare l’impatto all’interno della propria azienda prima di modificare la raccolta dei dati. Puoi utilizzare Analysis Workspace per misurare l’impatto della prevenzione del tracciamento ITP sulla tua attività:

* Misura la percentuale di traffico dai browser gestiti da ITP:

   1. Crea un segmento per vedere quanti visitatori utilizzano una piattaforma ITP.

      >[!NOTE]
      >
      >I browser specifici interessati da ITP dipendono dall’implementazione o meno di CNAME. Vedere &quot;[Tempistica delle principali modifiche alla politica ITP](#ITP-timeline)&quot; per maggiori dettagli.

      ![Segmento per i visitatori ITP](/help/technotes/assets/itp-visitor-segment.png)

   2. Applica il segmento al numero di visite per comprendere l’utilizzo relativo di Safari nella tua base di utenti. Consente di creare una tabella come questa:

      ![Percentuale di visite da parte di visitatori ITP](/help/technotes/assets/visits-vs-safari-visits.png)

* Misura la percentuale di visitatori che utilizzano browser non Safari che non ritornano entro sette giorni. Se i visitatori non Safari ritornano ripetutamente entro sette giorni, il traffico Safari potrebbe non risentirne in modo significativo.

   1. Crea un segmento come il seguente per il traffico non Safari.

      ![Segmento per i visitatori che ritornano dopo sette giorni](/help/technotes/assets/visits-after-seven-days.png)

   2. Applica il segmento al numero di visite per comprendere l’utilizzo relativo di Safari nella tua base di utenti. Consente di creare una tabella come questa:

      ![Percentuale di visitatori che ritornano dopo sette giorni](/help/technotes/assets/percent-visits-after-seven-days.png)

### Come regolare i dati durante il reporting

Se la tua azienda è interessata dalla prevenzione del tracciamento ITP, puoi prendere in considerazione le seguenti misure per regolare i tuoi dati durante il reporting.

* Crea un segmento per filtrare gli utenti ITP.

   ![Segmento per visitatori non ITP](/help/technotes/assets/non-itp-visitor-segment.png)

* Crea una metrica calcolata per regolare l’inflazione dei visitatori noti.

   ![Metrica calcolata per regolare l’inflazione dei visitatori](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Opzioni per attenuare l’effetto delle limitazioni dei cookie del browser](cookieless.md)
>[Impatto del nuovo framework per la trasparenza del tracciamento delle app di Apple su Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
