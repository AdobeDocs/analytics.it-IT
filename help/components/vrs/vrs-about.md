---
description: Suite di rapporti virtuali segmentano i dati di Adobe Analytics in modo da poter controllare l'accesso a ciascun segmento.
title: Panoramica delle suite di rapporti virtuali
uuid: 51c63c56-dd58-4c23-a997-ea6942480d22
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Panoramica delle suite di rapporti virtuali

Suite di rapporti virtuali segmentano i dati di Adobe Analytics in modo da poter controllare l'accesso a ciascun segmento.

Molti clienti dispongono di dati che scorrono in una suite di rapporti globale, ma anche di dati che scorrono in suite di rapporti più piccole. Impostano una variabile su più suite di rapporti e inviano i loro dati a più suite di rapporti. Questo viene definito *tag* multisuite o suite di rapporti *base/padre*.

Ad esempio, tutti i dati possono essere raccolti in una suite di rapporti, ma potete impostare suite di rapporti secondarie in modo che gli altri utenti della società abbiano accesso a parte dei dati, ma non a tutti. I dati possono essere suddivisi per regione. Potreste avere siti Web diversi per paesi diversi. Altri esempi possono essere marchi specifici che appartengono a un'azienda più grande, ma che hanno ciascuno un proprio team di marketing.

Una suite *di rapporti* virtuale (VRS) consente di riprodurre questo concetto di branching, utilizzando i segmenti invece delle suite di rapporti multiple. I dati vengono inviati a una suite di rapporti, quindi suddivisi in base ai segmenti. Utilizzando l'esempio dei marchi multipli, potete impostare una proprietà per il marchio a cui appartiene un elemento. Utilizzando i segmenti, puoi creare rapporti sugli elementi assegnati a ciascuna proprietà. Ciascuno di questi segmenti diventa una propria vista, creando in modo efficace una nuova suite di rapporti. Non invii dati specifici a quel segmento, solo alla suite di rapporti globale, ma funziona nei rapporti come se fosse una suite di rapporti diversa.

Una suite di rapporti virtuale eredita la maggior parte dei livelli di servizio della suite di rapporti di base, come le impostazioni eVar, le regole di elaborazione, le classificazioni, ecc. Le seguenti impostazioni NON vengono ereditate:

* ID suite di rapporti (RSID)
* Nome suite di rapporti
* Gruppi di autorizzazioni (le suite di rapporti virtuali possono essere assegnate ai propri gruppi di autorizzazioni)

## Vantaggi delle suite di rapporti virtuali {#section_3420422FE6DF46EAB151FD9442AAFDC4}

I clienti pagano per le chiamate server secondarie, pertanto l'eliminazione di queste chiamate può comportare notevoli risparmi. Anche una suite di rapporti virtuale è completamente retroattiva. Se la suite di rapporti globale contiene già dei dati, questi vengono automaticamente inclusi in una nuova suite di rapporti virtuale. Una nuova suite di rapporti secondaria inizierebbe a raccogliere i dati solo dopo la creazione, quindi non includerebbe alcun dato storico. Quando implementi Analytics, devi solo inviare dati a una suite di rapporti, anziché dover creare implementazioni per la suite di rapporti globale e per ogni suite di rapporti secondaria.

Aiuto delle suite di rapporti virtuali:

* Semplificate l'implementazione consentendo di utilizzare un singolo ID Suite di rapporti (RSID) in tutti i siti/domini. La disponibilità di tutti i dati in una singola suite di rapporti consente l'analisi dei clienti man mano che passiamo alla generazione successiva di Adobe Analytics.
* Gli utenti aziendali della tua organizzazione visualizzano sempre solo i segmenti di dati rilevanti per loro.
* Migliorate la sicurezza consentendo agli utenti amministratore di controllare l'accesso ai dati in modo più semplice e dettagliato dopo l'implementazione.
* Offrire la possibilità di partecipare a Device Co-op
* Metrica Persone
* Vista dei dati per singolo cliente (in futuro)
* Possibilità di creare suite di rapporti virtuali illimitate per segmentare i dati

## Limitazioni delle suite di rapporti virtuali {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Le suite di rapporti virtuali presentano le seguenti limitazioni:

* Eventuali limitazioni dei segmenti si applicano alle suite di rapporti virtuali

   Una suite di rapporti virtuale non è altro che un segmento applicato a una suite di rapporti. Poiché ogni suite di rapporti ha un proprio data warehouse e un proprio feed di dati, l'utilizzo di più suite di rapporti comporta alcuni vantaggi che i segmenti non forniscono.
* Report in tempo reale
* Le impostazioni e i nomi delle variabili non possono essere personalizzati come in una suite di rapporti completa

## Suite di rapporti virtuali e tag multisuite {#section_317E4D21CCD74BC38166D2F57D214F78}

| Funzionalità | Suite di rapporti virtuali | Assegnazione di tag a più lingue |
|--- |--- |--- |
| Offre report in tempo reale o "Dati correnti" | No | Sì |
| Funziona in tutti gli strumenti di Analytics (Analysis Workspace, Generatore di report, Analisi ad hoc, ecc.) | Sì.   Nota:  Puoi modificarle e identificarle come suite di rapporti virtuali solo in Reporting e analisi. Tuttavia, potete selezionarli nelle sottoscrizioni della suite di rapporti negli altri strumenti. | Sì |
| Può caricare i dati (tramite classificazioni, feed di dati, ecc.) | No | Sì |
| Supporta la creazione di report DL, segnalibri, dashboard, destinazioni, avvisi, segmenti, metriche calcolate... | Sì | Sì |
| Può essere aggiunto singolarmente ai gruppi di autorizzazioni | Sì | Sì |
| Può utilizzare le funzioni di amministrazione per modificare le singole impostazioni in questa suite di rapporti (Amministratore &gt; Suite di rapporti) | No (le impostazioni vengono ereditate dall'elemento padre) | Sì |

## Combinare suite di rapporti virtuali e tag multisuite {#section_026FA3FCD7314DD18220E73EC5702AFF}

In alcuni casi, l’utilizzo di suite di rapporti virtuali e di tag multisuite offre vantaggi.

Ad esempio, un rivenditore può utilizzare una suite di rapporti per ogni marchio e suite di rapporti virtuali per ogni marchio per suddividere i dati per regione. Allo stesso modo, un'organizzazione atletica potrebbe utilizzare una suite di rapporti per ogni squadra, quindi suite di rapporti virtuali per dividere i fan nella regione del team da quelli al di fuori della regione.
