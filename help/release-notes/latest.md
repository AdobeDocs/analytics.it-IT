---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: a74d47cf99545305c9b7d99d934dfedafdd9233b
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 57%

---

# Note sulla versione corrente di Adobe Analytics (settembre 2024)


**Ultimo aggiornamento**: giovedì 11 settembre 2024

Queste note sulla versione coprono il periodo di rilascio dall’11 settembre 2024 ai primi di ottobre. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
|--- | --- | --- | --- |
| **Informazioni aggiuntive nella colonna &quot;Usato in&quot; nel gestore delle metriche calcolate e nel gestore dei segmenti** | La colonna &quot;Usato in&quot; nel gestore delle metriche calcolate e nel gestore dei segmenti contiene le seguenti nuove aree di reporting:<ul><li>**Report Builder**: mostra il numero di metriche calcolate o di segmenti utilizzati nel Report Builder.</li><li>**Componenti ad hoc**: mostra il numero di metriche calcolate ad hoc o di segmenti ad hoc utilizzati nei progetti. Queste metriche e segmenti calcolati ad hoc (altrimenti noti come &quot;metriche calcolate rapide&quot; e &quot;segmenti rapidi&quot;) possono essere utilizzati solo nel progetto in cui sono stati creati, pertanto vengono segnalati separatamente dall’area di reporting &quot;Progetto&quot; nella colonna &quot;Utilizzato in&quot;.</li></ul> |  | 11 settembre 2024 |
| **Estensione Activity Map v3** | L’estensione Activity Map v3 è ora disponibile. Se hai installato l’estensione v2, disinstallala prima di installare l’estensione v3. Passa a **[!UICONTROL Tools]** > **[!UICONTROL Activity Map]** per ottenere la versione più recente dell&#39;estensione. |  | 3 settembre 2024 |


## Correzioni in Adobe Analytics

A4T: AN-355736
Activity Map: AN-353779
Analysis Workspace: AN-348485; AN-349693; AN-357247
App mobile di Analytics: AN-352645
Classificazioni: AN-355636; AN-355651; AN-355753; AN-356005; AN-356439; AN-356540; AN-356577; AN-356622
Analytics tra dispositivi: AN-355138
Feed dati: AN-356258; AN-357133
Data Warehouse: AN-339292; AN-353807
Posizioni di esportazione: AN-356912
API per la privacy: AN-352420
Report Builder: AN-352555; AN-354316
Progetti pianificati: AN-355971
Segmentazione: AN-352095;
Generazione rapporti di Target: AN-355748

Altre correzioni: AN-349698; AN-349880; AN-354860; AN-355355; AN-356289;

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza di 13 mesi di`cust_visids`** salvati | 20 agosto 2024 | La versione del **20 agosto 2024** del motore di elaborazione degli hit di Analytics impone una scadenza di 13 mesi per i `cust_visids` salvati. Se nella suite di rapporti è abilitato “Abilita unione visitatori”, questa impostazione viene utilizzata per trovare `cust_visid` per un `visid_high/visid_low value` senza `cust_visid` sull’hit. Precedentemente, non vi era alcuna scadenza della mappatura di un `cust_visid` per un `visid_high/visid_low`. Con questa versione, se sono trascorsi 13 mesi o più da quando `visid_high/visid_low` ha avuto un `cust_visid` su un hit, la mappatura scadrà. |
| **Campi XDM aggiuntivi dei dettagli di implementazione mappati automaticamente** | giovedì 11 settembre 2024 | Quando si utilizza l’Edge Network di Adobe Experience Platform per inviare dati ad Adobe Analytics, i campi XDM `xdm.implementationdetails.name` e `xdm.implementationdetails.environment` ora vengono sempre mappati alle variabili di dati di contesto `c.a.x.implementationdetails.name` e `c.a.x.implementationdetails.environment`. In precedenza, alcuni scenari impedivano il popolamento di questi valori. Adeguare le regole di elaborazione pertinenti in base alla disponibilità di questi valori. |

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
