---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ed7ccd23b850cda3a0bb695fdc8daee56643c33d
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 55%

---

# Note sulla versione corrente di Adobe Analytics (giugno 2024)

**Ultimo aggiornamento**: giovedì 12 giugno 2024

Queste note sulla versione coprono il periodo dal 12 giugno 2024 a luglio. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Seleziona più filtri quando sono disponibili nel menu a discesa in una tabella a forma libera** | Quando più filtri sono stati aggiunti a una tabella a forma libera come menu a discesa, gli utenti della tabella a forma libera ora possono selezionare più di un filtro alla volta. La tabella a forma libera viene filtrata in modo da includere uno qualsiasi dei filtri selezionati. In precedenza, gli utenti potevano selezionare un solo filtro alla volta in un menu a discesa dei filtri.<p>(Link alla documentazione da seguire.) |  | giovedì 19 giugno 2024 |
| **Sommario per i progetti Workspace** | È ora disponibile un nuovo sommario per i progetti. Il sommario fornisce collegamenti che consentono agli utenti di passare rapidamente a pannelli e visualizzazioni all’interno del progetto. Il sommario può essere abilitato per singoli progetti o per tutti i progetti di un determinato utente.<p>(Link alla documentazione da seguire.) |  | giovedì 19 giugno 2024 |
| **Aggiungere collegamenti ipertestuali a elementi dimensionali in una tabella a forma libera** | <ul><li>Puoi creare collegamenti ipertestuali per uno o più elementi dimensionali per renderli cliccabili all’interno di una tabella a forma libera in Analysis Workspace.</li><li>Puoi creare collegamenti ipertestuali per gli elementi dimensione che hanno valori URL, oppure puoi creare URL personalizzati per gli elementi dimensione che hanno valori non URL.</li><li>Puoi creare URL dinamici personalizzati per più elementi di dimensione utilizzando le variabili. Le variabili possono fare riferimento al valore di un elemento dimensione o alla dimensione di raggruppamento.</li></ul>(Link alla documentazione da seguire.) |  | giovedì 19 giugno 2024 |
| **Impostazioni dell’amministratore per controllare gli account e le posizioni utilizzati per l’esportazione e l’importazione** | Una nuova [Scheda Impostazioni di amministrazione in Gestione posizioni](https://experienceleague.adobe.com/it/docs/analytics/components/locations/locations-manager) consente agli amministratori di controllare se gli utenti possono creare e modificare account e posizioni. Queste impostazioni vengono applicate quando gli utenti [configurare account di importazione ed esportazione cloud](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-accounts) e [configurare i percorsi di importazione ed esportazione cloud](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-locations). <p>Gli amministratori possono anche limitare i tipi di account (Google Cloud Platform, Azure RBAC, Amazon S3 e così via) che gli utenti possono creare e utilizzare.</p><p>In precedenza, tutti gli utenti potevano creare, modificare e utilizzare account e posizioni per qualsiasi tipo di account.</p> | martedì 11 marzo 2024 | mercoledì 18 giugno 2024 |
| **Condividere account e posizioni utilizzati per l’esportazione e l’importazione** | Gli utenti possono ora rendere disponibili a tutti gli utenti della propria organizzazione gli account e le posizioni creati. Solo i proprietari degli account e delle posizioni e gli amministratori di sistema possono modificarli ed eliminarli.<p>In precedenza, gli account e le posizioni potevano essere utilizzati solo dall’utente che li aveva creati.</p><p>Queste impostazioni sono disponibili quando [configurare account di importazione ed esportazione cloud](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-accounts) e [configurare i percorsi di importazione ed esportazione cloud](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-locations). </p> | 12 giugno 2024 | 30 giugno 2024 |
| **Fare in modo che Activity Map utilizzi un numero inferiore di chiamate server per Web SDK** | Attualmente, gli eventi di collegamento Activity Map vengono conteggiati come propri eventi e comportano costi aggiuntivi. Questo miglioramento raccoglie alcuni eventi di collegamento e li inserisce nell’hit successivo, in modo simile a come gli eventi vengono gestiti da AppMeasurement. <p>Il link alla documentazione seguirà a breve</p> | Open Beta inizia il 19 giugno 2024 | Da definire |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* Sono stati risolti i seguenti problemi di classificazione: AN-347682; AN-348396; AN-348625; AN-348668; AN-348926; AN-348936; AN-349040; AN-349191; AN-349195; AN-349443; AN-349697; AN-349758; AN-349862; AN-350051; AN-350054; AN-350208; AN-350497; AN-350525; AN-351067
* Sono stati risolti i seguenti problemi relativi alle Date Warehouse: AN-346862; AN-349409; AN-349926; AN-350629; AN-350996
* Sono stati risolti i seguenti problemi relativi ai feed di dati: AN-346727; AN-348282; AN-348334; AN-348725; AN-348726; AN-348823; AN-349081; AN-349207; AN-349307; AN-349539; AN-349710; AN-349729; AN-349742; AN-349878; AN-349943; AN-350527;
* Sono stati risolti i seguenti problemi relativi alle origini dati: AN-350038
* Sono stati risolti i seguenti problemi di Analysis Workspace: AN-342953; AN-346346; AN-349590; AN-349717; AN-350057; AN-350697; AN-350904
* Sono stati risolti i seguenti problemi di Report Builder: AN-348903; AN-350691
* Sono stati risolti i seguenti problemi relativi a A4T: AN-347690; AN-350853

### Altre correzioni apportate ad Analytics

AN-346470; AN-346850; AN-347227; AN-348145; AN-348564; AN-349001; AN-349008; AN-349211; AN-349719; AN-350523;

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza di 13 mesi di`cust_visids`** salvati | 22 maggio 2024 | Una prossima versione del motore di elaborazione degli hit di Analytics, **prevista per luglio 2024**, inizierà ad applicare una scadenza di 13 mesi di `cust_visids` salvati. Se nella suite di rapporti è abilitato “Abilita unione visitatori”, questa impostazione viene utilizzata per trovare `cust_visid` per un `visid_high/visid_low value` senza `cust_visid` sull’hit. Attualmente, non vi è alcuna scadenza della mappatura di un `cust_visid` per un `visid_high/visid_low`. Con questa versione, se sono trascorsi 13 mesi o più da quando `visid_high/visid_low` ha avuto un `cust_visid` su un hit, la mappatura scadrà. |
| **Aggiornamenti per area geografica ISO** | 10 maggio 2024 | Il 7 giugno 2024 Adobe eseguirà gli aggiornamenti per l’area geografica ISO 2024. Con questa versione, sono previsti aggiornamenti minori relativi alle aree geografiche. |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.26.0), fare riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2024](/help/release-notes/2024.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
