---
description: Combina i dati con e senza marca temporale in un’unica suite di rapporti.
title: Marca temporale opzionale
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 89%

---

# Marca temporale opzionale

Combina i dati con e senza marca temporale in un’unica suite di rapporti.

Marca temporale opzionale consente di:

* Inserite sia i dati con marca temporale sia quelli privi di marca nella stessa suite per report globale.
* Inviate dati con marca temporale da un app per dispositivo mobile a una suite per report globale.
* Aggiornate le app per poter utilizzare il monitoraggio offline senza dover creare per una suite per report.

>[!WARNING]
>
>Se utilizzi Marca temporale opzionale, non impostare [s.visitorID](/help/implement/vars/config-vars/visitorid.md) su dati con marca temporale già esistente. Questo può portare a dati fuori ordine e influire negativamente sui calcoli dei tempi (come i valori del tempo trascorso), sull’attribuzione (persistenza eVar), sui conteggi di numero di visite/visite e sui rapporti sui percorsi.

>[!NOTE]
>
>I dati della sessione abilitati per le marche temporali vengono conservati per un massimo di 92 giorni. Ciò significa che una visita/sessione sarà “tenuta aperta” per 92 giorni, mentre qualsiasi hit aggiuntivo, che non sia di 30 minuti dopo l’hit precedente (in hit time), può ancora essere incluso nella stessa visita/sessione. Eventuali hit &quot;vecchi&quot; ricevuti fuori ordine produrranno risultati &quot;sconosciuti&quot;, poiché una serie di fattori (segmentazione, allocazione, scadenza, ecc.) influenzano l’inclusione o meno di tali hit nel reporting.

## Nuove suite di rapporti {#section_095A7CFBD280494593B9BEC1592B73A6}

* Se creata da un modello, una nuova suite di rapporti utilizza per impostazione predefinita Marca temporale opzionale.

  Puoi creare una nuova suite di rapporti da un modello in **Amministratore > Suite di rapporti > Crea nuovo > Suite di rapporti**.
* Se viene copiata da una suite di rapporti esistente, la nuova suite di rapporti eredita l’impostazione relativa alla marca temporale dall’originale, tra cui:

   * **Marca temporale non consentita** (impostazione che supporta s.visitorID)
   * **Marca temporale necessaria** (impostazione che non supporta s.visitorID)
   * **Marca temporale opzionale** (impostazione che supporta s.visitorID tranne che per hit con marca temporale)

## Per modificare le suite di rapporti esistenti in Marca temporale opzionale {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Vai a **Amministrazione > Suite di rapporti > Modifica impostazioni > Generale > Configurazione marca temporale**.
1. Seleziona la casella **Converti suite di rapporti selezionate in Marca temporale opzionale**.

   In questo modo la suite di rapporti verrà modificata in Marca temporale opzionale.

>[!NOTE]
>
>Se una suite di rapporti è impostata su **Marca temporale opzionale**, per modificare questa impostazione in qualsiasi modo, contatta l’Assistenza clienti di Adobe.
