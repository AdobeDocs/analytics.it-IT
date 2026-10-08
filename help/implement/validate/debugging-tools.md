---
title: Strumenti di debug per le implementazioni di Analytics
description: Esamina i dati che l’implementazione invia ad Adobe utilizzando i debugger di Analytics, gli strumenti di sviluppo del browser e i proxy di debug HTTP.
keywords: analizzatore di pacchetti, monitoraggio pacchetti, sniffer pacchetti, debugger, charles, NS_BINDING_ABORTED, sendBeacon
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 3%
---
# Strumenti di debug per le implementazioni di Analytics

Gli strumenti di debug, a volte denominati analizzatori di pacchetti o sniffer di pacchetti, consentono di controllare i dati inviati dall’implementazione ad Adobe. Possono aiutarti a confermare che le richieste di si attivano correttamente, esaminare le variabili e i payload inclusi in tali richieste e risolvere eventuali problemi relativi a comportamenti di implementazione imprevisti.

>[!NOTE]
>
>Gli strumenti elencati in questa pagina non sono completi. Rappresentano strumenti che i clienti di Adobe Analytics hanno trovato utili. Ad eccezione degli strumenti forniti da Adobe, Adobe non supporta o non risolve i problemi relativi a questi prodotti. Per informazioni sull&#39;installazione, l&#39;utilizzo e il supporto, consultare l&#39;autore dello strumento.

## Scegliere uno strumento di debug

Le seguenti categorie possono essere utili per selezionare uno strumento in base a ciò che si desidera controllare.

| Tipo di strumento | Utile quando |
| --- | --- |
| **Analytics e debugger tag** | Desideri che le variabili, i tag, i livelli di dati o le richieste di raccolta di Analytics vengano interpretati e presentati in un formato leggibile dagli utenti. |
| **Strumenti per sviluppatori browser** | Si sta eseguendo il debug di un&#39;implementazione Web e si desidera esaminare direttamente le richieste di rete senza installare un&#39;applicazione di debug separata. |
| **Proxy di debug HTTP(S)** | Desideri controllare il traffico HTTP da browser, app mobili, visualizzazioni Web, API o altri client, oppure devi disporre di funzionalità diverse dagli strumenti di sviluppo del browser. |

## Analytics e debugger dei tag

Analytics e i debugger di tag riconoscono le tecnologie di analisi e interpretano le loro richieste. Questi strumenti possono semplificare l’identificazione delle variabili di Adobe Analytics, dei payload di Experience Platform Web SDK, dei tag e delle informazioni di implementazione correlate, senza dover decodificare manualmente le richieste di rete.

