---
description: Le suite di rapporti virtuali segmentano i dati di Adobe Analytics, in modo da poter controllare l’accesso a ciascun segmento.
title: Panoramica delle suite di rapporti virtuali
feature: VRS
exl-id: 45d18d14-d95a-42fe-b00a-cfce5f936e37
TQID: https://experienceleague.adobe.com/gEs8c9pIUGbbPx7DBAwFhSvT-C6W2vfosgMkrO-32ic
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 807
ht-degree: 7%

---

# Panoramica delle suite di rapporti virtuali

Le suite di rapporti virtuali segmentano i dati di Adobe Analytics, in modo da poter controllare l’accesso a ciascun segmento.

Molti clienti hanno dati che fluiscono in una suite di rapporti globale, ma anche dati che fluiscono in suite di rapporti più piccole. Impostano una variabile su più suite di rapporti e inviano i loro dati a più suite di rapporti. Questa è definita *assegnazione di tag a più suite* o *suite di rapporti base/padre*.

Ad esempio, tutti i dati potrebbero essere raccolti in una singola suite di rapporti, ma puoi impostare suite di rapporti secondarie in modo che altre persone nella tua azienda possano accedere a parte dei dati, ma non a tutti. I dati potrebbero essere suddivisi per area geografica. Potresti avere siti web diversi per paesi diversi. Altri esempi potrebbero essere marchi specifici che appartengono a un’azienda più grande, ma che dispongono ciascuno di un proprio team di marketing.

Una *suite di rapporti virtuale* consente di riprodurre questo concetto di diramazione utilizzando segmenti invece di più suite di rapporti. I dati vengono inviati a una suite di rapporti, quindi vengono suddivisi in base ai segmenti. Utilizzando l’esempio di più marchi, puoi impostare una proprietà per il marchio a cui appartiene un articolo. Utilizzando i segmenti, puoi creare rapporti sugli elementi assegnati a ciascuna proprietà. Ognuno di questi segmenti diventa la propria vista, creando in modo efficace una nuova suite di rapporti. Non si inviano dati specifici a quel segmento, ma solo alla suite di rapporti globale, ma nei rapporti funziona come se si trattasse di una suite di rapporti diversa.

Una suite di rapporti virtuale eredita la maggior parte dei livelli di servizio della suite di rapporti di base, come le impostazioni di eVar, le regole di elaborazione, le classificazioni e così via. LE seguenti impostazioni NON vengono ereditate:

* ID suite di rapporti (RSID)
* Nome suite di rapporti
* Gruppi di autorizzazioni (le suite di rapporti virtuali possono essere assegnate ai propri gruppi di autorizzazioni)

## Vantaggi delle suite di rapporti virtuali {#section_3420422FE6DF46EAB151FD9442AAFDC4}

I clienti pagano per le chiamate server secondarie, quindi l’eliminazione di queste chiamate può comportare risparmi significativi. Anche una suite di rapporti virtuale è completamente retroattiva. Se la suite di rapporti globale contiene già dati, questi vengono inclusi automaticamente in una nuova suite di rapporti virtuale. Una nuova suite di rapporti secondaria inizia a raccogliere i dati solo dopo che è stata creata, quindi non include dati storici. Quando implementi Analytics, devi inviare i dati a una sola suite di rapporti, anziché dover creare implementazioni per la suite di rapporti globale e per ogni suite di rapporti secondaria.

Aiuto per le suite di rapporti virtuali:

* Semplifica l’implementazione consentendo di utilizzare un singolo ID suite di rapporti (RSID) su tutti i siti/domini. L’utilizzo di tutti i dati in un’unica suite di rapporti consente l’analisi dei clienti mentre ci avviciniamo alla prossima generazione di Adobe Analytics.
* Gli utenti aziendali dell’organizzazione visualizzano sempre solo i segmenti di dati di loro interesse.
* Migliora la sicurezza consentendo agli utenti amministratori di controllare l’accesso ai dati in modo più semplice e dettagliato dopo l’implementazione.
* Metrica Persone
* Una visualizzazione dei dati per singolo cliente (in futuro)
* Possibilità di creare suite di rapporti virtuali illimitate per segmentare i dati

## Limitazioni delle suite di rapporti virtuali {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Le suite di rapporti virtuali presentano le seguenti limitazioni:

* Eventuali limitazioni dei segmenti si applicano anche alle suite di rapporti virtuali

  Una suite di rapporti virtuale non è altro che un segmento applicato a una suite di rapporti. Poiché ogni suite di rapporti ha un proprio Data Warehouse e un proprio Feed di dati, l’utilizzo di più suite di rapporti comporta alcuni vantaggi che i segmenti non forniscono.
* Rapporto in tempo reale
* Le impostazioni e i nomi delle variabili non possono essere personalizzati come in una suite di rapporti completa

## Suite di rapporti virtuali e assegnazione di tag a più suite {#section_317E4D21CCD74BC38166D2F57D214F78}

| Funzionalità | Suite di rapporti virtuali | Assegnazione di tag multisuite |
|--- |--- |--- |
| Rapporti sui &quot;dati correnti&quot; in tempo reale | No | Sì |
| Funziona in tutti gli strumenti di Analytics (Analysis Workspace, Report Builder, ecc.) | Sì. **Nota:** è possibile modificarli e identificarli come suite di rapporti virtuali solo in [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Virtual report suites]. Tuttavia, puoi selezionarli nei menu a discesa delle suite di rapporti negli altri strumenti.<p>**Importante**: le suite di rapporti virtuali con elaborazione al momento del reporting e personalizzazione delle variabili non sono attualmente supportate in Adobe Report Builder. | Sì |
| Può caricare dati su di esso (tramite classificazioni, feed di dati, ecc.) | No | Sì |
| Supporta la creazione di rapporti DL, segnalibri, dashboard, destinazioni, avvisi, segmenti, metriche calcolate... | Sì | Sì |
| Può essere aggiunto singolarmente ai gruppi di autorizzazioni | Sì | Sì |
| Può utilizzare le funzioni di amministrazione per modificare le singole impostazioni in questa suite di rapporti (Amministratore > Suite di rapporti) | No (le impostazioni vengono ereditate dall&#39;elemento padre) | Sì |

{style="table-layout:auto"}

## Combinare suite di rapporti virtuali e assegnazione di tag a più suite {#section_026FA3FCD7314DD18220E73EC5702AFF}

In alcuni casi, l’utilizzo di suite di rapporti virtuali e di tag per più suite presenta alcuni vantaggi.

Ad esempio, una retailer potrebbe utilizzare una suite di rapporti per ogni marchio e suite di rapporti virtuali per ogni marchio per suddividere i dati per regione. Allo stesso modo, un&#39;organizzazione sportiva potrebbe utilizzare una suite di rapporti per ogni squadra, poi suite di rapporti virtuali per dividere i tifosi nella regione della squadra da quelli al di fuori della regione.
