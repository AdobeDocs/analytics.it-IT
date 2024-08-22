---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: bb7c5489a38ab6e8164f7d8feeb8f0d918d75853
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 98%

---

# Note sulla versione corrente di Adobe Analytics (agosto 2024)

**Ultimo aggiornamento**: mercoledì 20 agosto 2024

Queste note sulla versione coprono il periodo di rilascio compreso tra il 14 agosto 2024 e settembre 2024. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Miglioramenti del Web SDK per il tracciamento dei collegamenti** | Nell’ultima versione di Web SDK sono disponibili diversi miglioramenti di rilievo relativi al tracciamento dei collegamenti, a diretto vantaggio di Activity Map. Queste nuove funzioni sono disponibili sia nella libreria JavaScript di Web SDK che nell’estensione tag di Web SDK.<ul><li>Raggruppamento di eventi: quando un visitatore fa clic su un collegamento interno, puoi scegliere di raggruppare i dati dell’evento nella pagina successiva invece di attivare una chiamata dell’evento separata per il tracciamento dei collegamenti. Questo miglioramento riduce il numero di eventi utilizzati dal Web SDK rispetto al limite contrattuale.</li><li>Filtra le proprietà del clic: un nuovo callback che sostituisce `OnBeforeLinkClickSend`. Puoi utilizzare questo callback per filtrare o offuscare i dati relativi ai collegamenti prima di inviarli ad Adobe.</li></ul><p>Per ulteriori informazioni, consulta [clickCollection](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/clickcollection) nella guida utente del Web SDK.</p> | La versione beta aperta è iniziata il 10 luglio 2024 | 18 luglio 2024 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* È stato risolto un problema a causa del quale più valori sconosciuti venivano visualizzati in Workspace (AN-353632)
* È stato risolto un problema a causa del quale l’e-mail di notifica non veniva inviata dopo l’aggiunta di clienti o profili di prodotto nuovi di Analytics in Admin Console (AN-350930)

### Altre correzioni apportate ad Analytics

AN-354361; AN-354248; AN-354211; AN-354324; AN-351532; AN-349808; AN-347831; AN-353777; AN-354092; AN-354064; AN-354202; AN-354006; AN-354097; AN-352548; AN-353819; AN-353818; AN-353628; AN-353747; AN-353527; AN-353490; AN-352647; AN-352656; AN-351274; AN-352135; AN-351519; AN-344906; AN-353697; AN-354499; AN-354402; AN-354062; AN-353905; AN-353932; AN-354142; AN-354194; AN-354182; AN-353758; AN-353039; AN-353612; AN-350799; AN-354414; AN-354636; AN-354249; AN-353637; AN-350949; AN-349402; AN-355103; AN-354174; AN-353823; AN-354819; AN-354215; AN-354219; AN-354040; AN-354763; AN-354597; AN-354478; AN-354528; AN-354335

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza di 13 mesi di`cust_visids`** salvati | 20 agosto 2024 | La versione del **20 agosto 2024** del motore di elaborazione degli hit di Analytics impone una scadenza di 13 mesi per i `cust_visids` salvati. Se nella suite di rapporti è abilitato “Abilita unione visitatori”, questa impostazione viene utilizzata per trovare `cust_visid` per un `visid_high/visid_low value` senza `cust_visid` sull’hit. In precedenza, non vi era alcuna scadenza della mappatura di un `cust_visid` per un `visid_high/visid_low`. Con questa versione, se sono trascorsi 13 mesi o più da quando `visid_high/visid_low` ha avuto un `cust_visid` su un hit, la mappatura scadrà. |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Fine del ciclo di vita per l’API di Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.26.0), fare riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2024](/help/release-notes/2024.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione del componente aggiuntivo Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
