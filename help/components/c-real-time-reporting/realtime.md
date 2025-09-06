---
description: Visualizza il traffico della pagina web e classifica le visualizzazioni di pagina in tempo reale. Fornisce dati actionable su cui basare le decisioni aziendali.
title: Panoramica reportistica in tempo reale
topic-fix: Reports
feature: Real-time
exl-id: 056235bc-42ea-4118-aa54-bc7666044fe3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 9%

---

# Panoramica reportistica in tempo reale

Il reporting in tempo reale visualizza il traffico della pagina web e classifica le visualizzazioni di pagina in tempo reale. Fornisce dati actionable su cui basare le decisioni aziendali.

>[!NOTE]
>
>Il rapporto in tempo reale non richiede alcuna implementazione o assegnazione di tag aggiuntivi. Sfrutta l’implementazione esistente di Adobe Analytics. Per configurare rapporti in tempo reale, vedere [Configurazione rapporti in tempo reale](/help/admin/tools/manage-rs/edit-settings/realtime/t-realtime-admin.md).

## Accedere ai rapporti in tempo reale

1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**].

1. Nella parte sinistra della pagina, in **[!UICONTROL Templates]**, selezionare [!UICONTROL **Modelli Adobe**].

1. Selezionare [!UICONTROL **Coinvolgimento**] > **[!UICONTROL Real-Time]**.

## Informazioni sul reporting in tempo reale

Risposte in tempo reale alle seguenti domande: Che cosa è la tendenza sul mio sito e perché? Consente a un addetto marketing di rispondere rapidamente e gestire attivamente le prestazioni dei contenuti e delle campagne di marketing. I dati in tempo reale segnalati sono meno di due minuti latenti e con aggiornamenti automatici minuto per minuto.

![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report-realtime.png)

La dashboard include metriche ad alta frequenza di Adobe Analytics e analisi dei siti per segnalare visivamente il traffico e visualizzare le tendenze di notizie dinamiche e siti web di vendita al dettaglio. Real-Time conosce le tendenze nei tuoi dati di minuto in minuto, entro pochi secondi dalla raccolta. Raccoglie e trasmette i dati in un’interfaccia utente con aggiornamento automatico, utilizzando la correlazione e il tracciamento in tempo reale dei contenuti e alcune conversioni.

Due degli scenari di utilizzo più comuni includono gli editori che desiderano promuovere o ridurre di livello le storie quando l’attività dell’utente cambia e gli esperti di marketing che desiderano tenere traccia del lancio di una nuova linea di prodotti.

In qualità di amministratore, puoi

* Crea fino a 3 rapporti in tempo reale per suite di rapporti, utilizzando dimensioni o classificazioni e metriche esistenti. Utilizza le dimensioni secondarie per correlare (o suddividere) quella principale.
* Aggiungi 3 dimensioni (o classificazioni) per rapporto (una principale e due secondarie), oltre a 1 metrica a livello di sito.
* Utilizza qualsiasi evento personalizzato, evento del carrello acquisti o istanza.
* Visualizza fino a 2 ore di dati cronologici in tempo reale e modifica questa impostazione:

   * Ultimi 15 minuti: granularità di 1 minuto
   * Ultimi 30 minuti: granularità di 1 minuto
   * Ultima ora: granularità di 2 minuti
   * Ultime 2 ore: granularità di 4 minuti

* Confronta, ad esempio, i valori della settimana scorsa con quelli dell’anno precedente (nonché con il totale di oggi).

Tieni presente che le eVar (metriche di conversione) non sono supportate, in quanto non esiste un concetto di persistenza. Anche se puoi selezionare le metriche di conversione, queste funzionano solo se impostate sulla stessa pagina delle dimensioni. Per ulteriori informazioni, vedere il messaggio di avviso acquisito in [Impostazione di rapporti in tempo reale](/help/components/c-real-time-reporting/t-realtime-admin.md).

L&#39;impostazione e la visualizzazione di rapporti in tempo reale è riservata agli amministratori o a qualsiasi utente dei gruppi di autorizzazione &quot;Accesso a tutti i rapporti&quot; e &quot;Generazione avanzata di rapporti&quot;. Tuttavia, Real-Time rispetta le autorizzazioni. Se, ad esempio, non disponi dei diritti per visualizzare i ricavi, non potrai visualizzare un rapporto in tempo reale che includa i dati sui ricavi.

## Latenza dei dati come risultato della configurazione A4T {#latency-a4t}

Dopo l&#39;abilitazione dell&#39;integrazione A4T in Adobe [!DNL Target], si verificherà una latenza aggiuntiva di 5-10 minuti in Adobe Analytics. Questo aumento di latenza consente di memorizzare i dati da Analytics e [!DNL Target] sullo stesso hit, consentendo di suddividere i test per pagina e sezione del sito.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per i flussi live, i rapporti in tempo reale, le richieste API e i dati correnti per le variabili di traffico, vengono ritardati solo gli hit con un ID dati supplementare.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

Tieni presente che l’aumento della latenza inizia dopo l’implementazione del servizio Identity, anche se non hai implementato completamente questa integrazione.
