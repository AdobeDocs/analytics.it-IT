---
description: Combinate dati con marca temporale e non in una singola suite di rapporti.
title: Marca temporale opzionale
topic: Admin tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Marca temporale opzionale

Combinate dati con marca temporale e non in una singola suite di rapporti.

Marca temporale opzionale consente di:

* Inserite sia i dati con marca temporale sia quelli privi di marca nella stessa suite per report globale.
* Inviate dati con marca temporale da un app per dispositivo mobile a una suite per report globale.
* Aggiornate le app per poter utilizzare il monitoraggio offline senza dover creare per una suite per report.

Consultate [Utilizzo delle marche temporali facoltative](/help/implement/js-implementation/timestamps-overview.md) per le best practice relative all’utilizzo delle marche temporali nella suite di rapporti.

>[!IMPORTANT]
>
>Se utilizzate Marca temporale opzionale, non impostate [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html) su dati già con marca temporale. Questo può causare dati fuori ordine e influire negativamente sui calcoli del tempo (come i valori del tempo trascorso), l'attribuzione (persistenza eVar), i conteggi di numero di visita/visita e i rapporti di percorso.

> [!NOTE] I dati delle sessioni con marca temporale abilitata vengono conservati fino a 92 giorni. Ciò significa che una visita/sessione sarà "aperta" per 92 giorni, mentre qualsiasi hit aggiuntivo, che non sia 30 minuti dopo l’hit precedente (in fase di hit), può ancora essere incluso nella stessa visita/sessione. Eventuali hit "vecchi" ricevuti in base all’ordine produrranno risultati "sconosciuti", in quanto diversi fattori (segmentazione, allocazione, scadenza, ecc.) influenza se questi hit verranno inclusi o meno nel reporting.

## Nuove suite di rapporti {#section_095A7CFBD280494593B9BEC1592B73A6}

* Se creata da un modello, per impostazione predefinita una nuova suite di rapporti utilizza Marca temporale opzionale.

   (Puoi creare una nuova suite di rapporti da un modello in **Amministratore &gt; Suite di rapporti &gt; Crea nuovo &gt; Suite** di rapporti.)
* Se copiato da una suite di rapporti esistente, la nuova suite eredita l'impostazione della marca temporale dall'originale, inclusi:

   * **Marca temporale non consentita** (impostazione supportata da s.visitorID)
   * **Marca temporale richiesta** (impostazione di s.visitorID non supportata)
   * **Marca temporale opzionale** (impostazione di s.visitorID supportata ma non sugli hit con marca temporale)

## Per modificare le suite di rapporti esistenti in marche temporali opzionali {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Vai a **Admin (Amministratore) &gt; Report Suites (Suite di rapporti) &gt; Edit Settings (Modifica impostazioni) &gt; General (Generale) &gt; Timestamp Configuration (Configurazione** marca temporale).
1. Selezionate la casella **Converti suite di rapporti selezionate in marche temporali (facoltativo** ).

   In questo modo la suite di rapporti verrà modificata in Marca temporale opzionale.

> [!NOTE] Se una suite di rapporti è stata impostata su **Marca temporale opzionale**, per cambiare questa impostazione in qualsiasi altra, contatta l'Assistenza clienti Adobe.

