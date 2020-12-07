---
title: ' cookie Adobe Analytics e browser'
description: Scopri come  Adobe Analytics gestisce i cookie di un browser.
translation-type: tm+mt
source-git-commit: 1ff9c892670e7b120bf727e556ff70f76c6751be
workflow-type: tm+mt
source-wordcount: '2285'
ht-degree: 3%

---


#  cookie Adobe Analytics e browser

Per supportare l&#39;identificazione utente permanente tra le proprietà e le soluzioni,  Adobe Analytics è in grado di rispondere alle modifiche nel modo in cui i browser gestiscono i cookie. Nelle seguenti domande frequenti vengono fornite informazioni su come viene mantenuta l’identificazione dei visitatori persistenti con le modifiche apportate ai cookie del browser.

## Come stanno cambiando i browser nel modo in cui gestiscono i cookie?

In generale, la maggior parte dei browser stanno diventando più restrittivi nel modo in cui detengono cookie di terze parti. Questo può influenzare il monitoraggio se il cookie viene eliminato o rifiutato dal browser. Il browser Safari sta inoltre impostando alcune limitazioni per alcuni cookie di prime parti.

L&#39;elenco seguente mostra alcune modifiche recenti in base ai browser:

* Effetto cromatura: A partire da Chrome 80, l&#39; `SameSite` attributo viene gestito in modo diverso per gestire i cookie di terze parti o le richieste tra siti. In ultima analisi, Chrome sviluppatori stanno cercando modi per [rendere obsoleti i cookie](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html?m=1) di terze parti.

* Firefox ed Edge: Gli annunci sui prodotti indicano che le versioni successive dei loro browser devono seguire le stesse modifiche apportate in Chrome 80.

