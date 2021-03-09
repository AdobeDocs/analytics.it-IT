---
description: Le suite di rapporti rollup aggregano i dati provenienti da più suite di rapporti figlio e li visualizzano in un set di dati riepilogato.
title: Suite di rapporti rollup e globali
translation-type: tm+mt
source-git-commit: 4d0d5ca99049e48fcf1f248f78ecef94534b6815
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 1%

---


# Suite di rapporti rollup e globali

Le suite di rapporti rollup aggregano i dati provenienti da più suite di rapporti figlio e li visualizzano in un set di dati riepilogato. Offrono una posizione utile per visualizzare i totali sommati, come visualizzazioni di pagina, ricavi o altre dimensioni di base. I rollup vengono spesso utilizzati perché non richiedono un’implementazione aggiuntiva.

## Definizioni dei tipi di suite di rapporti

**Suite** di rapporti globale: L’implementazione viene modificata per inviare richieste di immagini tra domini diversi in un’unica suite di rapporti globale. Se gli hit vengono inviati anche a singole suite di rapporti, questa pratica è nota come assegnazione di tag a più suite.

**Suite** di rapporti rollup: Creato in Strumenti di amministrazione. Prende la somma di ogni metrica alla fine di ogni giorno.

* I rollup sono liberi di utilizzare e non aumentano l&#39;utilizzo delle chiamate server.
* I rollup forniscono dati totali, ma non segnalano valori singoli nei rapporti. Ad esempio, i valori eVar1 non sono inclusi, ma il totale aggregato può essere.
* I dati non vengono deduplicati quando si combinano dati tra suite di rapporti.
* I rollup vengono eseguiti su base notturna.
* Quando si aggiunge una suite di rapporti a un rollup esistente, i dati storici non vengono inclusi nel rollup.
* Per poter eseguire il rollup, tutte le suite di rapporti figlio devono disporre di dati. Se in un rollup sono incluse nuove suite di rapporti, assicurati di inviare almeno una visualizzazione di pagina a tali suite di rapporti.
* Le suite di rapporti rollup sono limitate a un massimo di 40 suite di rapporti figlio.
* Le suite di rapporti rollup sono limitate a un massimo di 100 eventi.
* I dati contenuti nelle suite di rapporti rollup non supportano raggruppamenti o segmenti.
* Il rapporto Pagine viene sostituito dal rapporto Siti più popolari , che riporta le metriche a livello di suite figlio.

## Suite di rapporti rollup e globali

**Chiamate** server secondarie: I rollup non generano chiamate server aggiuntive oltre a quelle raccolte da una singola suite di rapporti. Se l’organizzazione utilizza l’assegnazione tag a più suite, vengono effettuate chiamate server secondarie per ogni suite di rapporti aggiuntiva inclusa in una richiesta di immagine.

>[!TIP]
>
>Se utilizzi solo una suite di rapporti globale con [suite di rapporti virtuali](../../components/vrs/vrs-considerations.md), non sono necessarie chiamate server secondarie.

**Modifiche** all&#39;implementazione: I rollup non richiedono modifiche di implementazione, mentre le suite di rapporti globali richiedono di includere l’ID suite di rapporti globale nell’implementazione.

**Duplicazione**: Le suite di rapporti globali deduplicano i visitatori univoci, mentre i rollup no. Ad esempio, se un utente visita tre dei tuoi domini nello stesso giorno, i rollup contano tre visitatori univoci giornalieri. Le suite di rapporti globali registrano un visitatore univoco.

**Intervallo di tempo**: I rollup vengono elaborati solo a mezzanotte ogni notte, mentre le suite di rapporti globali segnalano i dati con latenza standard.

**Ampiezza**: I rollup non possono comunicare tra le suite di rapporti. Le suite di rapporti globali possono attribuire il credito alle variabili di conversione tra suite di rapporti e fornire percorsi tra suite di rapporti.

**Dati** storici: I rollup possono aggregare i dati storici, mentre le suite di rapporti globali riportano solo i dati dal momento in cui sono stati implementati.

**Rapporti**: Le suite di rapporti globali forniscono dati su tutte le dimensioni; i rollup forniscono dati aggregati solo su report di alto livello.

**Prodotti** supportati: I rollup possono essere utilizzati solo in Reports &amp; Analytics. Non sono supportati in Analysis Workspace o Data Warehouse. Le suite di rapporti globali possono essere utilizzate in tutti i prodotti.

**Numero di suite** di rapporti aggregate: I rollup supportano solo un massimo di 40 suite di rapporti figlio. Le suite di rapporti globali possono essere implementate su qualsiasi numero di domini o app che possiedi.
