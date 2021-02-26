---
description: Le suite di rapporti di rollup aggregano i dati da più suite di rapporti figlio e li visualizzano in un set di dati riepilogato.
title: Suite di rapporti rollup e globali
topic: Strumenti di amministrazione
uuid: c90b8e38-2c95-4318-8165-a362106b6142
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 2%

---


# Suite di rapporti rollup e globali

Le suite di rapporti di rollup aggregano i dati da più suite di rapporti figlio e li visualizzano in un set di dati riepilogato. Offrono una posizione ideale per visualizzare i totali sommati come visualizzazioni di pagina, ricavi o altre dimensioni di base. I rollup vengono utilizzati di frequente perché non richiedono un&#39;implementazione aggiuntiva.

## Definizioni dei tipi di suite di rapporti

**Suite** di rapporti globale: L’implementazione viene modificata per inviare le richieste di immagini tra domini diversi in una singola suite di rapporti globale. Se gli hit vengono inviati anche a singole suite di rapporti, questa pratica è detta tag per più suite.

**Suite** di rapporti rollup: Creato in Strumenti di amministrazione. Prende la somma di ogni metrica alla fine di ogni giorno.

* I rollup sono gratuiti e non aumentano l&#39;utilizzo delle chiamate server.
* I rollup forniscono dati totali, ma non segnalano valori singoli nei report. Ad esempio,  valori di eVar 1 non sono inclusi, ma il totale aggregato può essere incluso.
* I dati non vengono deduplicati quando si combinano dati tra suite per report.
* I rollup vengono eseguiti su base notturna.
* Quando aggiungete una suite di rapporti a un rollup esistente, i dati della cronologia non vengono inclusi nel rollup.
* Tutte le suite di rapporti figlio devono contenere dei dati per poter eseguire il rollup. Se in un rollup sono incluse nuove suite di rapporti, accertatevi di inviare almeno una visualizzazione di pagina a tali suite.
* Le suite di rapporti rollup sono limitate a un massimo di 40 suite di rapporti figlio.
* Le suite di rapporti rollup sono limitate a un massimo di 100 eventi.
* I dati contenuti nelle suite di rapporti rollup non supportano suddivisioni o segmenti.
* Il rapporto Pagine viene sostituito dal rapporto Siti più popolari, che riporta le metriche a livello di suite figlia.

## Suite di rapporti rollup e globali

**Chiamate** server secondarie: I rollup non comportano chiamate server aggiuntive oltre le raccolte da una singola suite di rapporti. Se l’organizzazione utilizza i tag per più suite, vengono effettuate chiamate server secondarie per ogni suite di rapporti aggiuntiva inclusa in una richiesta di immagine.

>[!TIP]
>
>Se utilizzi solo una suite di rapporti globale con [suite di rapporti virtuali](../../components/vrs/vrs-considerations.md), non sono necessarie chiamate server secondarie.

**Modifiche** di implementazione: I rollup non richiedono alcuna modifica di implementazione, mentre le suite per report globali richiedono di includere l&#39;ID suite per report globale nella tua implementazione.

**Duplicazione**: Le suite di rapporti globali deduplicano i visitatori univoci, mentre i rollup no. Ad esempio, se un utente visita tre dei tuoi domini nello stesso giorno, i rollup contano tre visitatori unici al giorno. Le suite di rapporti globali registrerebbero un visitatore unico.

**Intervallo** di tempo: I rollup vengono elaborati solo a mezzanotte ogni notte, mentre le suite per report globali riportano i dati con latenza standard.

**Larghezza**: I rollup non possono comunicare tra le suite di rapporti. Le suite per report globali possono attribuire credito alle variabili di conversione tra suite per report, nonché fornire percorsi tra suite per report.

**Dati** storici: I rollup possono aggregare i dati storici, mentre le suite di rapporti globali riportano solo i dati dal momento in cui sono stati implementati.

**Rapporti**: Le suite di rapporti globali forniscono dati su tutte le dimensioni; i rollup forniscono dati aggregati solo per report di alto livello.

**Prodotti** supportati: I rollup possono essere utilizzati solo in Reporting e analisi. Non sono supportati in  Analysis Workspace o Data Warehouse. Le suite di rapporti globali possono essere utilizzate per tutti i prodotti.

**Numero di suite** di rapporti aggregate: I rollup supportano solo un massimo di 40 suite di rapporti figlio. Le suite di rapporti globali possono essere implementate su un numero qualsiasi di domini o app che possedete.
