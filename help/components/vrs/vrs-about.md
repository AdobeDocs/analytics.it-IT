---
description: Le suite di rapporti virtuali segmentano i dati di Adobe Analytics in modo da poter controllare l’accesso a ogni segmento.
title: Panoramica delle suite di rapporti virtuali
uuid: 51c63c56-dd58-4c23-a997-ea6942480d22
exl-id: 45d18d14-d95a-42fe-b00a-cfce5f936e37
source-git-commit: fb5de8ad4eee3e9017ab547823a7fa9132fa2457
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 3%

---

# Panoramica delle suite di rapporti virtuali

Le suite di rapporti virtuali segmentano i dati di Adobe Analytics in modo da poter controllare l’accesso a ogni segmento.

Molti clienti hanno dati che scorrono in una suite di rapporti globale, ma hanno anche dati che scorrono in suite di rapporti più piccole. Imposta una variabile su più suite di rapporti e invia i loro dati a più di una suite di rapporti. Questo viene indicato come *tag multisuite* o *suite di rapporti base/principale*.

Ad esempio, tutti i dati possono essere raccolti in una singola suite di rapporti, ma puoi impostare suite di rapporti secondarie in modo che altre persone della tua azienda abbiano accesso a parte dei dati, ma non a tutti. I dati possono essere suddivisi per regione. Potresti avere diversi siti web per diversi paesi. Altri esempi possono essere marchi specifici che appartengono a un&#39;azienda più grande, ma che ciascuno di essi dispone di propri team di marketing.

Una *suite di rapporti virtuali* (VRS) consente di riprodurre questo concetto di diramazione utilizzando i segmenti anziché più suite di rapporti. I dati vengono inviati a una suite di rapporti e quindi suddivisi in base ai segmenti. Utilizzando l’esempio dei marchi multipli, puoi impostare una proprietà per il marchio a cui appartiene un articolo. Utilizzando i segmenti, puoi creare rapporti sugli elementi assegnati a ogni prop. Ognuno di questi segmenti diventa la propria vista, creando in modo efficace una nuova suite di rapporti. Non invii dati specifici a quel segmento, solo alla suite di rapporti globale, ma funziona nei rapporti come se si trattasse di una suite di rapporti diversa.

Una suite di rapporti virtuale eredita la maggior parte dei livelli di servizio della suite di rapporti di base, ad esempio le impostazioni eVar, le regole di elaborazione, le classificazioni e così via. Le seguenti impostazioni NON vengono ereditate:

* ID suite di rapporti (RSID)
* Nome della suite di rapporti
* Gruppi di autorizzazioni (le suite di rapporti virtuali possono essere assegnate ai rispettivi gruppi di autorizzazioni)

## Vantaggi delle suite di rapporti virtuali {#section_3420422FE6DF46EAB151FD9442AAFDC4}

I clienti pagano per le chiamate server secondarie, pertanto l’eliminazione di queste chiamate può comportare risparmi significativi. Anche una suite di rapporti virtuale è completamente retroattiva. Se la suite di rapporti globale contiene già dei dati, questi vengono automaticamente inclusi in una nuova suite di rapporti virtuale. Una nuova suite di rapporti secondaria inizierebbe a raccogliere i dati solo dopo la creazione, pertanto non includerebbe dati storici. Quando implementi Analytics, devi solo inviare dati a una suite di rapporti, anziché dover creare implementazioni per la suite di rapporti globale e per ogni suite di rapporti secondaria.

Aiuto per le suite di rapporti virtuali:

* Semplifica l’implementazione consentendo di utilizzare un singolo ID suite di rapporti (RSID) in tutti i siti/domini. Disporre di tutti i dati in una singola suite di rapporti consente l’analisi dei clienti man mano che ci avviciniamo alla prossima generazione di Adobe Analytics.
* Gli utenti aziendali della tua organizzazione visualizzano sempre solo i segmenti di dati rilevanti per loro.
* Migliora la sicurezza consentendo agli utenti amministratori di controllare l’accesso ai dati in modo più semplice e granulare dopo l’implementazione.
* Fornire la possibilità di partecipare a Device Co-op
* Metrica Persone
* Visualizzazione dei dati per singolo cliente (in futuro)
* Possibilità di creare suite di rapporti virtuali illimitate per segmentare i dati

## Limitazioni delle suite di rapporti virtuali {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Le suite di rapporti virtuali hanno le seguenti limitazioni:

* Eventuali limitazioni dei segmenti si applicano anche alle suite di rapporti virtuali

   Una suite di rapporti virtuale non è altro che un segmento applicato a una suite di rapporti. Poiché ogni suite di rapporti ha una propria Data Warehouse e un proprio feed dati, l’utilizzo di più suite di rapporti comporta alcuni vantaggi che i segmenti non forniscono.
* Rapporto in tempo reale
* Le impostazioni e i nomi delle variabili non possono essere personalizzati come in una suite di rapporti completa

## Suite di rapporti virtuali e assegnazione di tag a più suite {#section_317E4D21CCD74BC38166D2F57D214F78}

| Funzionalità | Suite di rapporti virtuali | Assegnazione di tag a più suite |
|--- |--- |--- |
| Rapporti in tempo reale o &quot;Dati correnti&quot; | No | Sì |
| Funziona in tutti gli strumenti di Analytics (Analysis Workspace, Report Builder, ecc.) | Sì. **Nota:** puoi modificarli e identificarli come suite di rapporti virtuali solo in Reports &amp; Analytics. Tuttavia, puoi selezionarli negli elenchi a discesa delle suite di rapporti negli altri strumenti. | Sì |
| Può caricare dati su di esso (tramite classificazioni, feed di dati, ecc.) | No | Sì |
| Supporta la creazione di report DL, segnalibri, dashboard, destinazioni, avvisi, segmenti, metriche calcolate... | Sì | Sì |
| Può essere aggiunto singolarmente ai gruppi di autorizzazioni | Sì | Sì |
| Può utilizzare le funzioni di amministrazione per modificare le singole impostazioni in questa suite di rapporti (Amministratore > Suite di rapporti) | No (le impostazioni vengono ereditate dall&#39;elemento padre) | Sì |

## Combinare suite di rapporti virtuali e assegnazione di tag a più suite {#section_026FA3FCD7314DD18220E73EC5702AFF}

In alcuni casi, l’utilizzo di suite di rapporti virtuali e tag con più suite presenta vantaggi.

Ad esempio, un rivenditore può utilizzare una suite di rapporti per ogni marchio e suite di rapporti virtuali per ogni marchio per suddividere i dati per regione. Allo stesso modo, un&#39;organizzazione atletica potrebbe utilizzare una suite di rapporti per ogni team, quindi suite di rapporti virtuali per dividere i fan nella regione del team da quelli al di fuori della regione.
