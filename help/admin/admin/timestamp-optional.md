---
description: Combina sia i dati con marca temporale che quelli privi di marca in una singola suite di rapporti.
seo-description: Combina sia i dati con marca temporale che quelli privi di marca in una singola suite di rapporti.
seo-title: Marca temporale opzionale
solution: Analytics
title: Marca temporale opzionale
topic: Strumenti di amministrazione
uuid: 0 fa 63658-1 cc 2-4 adc -8 d 51-a 0662 d 0 aa 941
translation-type: tm+mt
source-git-commit: 2b7644a7af34fff95d7557382abf3d370bd2637c

---


# Marca temporale opzionale

Combina sia i dati con marca temporale che quelli privi di marca in una singola suite di rapporti.

Marca temporale opzionale:

* Inserite sia i dati con marca temporale sia quelli privi di marca nella stessa suite per report globale.
* Inviate dati con marca temporale da un app per dispositivo mobile a una suite per report globale.
* Aggiornate le app per poter utilizzare il monitoraggio offline senza dover creare per una suite per report.

Consultate [Utilizzo della marca temporale opzionale](/help/implement/js-implementation/timestamps-overview.md) per le best practice quando si utilizzano marche temporali nella suite di rapporti.

>[!IMPORTANT]
>
>Se utilizzate Marca temporale opzionale, non impostate [s. visitorid](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) su dati già con marca temporale. Questo può portare a dati out-of-order e influenzare in modo negativo i calcoli temporale (ad esempio i valori passati), l'attribuzione (persistenza evar), il numero di visite/visite e i rapporti sui percorsi.

>[!NOTE]
>
>I dati delle sessioni abilitati per marca temporale vengono conservati per un massimo di 92 giorni. Ciò significa che una visita/sessione verrà «sospesa» per 92 giorni mentre qualsiasi hit aggiuntivo (che non sarà 30 minuti dopo l'hit precedente (in tempo hit) può essere incluso nella stessa visita/sessione. Tutti gli hit "obsoleti" ricevuti dall'ordine produrranno risultati "sconosciuti", in base a una serie di fattori (segmentazione, allocazione, scadenza ecc.) determina se questi hit verranno inclusi nel reporting o meno.

## Nuove suite di rapporti {#section_095A7CFBD280494593B9BEC1592B73A6}

* Se viene creata da un modello, una nuova suite di rapporti è impostata su Marca temporale opzionale.

   (Puoi creare una nuova suite di rapporti da un modello in **Admin (Amministratore) &gt; Report Suites (Suite di rapporti) &gt; Create New (Crea nuovo) &gt; Report Suite**(Suite di rapporti)).
* Se copiata da una suite di rapporti esistente, la nuova suite di rapporti eredita l'impostazione temporale dall'originale, incluso:

   * **Marche temporali non consentite** (impostazione s. visitorid supportata)
   * **Marca temporale richiesta** (impostazione s. visitorid non supportata)
   * **Marca temporale opzionale** (impostazione s. visitorid supportata ma non sugli hit con marca temporale)

## Per modificare le suite di rapporti esistenti su Marca temporale opzionale {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Vai a **Admin (Amministratore) &gt; Report Suites (Suite di rapporti) &gt; Edit Settings (Modifica impostazioni) &gt; General (Generale) &gt; Timestamp Configuration**(Configurazione marca temporale).
1. Selezionate la **casella di testo Converti suite di rapporti selezionate nella casella opzionale** Marca temporale.

   In questo modo la suite di rapporti viene modificata in Marca temporale opzionale.

>[!NOTE]
>
>Se una suite di rapporti è stata impostata su **Marca temporale opzionale**, per modificarla in qualsiasi altra impostazione, contattate Adobe Client Care.

