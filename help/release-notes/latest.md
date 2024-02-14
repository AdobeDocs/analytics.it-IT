---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 55c08fd64b2fbac0e21af10896773c2530fa64a8
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 42%

---

# Note sulla versione corrente di Adobe Analytics (febbraio 2024)

**Ultimo aggiornamento**: giovedì 14 febbraio 2024

Queste note sulla versione coprono il periodo dal 14 febbraio 2024 all’11 marzo 2024. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzionalità | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Activity Map per Web SDK senza costi aggiuntivi** | Attualmente, gli eventi di collegamento Activity Map vengono conteggiati come propri eventi e comportano costi aggiuntivi. Questo miglioramento raccoglie alcuni eventi di collegamento e li inserisce nell’hit successivo, in modo simile a come gli eventi vengono gestiti da AppMeasurement. |  | giovedì 14 febbraio 2024 |
| **Aumento delle soglie predefinite per traffico ridotto** | In entrata **metà aprile 2024**, ad Adobe, inizierà ad aumentare le soglie di traffico ridotto della suite di rapporti predefinita come segue: ![soglie di traffico ridotto](assets/thresholds.png) Questo incide solo sulle variabili attualmente impostate al di sotto delle nuove soglie. Queste modifiche saranno apportate in modo incrementale e ci aspettiamo che il lavoro sia completato entro il **fine maggio**. Con l’introduzione di questi aumenti, potresti notare modifiche per le variabili ad alta cardinalità:<ul><li>Per il reporting possono essere disponibili più valori di dimensione.</li><li>Segmenti e metriche calcolate possono includere più dati.</li><li>Le suite di rapporti virtuali basate sui segmenti possono includere più dati.</li></ul> | Metà aprile 2024 | Fine di maggio 2024 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* Sono stati risolti i seguenti problemi relativi alle classificazioni: AN-319515; AN-337559; AN-338149; AN-338702; AN-338769; AN-338891; AN-339327; AN-339649; AN-339668; AN-339669; AN-339776; AN-339822; AN-340017; AN-340202; AN-340476;
* Sono stati risolti i seguenti problemi relativi al Generatore di regole di classificazione: AN-338385; AN-338399; AN-338592; AN-338810; AN-338893; AN-339431; AN-339894; AN-339933; AN-340201; AN-340309;
* Sono stati risolti i seguenti problemi di A4T: AN-334830; AN-336194; AN-338309; AN-338650;
* È stato risolto il seguente problema di raccolta dati: AN-339323
* Sono stati risolti i seguenti problemi relativi alle Date Warehouse: AN-335542; AN-331425; AN-337215; AN-338445; AN-338643; AN-338651; AN-339461; AN-340066; AN-340207; AN-340460
* Sono stati risolti i seguenti problemi relativi ai feed di dati: AN-335952; AN-338653; AN-339508; AN-339681; AN-340418
* Sono stati risolti i seguenti problemi relativi a Origini dati: AN-338648
* Sono stati risolti i seguenti problemi di Analysis Workspace: AN-326509; AN-336186; AN-336190; AN-336309; AN-337922; AN-338094; AN-338323; AN-338556; AN-339600; AN-340445

### Altre correzioni apportate ad Analytics

AN-328239; AN-332908; AN-335449; AN-335517; AN-336075; AN-336100; AN-336128; AN-338088; AN-338270; AN-338393; AN-338494; AN-339326; AN-339742; AN-339883; AN-340419;

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| Aggiunte di membri agli oggetti API di Adobe | 17 gennaio 2024 | Adobe può aggiungere membri di richiesta e risposta facoltativi (coppie nome/valore) agli oggetti API esistenti in qualsiasi momento e senza preavviso o modifiche nel controllo delle versioni. L’Adobe consiglia di fare riferimento alla documentazione API di qualsiasi strumento di terze parti integrato con le nostre API in modo che, se non comprese, tali aggiunte vengano ignorate durante l’elaborazione. Se implementate correttamente, queste aggiunte rappresentano modifiche non definitive per l’implementazione. Adobe non rimuove né aggiunge parametri richiesti senza prima fornire una notifica standard tramite le note sulla versione. |
| Plug-in `getPageLoadTime` obsoleto | 10 gennaio 2024 | Questo plug-in non è più supportato. Il suo codice utilizza il metodo performance.timing, che (secondo MDN) è diventato [obsoleto](https://developer.mozilla.org/it-IT/docs/Web/API/PerformanceTiming). È stato avviato il lavoro su un plug-in aggiornato. |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.25.0), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2023](/help/release-notes/2023.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
