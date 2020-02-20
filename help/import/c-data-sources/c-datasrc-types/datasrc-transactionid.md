---
title: Origini dati ID transazione
description: Scopri il flusso di lavoro generale dell'utilizzo delle origini dati ID transazione.
translation-type: tm+mt
source-git-commit: a5c3d9b2cd02dc7e89abb469e2e0e44985a17638

---


# Origini dati ID transazione

Le origini dati ID transazione consentono non solo di visualizzare i dati online e offline affiancati, ma anche di collegare i dati. Richiede l&#39;utilizzo della [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variabile nell&#39;implementazione di Analytics.

Quando inviate un hit online contenente un `transactionID` valore, Adobe crea uno &quot;snapshot&quot; di tutte le variabili impostate o persistenti in quel momento. Se viene trovato un ID transazione corrispondente caricato tramite Origini dati, i dati offline e online vengono legati insieme. Non importa quale origine di dati viene visualizzata per prima.

## Flusso di lavoro complessivo delle origini dati ID transazione

Utilizza il seguente flusso di lavoro generico per iniziare a utilizzare le origini dati ID transazione:

1. Creare un&#39;origine dati (tipo &quot;Generico&quot; e &quot;Origine dati generica (ID transazione)&quot;).
1. Segui la procedura guidata di configurazione dei feed di dati per ottenere un percorso FTP per caricare i dati e scaricare un file modello origini dati.
1. Aggiornate l&#39;implementazione per includere la `transactionID` variabile.
1. Carica un file origini dati sul sito FTP con un `.fin` file.
