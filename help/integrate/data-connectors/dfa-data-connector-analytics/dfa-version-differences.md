---
description: Al momento sono disponibili tre versioni dell'integrazione DFA, 1.0, 1.5 e 2.0.
keywords: DFA
seo-description: Al momento sono disponibili tre versioni dell'integrazione DFA, 1.0, 1.5 e 2.0.
seo-title: Differenze tra versioni
solution: Analytics
title: Differenze tra versioni
topic: Connettori dati
uuid: e 0 ae 70 f 0-369 d -451 a -9752-02660 d 270660
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Version Differences{#version-differences}

Al momento sono disponibili tre versioni dell'integrazione DFA, 1.0, 1.5 e 2.0.

Nella tabella seguente sono riepilogate le funzioni di ciascuna versione dell'integrazione.

| Funzione | Versione 1.0 | Versione 1.5 | Versione 2.0 |
|---|---|---|---|
| DFA Click and Impression Nightly Metrics | Sì | Sì | Sì |
| Monitoraggio click-through e tracciamento della visualizzazione | Sì | Sì | Sì |
| L'integrazione riceve i dati su un livello Inserzionista | No | Sì | Sì |
| L'integrazione riceve i dati su un livello di configurazione della luce | No | No | Sì |
| Metriche costi | No | No | Sì |
| Metriche Creative | No | No | Sì |
| Stringhe di query superiori a 2 KB | No | Sì | Sì |
| Utilizza il modulo Integra per una raccolta dati di terze parti ottimale | No | Sì | Sì |
| Tracciamento timeout ed errori | No | Sì | Sì |
| No need for negotiated Client ID ID | No | No | Sì |

## About Version 1.5 {#section-b5a3e967cfa141ea8f740612336181be}

La versione 1.5 dell'integrazione introduce il modulo Integra alla pagina di destinazione Java. Il modulo Integra consente di effettuare richieste di dimensioni fisse al server di annunci DFA (ad. doubleclick. net) che superano i limiti di richiesta 2 K della precedente integrazione. It also introduces a configurable timeout, *`s.maxDelay`*, to continue collecting Adobe visitor data when network outages occur. Gli errori e i timeout possono essere catturati anche nelle variabili di Analytics.

Nell'illustrazione seguente sono illustrate le interazioni della rete sulla pagina di destinazione nella versione 1.5.

![](assets/DFA_About_1_5.png)

Nella versione 1.5, il modulo Integra (2) richiede dati da Floodlight Server (3). The Floodlight Server will redirect to the DFA ad server, which will return data about the visas as version 1.0. Sarà 302 reindirizzamento (4) a un particolare servizio traduttor sull'integrazione di .112 .2 o 7. net, che trasformerà la struttura di risposta in un oggetto JSON. Il modulo Integra utilizza questo oggetto JSON e trasmette le informazioni al tracciamento Adobe (5).

Passando dalla versione 1.0 dell'integrazione a 1.5 è necessario modificare javascript. Per ottenere questo javascript, accedi al tuo account Adobe Online Marketing Suite, scegli il prodotto Genesis, fai clic su Modifica nell'integrazione DFA e segui la procedura guidata. Se avete già assegnato un ID sito client, una volta salvato l'integrazione riceverete immediatamente il nuovo codice javascript tramite e-mail. Una volta presente questo codice, sarà necessario anche una nuova versione del codice s_ code con il modulo Integra. Questo codice può essere richiesto dal tuo Account Manager o Consulente di implementazione.

Una funzione importante del nuovo codice javascript è che non c'è alcuna modifica implementazione necessaria tra la versione 1.5 e la versione 2.0.

## About Version 2.0 {#section-afd56de0c56c4489bb5ddc5798d6709a}

L'ultima versione dell'integrazione DFA porta i dati per un'intera configurazione di Floodlight nell'integrazione. Precedente alla versione 2.0, le singole integrazioni erano collegate a un singolo inserzionista DFA. Con questa modifica, i clic su Clic, Impression e Costi per l'intera configurazione Floodlight saranno inclusi nella suite di rapporti integrata. È inoltre possibile tenere traccia delle azioni di visualizzazione cross-site quando questi due siti si trovano all'interno della stessa configurazione di Floodlight.

Sono disponibili anche le metriche Costi multimediali a partire dalla versione 2.0 dell'integrazione. Per abilitare le metriche dei costi multimediali per un'integrazione, devi scegliere un evento Reporting e analisi per i contenuti multimediali nella procedura guidata Genesis, e specificare in che valuta i dati delle metriche si trovano nell'interfaccia DFA.

I timeout devono diminuire con l'integrazione del 2.0, poiché i reindirizzamenti 302 sono stati eliminati. L'eliminazione di questi segmenti dovrebbe ridurre i timeout e aumentare la quantità di dati DFA che puoi integrare.

Se una configurazione floodlight è una configurazione condivisa in DFA, l'aggiornamento dalla versione 1. Da 5 a 2.0, i dati di conversione per tutti gli advertiser condivisi all'interno della configurazione Floodlight devono essere inclusi nella suite di rapporti.

## Upgrading to Version 2.0 {#section-f0bf90b9a7a1434ab1540b6c0999f4c7}

La tabella seguente delinea i proprietari per la migrazione alle versioni più recenti dell'integrazione:

| Migrazione | Proprietario | Attività |
|---|---|---|
| Versione da 1.0 a 1.5 | Client | Implementazione di Javascript versione 1.5 con il modulo Integra modulo |
| Versione da 1.5 a 2.0 | Client | Client inizia discussione con Google sui fotogrammi temporali per l'aggiornamento. Dopo l'approvazione, Google abilita Advanced Ad Serving. |

