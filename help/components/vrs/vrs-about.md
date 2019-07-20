---
description: Le suite di rapporti virtuali segmentano i dati di Adobe Analytics in modo da poter controllare l'accesso a ogni segmento.
seo-description: Le suite di rapporti virtuali segmentano i dati di Adobe Analytics in modo da poter controllare l'accesso a ogni segmento.
seo-title: Panoramica suite di rapporti virtuali
title: Panoramica suite di rapporti virtuali
uuid: 51 c 63 c 56-dd 58-4 c 23-a 997-ea 6942480 d 22
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Panoramica suite di rapporti virtuali

Le suite di rapporti virtuali segmentano i dati di Adobe Analytics in modo da poter controllare l'accesso a ogni segmento.

Molti clienti hanno dati che confluiscono in una suite di rapporti globale, ma hanno anche dati che confluiscono in suite di rapporti più piccole. Essi impostano una variabile su più suite di rapporti e inviano i loro dati a più suite di rapporti. This is referred to as *multisuite tagging*, or *base/parent report suites*.

Ad esempio, tutti i dati possono essere raccolti in una suite di rapporti, ma puoi configurare suite di rapporti secondarie in modo che altre persone della tua azienda possano accedere a parte dei dati, ma non all'intero. I dati possono essere suddivisi per regione. Potreste avere siti Web diversi per diversi paesi. Altri esempi possono essere marchi specifici appartenenti a un'azienda più grande, ma ciascuno dei quali ha i propri team di marketing.

A *virtual report suite* (VRS) allows you to reproduce this branching concept, using segments instead of multiple report suites. I dati vengono inviati a una suite di rapporti, quindi suddivisi in base ai segmenti. Utilizzando più marchi, potreste impostare un prop per il marchio a cui appartiene un elemento. Utilizzando i segmenti, puoi generare rapporti sugli elementi assegnati a ogni prop. Ciascuno di questi segmenti diventa una visualizzazione indipendente, creando una nuova suite di rapporti. Non invii dati specificatamente a tale segmento, solo alla suite di rapporti globale, ma funziona nei tuoi rapporti come se si trattasse di una suite di rapporti diversa.

Una suite di rapporti virtuale eredita la maggior parte dei livelli di servizio della suite di rapporti base, come le impostazioni evar, le regole di elaborazione, le classificazioni ecc. Le seguenti impostazioni NON sono ereditate:

* ID suite di rapporti (RSID)
* Nome suite di rapporti
* Gruppi di autorizzazioni (le suite di rapporti virtuali possono essere assegnate a gruppi di autorizzazioni propri)

## Benefits of Virtual Report Suites {#section_3420422FE6DF46EAB151FD9442AAFDC4}

I clienti pagano per chiamate secondarie al server, pertanto, eliminando tali chiamate, i risparmi potrebbero risultare significativi. Anche una suite di rapporti virtuale è completamente retroattiva. Se la suite di rapporti globale contiene già dati, i dati pertinenti vengono automaticamente inclusi in una nuova suite di rapporti virtuale. Una nuova suite di rapporti secondaria inizia a raccogliere dati dopo averlo creato, pertanto non includerà dati storici. Quando implementa Analytics, devi solo inviare dati a una suite di rapporti, piuttosto che dover creare implementazioni per la suite di rapporti globale e per ogni suite di rapporti secondaria.

Aiuto suite per rapporti virtuali:

* Semplificazione dell'implementazione consentendo di utilizzare un singolo ID suite di rapporti (RSID) per tutti i siti/domini. Avere tutti i dati in una singola suite di rapporti abilita l'analisi dei clienti quando ci spostiamo verso la prossima generazione di Adobe Analytics.
* Gli utenti aziendali della tua organizzazione vedono sempre i segmenti di dati rilevanti per loro.
* Migliora la sicurezza consentendo agli utenti Admin di controllare l'accesso ai dati in modo più semplice e granulare dopo l'implementazione.
* Possibilità di partecipare a Device Co-op
* Metrica Persone
* Una visualizzazione per singolo cliente dei dati (in futuro)
* Possibilità di creare suite di rapporti virtuali illimitate per segmentare i dati

## Limitations of Virtual Report Suites {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Le suite di rapporti virtuali presentano i seguenti limiti:

* Eventuali limitazioni dei segmenti sono applicabili alle suite di rapporti virtuali

   Una suite di rapporti virtuale non è più di un segmento applicato a una suite di rapporti. Dato che ogni suite di rapporti ha un proprio data warehouse e il proprio feed dati, l'uso di più suite di rapporti genera alcuni vantaggi che i segmenti non forniscono.
* Rapporto in tempo reale
* Le impostazioni e i nomi delle variabili non possono essere personalizzati come in una suite di rapporti completa

## Virtual Report Suites vs. Multisuite Tagging {#section_317E4D21CCD74BC38166D2F57D214F78}

| Funzionalità | Suite di rapporti virtuali | Assegnazione tag multisuite |
|--- |--- |--- |
| Offerte in tempo reale o dati correnti | No | Sì |
| Funziona in tutti gli strumenti Analytics (Analysis Workspace, Generatore di report, Analisi ad hoc, ecc.) | Sì.   Nota: Puoi modificarle e identificarle come suite di rapporti virtuali solo in Reporting e analisi. Tuttavia, puoi selezionarli nei menu a discesa Suite di rapporti negli altri strumenti. | Sì |
| Può caricare dati su di esso (tramite classificazioni, feed dati, ecc.) | No | Sì |
| Supporta la creazione di rapporti DL, segnalibri, dashboard, target, avvisi, segmenti, metriche calcolate… | Sì | Sì |
| Può essere aggiunto singolarmente a Gruppi di autorizzazioni | Sì | Sì |
| Può utilizzare le funzioni Amministratore per modificare le singole impostazioni in questa suite di rapporti (Amministratore &gt; Suite di rapporti) | No (le impostazioni vengono ereditate dall'elemento padre) | Sì |

## Combine Virtual Report Suites and Multisuite Tagging {#section_026FA3FCD7314DD18220E73EC5702AFF}

In alcuni casi, si possono utilizzare sia suite di rapporti virtuali che tag multisuite.

Ad esempio, un rivenditore potrebbe utilizzare una suite di rapporti per ogni marchio e suite di rapporti virtuali per ogni marchio per suddividere i dati in base alla regione. Analogamente, un'organizzazione sportiva potrebbe utilizzare una suite di rapporti per ciascun team, e suite di rapporti virtuali per dividere i fan nell'area del team da quelli esterni alla regione.
