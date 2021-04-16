---
description: Visualizza il traffico della pagina web e classifica le visualizzazioni di pagina in tempo reale. Fornisce dati utilizzabili su cui basare le tue decisioni aziendali.
title: Rapporti in tempo reale
topic-fix: Reports
uuid: c09cc605-0b3b-41ab-9b46-8c2a26f579a3
exl-id: 267246ba-617f-4284-aaad-d0ace0f6a8cf
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 16%

---

# Rapporti in tempo reale

Visualizza il traffico della pagina web e classifica le visualizzazioni di pagina in tempo reale. Fornisce dati utilizzabili su cui basare le tue decisioni aziendali.

>[!NOTE]
>
>Il rapporto in tempo reale non richiede alcuna implementazione o assegnazione di tag aggiuntivi. Utilizza l’implementazione esistente di Adobe Analytics. Per configurare rapporti in tempo reale, consulta [Configurazione rapporti in tempo reale](/help/admin/admin/realtime/t-realtime-admin.md).

**[!UICONTROL Site Metrics]** > **[!UICONTROL Real-Time]**

Risposta in tempo reale alle seguenti domande: Cosa è la tendenza sul mio sito e perché? Consente agli addetti al marketing di rispondere rapidamente e di gestire attivamente le prestazioni dei contenuti e delle campagne di marketing. I dati in tempo reale segnalati sono latenti da meno di due minuti e si aggiornano automaticamente su base minuto per minuto.

![](assets/report-realtime.png)

Il dashboard include metriche ad alta frequenza di Adobe Analytics e analisi del sito per segnalare visivamente il traffico e la tendenza della visualizzazione delle pagine di notizie dinamiche e siti web di vendita al dettaglio. In tempo reale è possibile comprendere le tendenze dei dati da minuto a minuto, entro pochi secondi dalla raccolta. Raccoglie e trasferisce i dati in un’interfaccia utente con aggiornamento automatico, utilizzando correlazione e tracciamento in tempo reale dei contenuti e alcune conversioni.

Due degli scenari di utilizzo più diffusi includono editori che desiderano promuovere/moderare le storie quando cambia l’attività dell’utente e addetti al marketing che desiderano tenere traccia del lancio di una nuova linea di prodotti.

In qualità di amministratore, puoi

* Crea fino a 3 rapporti in tempo reale per suite di rapporti, utilizzando dimensioni o classificazioni e metriche esistenti. Utilizza le dimensioni secondarie per correlare (o suddividere) con quella primaria.
* Aggiungi 3 dimensioni (o classificazioni) per report (una primaria e due secondarie), oltre a 1 metrica a livello di sito.
* Utilizza qualsiasi evento personalizzato, evento del carrello acquisti o istanza.
* Visualizza fino a 2 ore di dati storici in tempo reale e modifica questa impostazione:

   * Ultimi 15 minuti: Granularità di 1 minuto
   * Ultimi 30 minuti: Granularità di 1 minuto
   * Ultima 1 ora: Granularità di 2 minuti
   * Ultime 2 ore: Granularità di 4 minuti

* Confronta, ad esempio, i valori della settimana scorsa ai valori dello scorso anno (così come al totale di oggi).

Le eVar (metriche di conversione) non sono supportate, in quanto non esiste alcun concetto di persistenza. Puoi selezionare le metriche di conversione, ma queste funzionano solo se sono impostate sulla stessa pagina delle dimensioni. Per ulteriori informazioni, vedere il messaggio di avviso acquisito in [Impostazione di rapporti in tempo reale](/help/admin/admin/realtime/t-realtime-admin.md).

L&#39;impostazione e la visualizzazione dei rapporti in tempo reale è limitata agli amministratori o a qualsiasi utente nei gruppi di autorizzazioni &quot;Accesso a tutti i rapporti&quot; e &quot;Generazione avanzata di rapporti&quot; . Tuttavia, Real-Time rispetta le autorizzazioni. Se, ad esempio, non disponi dei diritti per visualizzare le entrate, non potrai visualizzare un rapporto in tempo reale che include i dati sulle entrate.

## Latenza dei dati come risultato della configurazione A4T {#section_806CE36354FC4C539A0DED9266A5C704}

Dopo l’abilitazione dell’integrazione A4T in Adobe Target, si verifica una latenza aggiuntiva di 5-10 minuti in Adobe Analytics. Questo aumento della latenza consente la memorizzazione dei dati da Analytics e Target nello stesso hit, con conseguente possibilità di suddividere i test per pagina e sezione del sito.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per lo streaming live, i rapporti in tempo reale e le richieste API e per i dati correnti per le variabili di traffico, vengono ritardati solo gli insiemi con ID di dati supplementari.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

L’aumento della latenza inizia dopo l’implementazione del servizio Identity, anche se questa integrazione non è stata completamente implementata.