* Safari: With [Safari 12.1](https://webkit.org/blog/category/privacy/), first party persistent cookies set through the document.cookie API, often known as “client-side” cookies, have their expiration capped at seven days.

## Qual è la differenza tra cookie di terze parti e cookie di prime parti?

### Cookie di prime parti

I cookie di prime parti vengono creati dai siti Web dei clienti (specifici per il dominio) e memorizzati nei browser dei clienti quando gli utenti visitano i siti Web dei clienti. Tutti i browser generalmente accettano i cookie di prime parti. In un’implementazione di analisi dei cookie di prime parti, il cookie dell’ID visitatore viene creato in un nodo di Adobe  quando il nome host viene riconciliato con il dominio mediante l’uso di un [CNAME](https://docs.adobe.com/content/help/it-IT/id-service/using/reference/analytics-reference/cname.html). Il cookie viene quindi accettato dal browser in un contesto di prime parti. Per ulteriori informazioni, consultate [Informazioni sui cookie](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-first-party.html)di prime parti.

### Cookie di terze parti

I cookie di terze parti non vengono creati dai siti Web visitati dagli utenti. Sebbene i browser trattino tutti i cookie di terze parti allo stesso modo e li memorizzino di conseguenza, i cookie di terze parti stessi possono comportarsi in modi diversi e importanti. Con l’implementazione di cookie di terze parti di Analytics da parte del cliente, il cliente effettua chiamate solo a  Adobe e non a domini di terze parti sconosciuti o sospetti. Questo è il metodo corrente per implementare Analytics per un tracciamento sicuro (HTTPS) e affidabile con identificatori persistenti. Questo metodo viene implementato configurando il file AppMeasurement.js. Per ulteriori informazioni, vedere [Cookie e il servizio](https://docs.adobe.com/content/help/it-IT/id-service/using/intro/cookies.html)identità Experience Platform .

![Confronto tra cookie](assets/cookies2.png)

## In che modo i browser memorizzano e gestiscono attualmente i cookie di Analytics?

A seconda dell’implementazione, i cookie di Analytics sono memorizzati come segue:

### Implementazioni di cookie di terze parti

I browser attualmente memorizzano l&#39;ID [demdex.net](https://docs.adobe.com/content/help/it-IT/audience-manager/user-guide/reference/demdex-calls.html) dell&#39;Adobe  come cookie di terze parti. Questo cookie fornisce identificatori persistenti tra i domini e consente il contenuto protetto (https).

### Implementazioni di cookie di prime parti

Configurando un CNAME, l&#39;utente può ricevere  cookie di Adobe in un contesto di cookie di prime parti per i propri browser. Questa può essere un&#39;opzione valida se un&#39;implementazione di cookie di terze parti non è ottimale per gli utenti.

## Cos’è l’attributo del cookie SameSite e come influisce su Analytics?

Con il rilascio del browser Chrome 80 e versioni successive di Firefox e browser Edge, l&#39;attributo cookie SameSite applica la specifica per tre valori diversi per controllare il comportamento della richiesta intersito, come segue:

* `None`: Questa impostazione consente l&#39;accesso tra siti e consente il passaggio dei cookie in un contesto di terze parti. Per specificare questo attributo, dovete anche specificare `Secure` e tutte le richieste del browser devono seguire HTTPS. Ad esempio, quando si imposta il cookie, i valori dell&#39;attributo vengono combinati come segue: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Se non etichettati correttamente, i cookie non sono utilizzabili per i browser più recenti e verranno rifiutati.

* `Lax`: Consente l&#39;invio di richieste tra siti con cookie dello stesso sito solo per le operazioni di navigazione di livello principale con metodi *sicuri* (di sola lettura, ad esempio `GET`) HTTP.

* `Strict`: Il cookie dello stesso sito non viene inviato per richieste di siti Web di terze parti. Il cookie viene inviato solo se il sito del cookie corrisponde al sito nella barra URL.

Il comportamento predefinito in queste versioni del browser consiste nel trattare i cookie che non hanno `SameSite` attributi specificati come `SameSite=Lax`.

## In che modo  Adobe Analytics risponde a tali modifiche?

Tutti  aggiornamenti dei cookie di Adobe vengono gestiti tramite  server di Adobe e   ha aggiornato i propri server periferici per impostare gli attributi appropriati dei cookie.  Adobe ha rilasciato aggiornamenti lato server per impostare i cookie di terze parti con gli attributi appropriati. Per i siti non sono necessari aggiornamenti JavaScript.

Questo aggiornamento da  server periferici di Adobe si verifica automaticamente quando gli utenti visitano qualsiasi sito Web in cui viene utilizzato il cookie. Per la maggior parte  prodotti di Adobe, i cookie avranno i flag appropriati come Chrome 80 è rilasciato. L&#39;eccezione è  implementazioni Adobe Analytics che utilizzano la raccolta dati di terze parti e non utilizzano il servizio di identità del Experience Cloud  (ECID). Questi clienti potrebbero rilevare un lieve aumento temporaneo dei nuovi visitatori, che altrimenti sarebbero stati contrassegnati come visitatori di ritorno.

Per i browser che Google ha identificato come la gestione errata dei cookie quando `SameSite` è impostato su `None`, `SameSite` sarà invece lasciato disimpostato.

Nella tabella seguente sono riepilogati i cookie di Analytics:

![Tabella cookie](assets/cookies1.png)

## Qual è il modo migliore per preparare il mio sito per le modifiche Chrome, Firefox ed Edge?

I clienti di Analytics devono confermare che la propria configurazione JavaScript utilizza HTTPS per le chiamate ai servizi  Adobe. ECID reindirizza le chiamate HTTP di terze parti al relativo endpoint HTTPS, che può aumentare la latenza, ma significa che non è necessario modificare la configurazione.

 Adobe suggerisce di assicurarsi che tutte le pagine del sito siano servite con HTTPS.

### Un CNAME per più domini

Se hai un’implementazione CNAME impostata nello stesso dominio del tuo sito Web, questo sarà un contesto di cookie di prime parti e non devi apportare modifiche.

Tuttavia, se possiedi più domini e utilizzi lo stesso CNAME per la raccolta dati in tutti i tuoi domini, viene trattato come cookie di terze parti per gli altri domini. Con Chrome 80, non sarà più visibile su questi altri domini. Per rendere il comportamento più simile in tutti i browser, Analytics sta impostando esplicitamente il `SameSite` valore di questo cookie su `Lax`. Se si utilizza questo cookie in un contesto di terze parti intuitivo, sarà necessario impostare il cookie con il `SameSite=None` valore, il che significa anche che è necessario utilizzare sempre HTTPS. Contatta  Assistenza clienti di Adobe affinché il valore SameSite venga modificato per i CNAME protetti. Nota, questa azione NON è necessaria per i clienti Analytics che utilizzano ECID.

## Qual è l&#39;impatto delle modifiche di Safari (ITP 2.1) per Analytics?

Nonostante le modifiche in Safari 12.1, i set di dati dai cookie Adobe Experience Cloud sono ancora in fase di raccolta. Anche se i cookie sono limitati a sette giorni, i visitatori che tornano alla vostra proprietà entro tale termine rinnovano il cookie e lo impediscono di scadere per altri sette giorni. Le finestre di lookback e i conteggi dei visitatori di ritorno potrebbero essere ridotti per il traffico Safari fino a quando non sarà disponibile un aggiornamento del Adobe .

A causa della finestra di scadenza ridotta di sette giorni, i clienti potrebbero vedere un aumento di visitatori unici. I conteggi delle visite e delle visualizzazioni di pagina non devono essere interessati. Se disponete di una proprietà con traffico stagionale, ad esempio servizi fiscali o vendite al dettaglio per le festività, l&#39;impatto potrebbe essere maggiore in quanto il visitatore non sarà connesso tra le stagioni.

Se utilizzi un CNAME, il servizio ID visitatore salva l’ECID in un cookie di prime parti lato server. Questo consente al cookie di persistere per tutta la durata.

**Nota: ITP 2.1 non si applica ai browser incorporati nelle app mobili.**

### Cookie di prime parti interessati

I cookie di prime parti creati tramite `document.cookie` sono interessati. Se state impostando uno di questi cookie tramite la risposta HTTP (lato server) o mediante la certificazione CNAME, le modifiche apportate alla norma ITP 2.1 non vengono applicate. Sono interessati i seguenti cookie di prime parti e  librerie JavaScript di Adobe correlate:

* Cookie AMCV impostati dalla libreria del servizio ECID (ID Experience Cloud )
* Cookie di fallback legacy di Analytics `s_fid`

Il `s_vi` cookie legacy di Analytics come cookie di terze parti, compresi gli oggetti di raccolta di adobedc.net, 2o7.net o omtrdc.net, continua a essere bloccato in base alle versioni precedenti di ITP.

In sintesi:

* Se disponete di un CNAME e utilizzate il servizio ID visitatore — l&#39;implementazione non verrà modificata.

* Se utilizzi un CNAME di prima parte nel contesto di prima parte e non utilizzi il servizio ID visitatore — l&#39;implementazione non verrà modificata.

* Se utilizzate un dominio di cookie di prime parti nel contesto di terze parti o con i nomi di dominio standard di terze parti (ad esempio `adobedc.net`, `2o7.net``omtrdc.net`, ecc.), Safari continuerà a bloccarlo così com’è.

* Se utilizzi un ID visitatore personalizzato — Dipende da come memorizzi l’ID visitatore. Se memorizzi l’ID in un cookie &quot;lato client&quot; di prime parti, sarai soggetto alla scadenza di sette giorni. Se utilizzi altri mezzi per memorizzare il tuo ID personalizzato, dovrai valutare se ne sei interessato.

### Set di dati meno interessati

I set di dati con visitatori attivi che ritornano frequentemente sono i meno interessati dalle modifiche. Se il contenuto del sito è tale che i clienti ritornano ogni giorno o almeno un paio di volte alla settimana, i cookie per questi utenti attivi saranno rinnovati prima della scadenza. I social network, i notiziari e altri siti di notizie avranno più probabilità di avere una vasta comunità di utenti che tornano frequentemente.

I clienti che utilizzano `s_vi` come ID visitatore principale e sono configurati con la raccolta dati di prime parti utilizzando un CNAME non saranno interessati da ITP 2.1. Si noti che nei casi in cui `s_vi` non è possibile impostare, il cookie di fallback può essere utilizzato `s_fid` e avrà una scadenza di sette giorni.

Inoltre, i set di dati che utilizzano il servizio ID visitatore e hanno un dominio di prime parti ne sono meno influenzati.

## Le modifiche apportate a Safari influiscono sulla mia attività?

 Adobe consiglia ai clienti di misurare l&#39;impatto all&#39;interno della propria azienda prima di apportare modifiche alla raccolta dei dati. Questo può essere fatto con i metodi forniti di seguito in questa sezione.

Per misurare l’impatto dei reporting e dei test, è importante sapere quale tipo di visitatore e di tracciamento dei cookie hai implementato e quanto traffico hai dagli utenti con Safari. Per misurare l&#39;impatto sulla vostra attività, tenete in considerazione quanto segue:

* Verificare i tipi di cookie impostati dalle librerie di Adobi .

* Aprite la console per sviluppatori nel browser Safari più recente. Se visualizzi uno dei cookie elencati sopra nel tuo dominio di prime parti, queste modifiche potrebbero interessarti.

* Se visualizzate un `s_vi` cookie, ma non un `AMCV` cookie impostato nel contesto di un CNAME, utilizzate un CNAME per l&#39;identificazione dei visitatori e l&#39;utilizzo di Analytics non viene influenzato da queste modifiche. Se nel contesto di un CNAME sono visualizzati sia un `s_vi` cookie che un `AMCV` cookie, hai utilizzato di recente o al momento il periodo di tolleranza e il traffico Adobe Analytics  potrebbe essere influenzato.

* Utilizzate Analytics per misurare la percentuale di visitatori che non tornano entro sette giorni. Se i visitatori ritornano ripetutamente entro sette giorni, il traffico potrebbe non risentirne in modo significativo. Per istruzioni su come utilizzare  Adobe Analytics per risolvere questo problema, consultate [Safari ITP 2.1 Impact on Adobe Experience Cloud and  Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)(Impatto su e clienti ).

* Misurate la percentuale di traffico dai browser Safari per determinare se apportare modifiche è sufficientemente giustificata. Per istruzioni sull&#39;utilizzo di Analytics per calcolare la percentuale di traffico Safari verso i siti, consultate [Safari ITP 2.1 Impact on Adobe Experience Cloud and  Experience Platform Customers (Impatto di Safari ITP 2.1 sui clienti](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)e.

## Quali browser vengono utilizzati maggiormente dai visitatori?

Se siete interessati a saperne di più sui browser utilizzati dai visitatori, potete utilizzare il Dimension [](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-browsers.html) Browser di Analytics per determinare quali browser sono maggiormente utilizzati per i vostri siti. Puoi anche utilizzare gli Dimension di Analytics per vedere quali browser vengono utilizzati maggiormente in base alle aree geografiche. For more information, see [GeoSegmentation](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-geosegmentation.html).

Secondo [statcounter](https://gs.statcounter.com/browser-market-share/all), alla fine del 2019 la quota di mercato mondiale per ciascun browser era la seguente:

* Effetto cromatura: ~64%
* Safari: ~17%
* Firefox: ~4%
* Bordo: ~2%

Man mano che la quota di mercato cambia, puoi fare riferimento a tali [statistiche](https://gs.statcounter.com/browser-market-share/all) per rivedere la tua strategia di implementazione.

## Come posso utilizzare al meglio le modifiche ITP 2.1 in Safari a breve termine?

 programma CNAME e certificati gestiti del Adobe viene utilizzato per gestire le modifiche ITP. Il programma di certificazione gestito di Adobe consente di implementare un nuovo certificato di prima parte per i cookie dei siti Web visualizzati senza nessun costo aggiuntivo. Oggi,  Adobe dispone di diversi servizi CNAME per soluzione e sta cercando di sfruttare a breve termine il programma di certificazione di Analytics.

Qualsiasi cliente Analytics corrente con un’impostazione CNAME che utilizza anche  Experience Cloud ID Services per l’identificazione del visitatore potrà sfruttare un futuro aggiornamento della libreria ECID. Questa modifica consentirà ai server di monitoraggio certificati CNAME di mantenere l&#39;ECID e di utilizzarlo come riferimento per l&#39;identificazione dei visitatori. Ulteriori informazioni sono disponibili nelle versioni successive della libreria ECID.

 Adobe è consapevole del fatto che non tutti i clienti della libreria ECID utilizzano CNAMES o Analytics. A tutti i clienti ECID verrà offerta una configurazione CNAME per utilizzare la stessa funzionalità.

Se al momento non utilizzi un CNAME per la tua implementazione, puoi avviare il processo parlando con l&#39;Assistenza clienti.

## Quali sono  Adobi  piani futuri per l&#39;identificazione dei visitatori persistenti?

Le nuove funzionalità e implementazioni includono:

* Opzioni self-service di certificazione CNAME in tutte le soluzioni  Adobe

* Metodi di raccolta di ID visitatore flessibili, BYOI (Porta la tua identità) e raccolta di dati API-first

* Grafici di identità di Adobe Experience Platform

* Metodo unificato per la raccolta dei dati  Adobe

 Adobe si impegna per una personalizzazione più accurata per i consumatori che desiderano un&#39;esperienza personalizzata.  Adobe si adopera per offrire ai nostri clienti funzionalità di identità online che li aiutino ad allineare le scelte relative alla privacy dei loro clienti.

## Ulteriori informazioni

Per ulteriori informazioni, consulta:

* [Adobe Experience Cloud: Aggiornamenti dei cookie per Google Chrome](https://medium.com/adobetech/adobe-experience-cloud-cookie-updates-for-google-chrome-19ad67cf1598)

* [Safari ITP 2.1 Impatto sui clienti Adobe Experience Cloud e  Experienci Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)
