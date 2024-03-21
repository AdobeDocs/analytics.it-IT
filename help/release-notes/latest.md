---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b5d274b6b529737b2ad1d135599fe0b0dcf4bf2a
workflow-type: tm+mt
source-wordcount: '1299'
ht-degree: 36%

---

# Note sulla versione corrente di Adobe Analytics (marzo 2024)

**Ultimo aggiornamento**: venerdì 21 marzo 2024

Queste note sulla versione coprono il periodo dal 12 marzo 2024 ad aprile 2024. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Aggiornamento AppMeasurement** | [Versione di AppMeasurement v2.26.0](/help/implement/appmeasurement-updates.md) è disponibile. | | martedì 4 marzo 2024 |
| **Nuova colonna disponibile nella pagina di destinazione Progetti** | Il **[!UICONTROL Last used]** è ora disponibile quando si visualizza la scheda Progetti nella [Pagina di destinazione di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html?lang=it). <p>Queste informazioni possono essere utili per determinare se un progetto è utile per gli utenti dell’organizzazione, mostrando la data e l’ora dell’ultima apertura del progetto.</p> <p>Precedentemente, il **[!UICONTROL Last used]** Questa colonna era disponibile solo nelle aree Gestione metriche calcolate, Gestione segmenti e Gestione avvisi.</p> |  | giovedì 13 marzo 2024 |
| **Supporto di Analytics per i flag di consenso richiesti da Google per DMA** | A causa delle nuove normative europee sulla privacy, Google richiede che i dati raccolti in Europa che sono stati inviati a loro indichino se sono stati concessi due particolari tipi di consenso. **A partire dal 6 marzo**, Google non accetterà più i dati dell’evento che non indicano che è stato concesso il relativo consenso. Adobe Analytics ha rilasciato il supporto per l’acquisizione di questi dati tramite una nuova variabile adConsent. Puoi visualizzare la nuova variabile elencata nella sezione [Interfaccia utente di Privacy Reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md). Se desideri attivare questa impostazione e hai già abilitato la privacy per le variabili di consenso precedenti, dovrai abilitare nuovamente la privacy.<p>Il [Dimensione del consenso per la piattaforma di annunci](/help/components/dimensions/ad-consent.md) indica se il consenso viene raccolto per inviare dati a provider pubblicitari di terze parti come Google. |  | giovedì 13 marzo 2024 |
| **Utilizzo del Report Builder incluso nella colonna &quot;Utilizzato in&quot; nel Gestore delle metriche calcolate e nel Gestore segmenti** | Quando si visualizza **Utilizzato in** Nella colonna Gestione metriche calcolate o Gestione segmenti, i dati di utilizzo sono ora disponibili per il Report Builder.<p>In precedenza, i dati di utilizzo nel Gestore segmenti erano disponibili solo per Avvisi, Progetti, Progetti programmati e Metriche calcolate, mentre i dati di utilizzo nel Gestore metriche calcolate erano disponibili solo per Avvisi, Progetti e Progetti programmati.</p> |  | A fine marzo o all&#39;inizio di aprile |
| **Utilizzare gli stessi account cloud per feed di dati, Data Warehouse e set di classificazione** | Ora è possibile utilizzare gli account e le posizioni cloud creati per esportare i dati (con feed di dati e Data Warehouse) e importare i dati (con set di classificazione).<p> **Modifiche durante la configurazione degli account:** Gli utenti possono configurare gli account di importazione ed esportazione cloud e configurare le posizioni di importazione ed esportazione cloud che possono essere utilizzate per uno dei seguenti scopi:<ul><li>Importazione di dati con set di classificazione</li><li>Esportazione di dati con feed di dati</li><li>Esportazione di dati con Data Warehouse.</li></ul><p>**Modifiche durante la gestione degli account**: gli utenti possono utilizzare la pagina Posizioni (in Componenti > Posizioni) per visualizzare e gestire tutti gli account e le posizioni creati, indipendentemente da dove sono stati creati. <p>In precedenza, la pagina Posizioni si applicava solo ai conti creati per l’importazione di dati con set di classificazione.</p> | | Aprile 2024 |
| **Gli amministratori possono gestire tutte le posizioni e gli account della propria organizzazione** | Una nuova opzione nella scheda Posizioni (nella pagina Componenti > Posizioni ) consente agli amministratori di visualizzare e gestire tutte le posizioni dell’organizzazione.<p>Una nuova opzione nella scheda Account ubicazione (nella pagina Componenti > Posizioni ) consente agli amministratori di visualizzare e gestire tutti gli account dell&#39;organizzazione.</p> <p>In precedenza, gli amministratori potevano visualizzare e gestire solo le posizioni e gli account creati.</p> |  | Aprile 2024 |
| **L’Activity Map utilizza un numero inferiore di chiamate server per Web SDK** | Attualmente, gli eventi di collegamento Activity Map vengono conteggiati come propri eventi e comportano costi aggiuntivi. <p>Questo miglioramento raccoglie alcuni eventi di collegamento e li inserisce nell’hit successivo, in modo simile a come gli eventi vengono gestiti da AppMeasurement.</p> |  | mercoledì 30 aprile 2024 |
| **Aumento delle soglie predefinite per traffico ridotto** | Verso la **metà di aprile 2024**, Adobe inizierà ad aumentare le soglie di traffico ridotto della suite di rapporti predefinita come segue: ![soglie di traffico ridotto](assets/thresholds.png). Questo influisce solo sulle variabili attualmente impostate al di sotto delle nuove soglie. Queste modifiche saranno apportate in modo incrementale ed è previsto che il lavoro sia completato entro la **fine del mese di maggio**. Con l’introduzione di questi aumenti, potresti notare modifiche per le variabili ad alta cardinalità:<ul><li>Per il reporting possono essere disponibili più valori di dimensione.</li><li>Segmenti e metriche calcolate possono includere più dati.</li><li>Le suite di rapporti virtuali basate sui segmenti possono includere più dati.</li><li>Le esportazioni delle classificazioni possono includere più dati.</li></ul> | | Metà aprile 2024 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* Sono stati risolti i seguenti problemi di classificazione: AN-335632; AN-337559; AN-340164; AN-340370; AN-341089; AN-341211; AN-341284; AN-341469; AN-341481; AN-341760; AN-341778; AN-342144; AN-342258; AN-342338, AN-342400
* Sono stati risolti i seguenti problemi relativi al Generatore di regole di classificazione: AN-340921; AN-341269; AN-341292; AN-341467; AN-341666; AN-342145; AN-342329
* È stato risolto il seguente problema di avvisi intelligenti: AN-340736
* È stato risolto il seguente problema di segmentazione: AN-336242
* Sono stati risolti i seguenti problemi relativi alle Date Warehouse: AN-335354; AN-339446; AN-339774; AN-340221; AN-340599; AN-341277; AN-342009; AN-342088; AN-342592
* Sono stati risolti i seguenti problemi relativi ai feed di dati: AN-335508; AN-340887; AN-341050; AN-341208; AN-341403; AN-341479; AN-341524; AN-341661; AN-342000; AN-342125; AN-342256; AN-342301; AN-342410; AN-342502; AN-342525
* È stato risolto il seguente problema di Report Builder: AN-340540
* Sono stati risolti i seguenti problemi di Analysis Workspace: AN-295889; AN-330981; AN-338818; AN-339730; AN-341114; AN-341520;