| Strumento | Disponibilità | Utile per | Considerazioni |
| --- | --- | --- | --- |
| **[Adobe Experience Platform Debugger](https://experienceleague.adobe.com/it/docs/experience-platform/debugger/home)** | Estensione browser | Debug delle implementazioni di Adobe Experience Platform e CX Enterprise, inclusi Adobe Analytics, tag, livelli dati e Experience Platform Web SDK | Strumento fornito da Adobe e incentrato sulle tecnologie Adobe |
| **[Omnibug](https://omnibug.io)** | Browser basati su Chromium e Firefox | Decodificare Adobe Analytics, Experience Platform Web SDK, i tag Adobe e le richieste di molti altri fornitori di analisi e marketing | Utile per implementazioni contenenti tecnologie di più fornitori |
| **[Debugger ObservePoint](https://www.observepoint.com/solutions/observepoint-debugger/)** | CHROME e EDGE | Analisi e decodifica dei tag di analisi, marketing e misurazione, incluse le richieste di Adobe Analytics | Debugger basato su browser; ObservePoint offre anche prodotti separati per la convalida automatizzata dell’implementazione |
| **[Adobe Experience Platform Assurance](https://experienceleague.adobe.com/it/docs/experience-platform/assurance/home)** | Applicazione web in CX Enterprise | Analisi e convalida degli eventi dalle implementazioni di Mobile SDK e visualizzazione del modo in cui Edge Network ha elaborato gli eventi | strumento fornito da Adobe; connetti l’app a una sessione Assurance per visualizzarne gli eventi |

## Strumenti per sviluppatori di browser

Ogni browser moderno include strumenti per sviluppatori in grado di verificare le richieste di rete, pertanto spesso non è necessario uno strumento separato per eseguire il debug di un’implementazione web. Premere **F12** o **Ctrl+Maiusc+I** (Windows e Linux) o **Cmd+Opzione+I** (macOS), quindi selezionare la scheda **Rete**. In Safari, abilita innanzitutto le funzionalità per sviluppatori nelle impostazioni **Avanzate** di Safari.

## Proxy di debug HTTP(S)

I proxy di debug HTTP intercettano il traffico HTTP e HTTPS tra un client e un server. Sono utili quando gli strumenti di sviluppo del browser non forniscono una visibilità sufficiente o quando l’implementazione viene eseguita al di fuori di un browser web tradizionale.

L&#39;ispezione HTTPS in genere richiede la configurazione del client per considerare attendibile un certificato fornito dal proxy di debug. Segui i criteri di sicurezza della tua organizzazione durante l’installazione dei certificati o l’intercettazione del traffico crittografato.

| Strumento | Utile per |
| --- | --- |
| **[Charles](https://www.charlesproxy.com/)** | Analisi del traffico di browser, applicazioni, dispositivi mobili e altro/i HTTP(S) |
| **[Filtro ovunque](https://www.telerik.com/fiddler/fiddler-everywhere)** | Acquisizione e controllo del traffico HTTP(S) tra applicazioni e dispositivi. Distinto dal prodotto Fiddler Classic precedente. |
| **[Proxyman](https://proxyman.com/)** | Analisi e modifica del traffico HTTP(S) da browser, applicazioni e dispositivi mobili |
| **[Toolkit HTTP](https://httptoolkit.com/)** | Analisi del traffico da applicazioni, API, ambienti di sviluppo e dispositivi mobili, con flussi di lavoro orientati al debug di applicazioni e API |
| **[mitmproxy](https://www.mitmproxy.org/)** | Intercettazione, ispezione e modifica di HTTP(S) scrivibili tramite interfacce web e della riga di comando. Ideale per gli utenti che hanno familiarità con i flussi di lavoro della riga di comando. |

## Individuare le richieste di Adobe Analytics

Per le implementazioni che inviano dati direttamente ad Adobe Analytics, come AppMeasurement, filtra le richieste di rete per:

```text
/ss/
```

Le richieste di raccolta di Adobe Analytics contengono variabili di Analytics nell’URL della richiesta o nel payload. Le richieste non elaborate utilizzano nomi di parametri di query anziché nomi di variabili; ad esempio, eVar1 viene visualizzato come `v1` e prop1 come `c1`. Questi nomi vengono decodificati automaticamente dai debugger di Analytics. Per decodificarli, consulta il [riferimento alla variabile](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference) nella documentazione dell&#39;API di inserimento dati.

Per i codici di stato HTTP restituiti dai server di raccolta dati di Analytics, vedi [Codici di risposta HTTP](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes) nella documentazione dell&#39;API di inserimento dati.

Per le implementazioni che utilizzano Adobe Experience Platform Web SDK, filtra le richieste di rete per:

```text
/ee/
```

Seleziona la richiesta e analizzane il payload per visualizzare i dati inviati a Adobe Experience Platform Edge Network. Il Web SDK invia i dati ad Edge Network, che può quindi inoltrarli ad Adobe Analytics e ad altri servizi configurati. L’ispezione della richiesta del client verifica ciò che il browser ha inviato all’Edge Network; non conferma di per sé che i dati sono stati elaborati correttamente da ogni servizio a valle. Per vedere come Edge Network ha elaborato un evento, usa [Adobe Experience Platform Assurance](https://experienceleague.adobe.com/it/docs/experience-platform/assurance/home).

## Richieste interrotte

Quando una pagina si sposta, il browser può annullare le richieste ancora in corso. Firefox etichetta queste richieste `NS_BINDING_ABORTED`; Chrome e Edge le etichetta `(canceled)`. Per mantenere visibili le richieste dopo la navigazione, abilita **Mantieni registro** (Chrome e Edge) o **Mantieni registri** (Firefox).

Una richiesta annullata non significa necessariamente che i dati siano andati persi. Il browser potrebbe aver inviato la richiesta completa e interrotto l’attesa solo della risposta. Gli strumenti per sviluppatori di browser in genere non possono mostrare la differenza, ma un proxy di debug HTTP può.

Le richieste inviate con `navigator.sendBeacon()` non vengono annullate durante la navigazione. AppMeasurement utilizza `sendBeacon` per i collegamenti di uscita e ogni volta che [`useBeacon`](/help/implement/vars/config-vars/usebeacon.md) è abilitato. Il Web SDK lo utilizza per gli eventi inviati con [`documentUnloading`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/documentunloading). Se le richieste di tracciamento dei collegamenti vengono spesso annullate, utilizza queste opzioni.
