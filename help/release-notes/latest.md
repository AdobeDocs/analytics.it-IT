---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: cb0eab15dac6d679e9f912010045e6be2e47df4a
workflow-type: ht
source-wordcount: '732'
ht-degree: 100%

---

# Note sulla versione corrente di Adobe Analytics (luglio 2024)

**Ultimo aggiornamento**: 17 luglio 2024

Queste note sulla versione coprono il periodo di rilascio compreso tra il 17 luglio 2024 e agosto 2024. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Miglioramenti del Web SDK per il tracciamento dei collegamenti** | Nell’ultima versione di Web SDK sono disponibili diversi miglioramenti di rilievo relativi al tracciamento dei collegamenti, a diretto vantaggio di Activity Map. Queste nuove funzioni sono disponibili sia nella libreria JavaScript di Web SDK che nell’estensione tag di Web SDK.<ul><li>Raggruppamento di eventi: quando un visitatore fa clic su un collegamento interno, puoi scegliere di raggruppare i dati dell’evento nella pagina successiva invece di attivare una chiamata dell’evento separata per il tracciamento dei collegamenti. Questo miglioramento riduce il numero di eventi utilizzati dal Web SDK rispetto al limite contrattuale.</li><li>Filtra le proprietà del clic: un nuovo callback che sostituisce `OnBeforeLinkClickSend`. Puoi utilizzare questo callback per filtrare o offuscare i dati relativi ai collegamenti prima di inviarli ad Adobe.</li></ul><p>Per ulteriori informazioni, consulta [clickCollection](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/clickcollection) nella guida utente del Web SDK.</p> | La versione beta aperta è iniziata il 10 luglio 2024 | Da definire |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* È stato risolto un problema che impediva agli utenti di accedere all’interfaccia utente di Analytics (AN-352953)
* È stato risolto un problema che impediva agli utenti di accedere all’app mobile di Analytics (AN-352463)
* È stato risolto un problema che impediva il download del progetto come PDF (AN-352680)
* È stato risolto un problema che impediva l’importazione delle classificazioni. (AN-352178)

### Altre correzioni apportate ad Analytics

AN-352905; AN-352902; AN-352693; AN-352659; AN-352619; AN-352577; AN-352575; AN-352572; AN-352571; AN-352549; AN-352501; AN-352499; AN-352478; AN-352466; AN-352437; AN-352378; AN-352355; AN-352341; AN-352318; AN-352297; AN-352272; AN-352267; AN-352263; AN-352088; AN-352019; AN-352018; AN-351978; AN-351908; AN-351809; AN-351750; AN-351689; AN-351624; AN-351564; AN-351524; AN-351507; AN-351416; AN-351414; AN-351405; AN-351299; AN-351283; AN-351231; AN-350710; AN-349912; AN-349786; AN-348300; AN-348061; AN-347865; AN-347676; AN-347478; AN-343611; AN-343114; AN-334124

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza di 13 mesi di`cust_visids`** salvati | 22 maggio 2024 | Una prossima versione del motore di elaborazione degli hit di Analytics, **prevista per luglio 2024**, inizierà ad applicare una scadenza di 13 mesi di `cust_visids` salvati. Se nella suite di rapporti è abilitato “Abilita unione visitatori”, questa impostazione viene utilizzata per trovare `cust_visid` per un `visid_high/visid_low value` senza `cust_visid` sull’hit. Attualmente, non vi è alcuna scadenza della mappatura di un `cust_visid` per un `visid_high/visid_low`. Con questa versione, se sono trascorsi 13 mesi o più da quando `visid_high/visid_low` ha avuto un `cust_visid` su un hit, la mappatura scadrà. |

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