### Altre correzioni apportate ad Analytics

AN-312198; AN-338009; AN-339549; AN-333970; AN-334790; AN-336461; AN-336572; AN-339549; AN-341119; AN-341246; AN-341268; AN-341272; AN-341475; AN-341547; AN-341558; AN-341680; AN-342017;

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza di 13 mesi del salvataggio`cust_visids`** | giovedì 20 marzo 2024 | Una prossima versione del motore di elaborazione degli hit di Analytics, prevista per aprile o maggio, inizierà ad applicare una scadenza di 13 mesi di `cust_visids`. Se nella suite di rapporti è abilitato &quot;Abilita unione visitatori&quot;, questa impostazione viene utilizzata per trovare `cust_visid` per un `visid_high/visid_low value` senza `cust_visid` sull&#39;hit. Attualmente, non vi è alcuna scadenza della mappatura di un `cust_visid` per un `visid_high/visid_low`. Con questa versione, se sono trascorsi 13 mesi o più da `visid_high/visid_low` ha avuto un `cust_visid` in caso di hit, la mappatura scadrà. |
| **Adobe di aggiunte di membri oggetto API** | 17 gennaio 2024 | Adobe può aggiungere membri di richiesta e risposta facoltativi (coppie nome/valore) agli oggetti API esistenti in qualsiasi momento e senza preavviso, né modifiche nel controllo delle versioni. Adobe consiglia di fare riferimento alla documentazione API di qualsiasi strumento di terze parti integrato con le proprie API, in modo che tali aggiunte, se non comprese, vengano ignorate durante l’elaborazione. Se implementate correttamente, tali aggiunte rappresentano modifiche che non comportato interruzioni per l’implementazione. Adobe non rimuove né aggiunge parametri richiesti senza prima fornire una notifica standard tramite le note sulla versione. |
| **`getPageLoadTime`plug-in obsoleto** | 10 gennaio 2024 | Questo plug-in non è più supportato. Il suo codice utilizza il metodo performance.timing, che (secondo MDN) è diventato [obsoleto](https://developer.mozilla.org/it-IT/docs/Web/API/PerformanceTiming). È stato avviato il lavoro su un plug-in aggiornato. |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.26.0), fare riferimento a [AppMeasurement per le note sulla versione di JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2023](/help/release-notes/2023.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
