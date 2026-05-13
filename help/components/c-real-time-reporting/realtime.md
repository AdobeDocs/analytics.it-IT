---
description: Visualizza il traffico della pagina web e classifica le visualizzazioni di pagina in tempo reale. Fornisce dati actionable su cui basare le decisioni aziendali.
title: Panoramica reportistica in tempo reale
topic-fix: Reports
feature: Real-time
exl-id: 056235bc-42ea-4118-aa54-bc7666044fe3
TQID: https://experienceleague.adobe.com/2QizNDKGlAUqX7IbHANm-nGMicLXDfKSnl7nYGkETxQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 630
ht-degree: 2%

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

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi il flusso live e il reporting in tempo reale, e si applica nei seguenti scenari:

* Per i flussi live, i rapporti in tempo reale, le richieste API e i dati correnti per le variabili di traffico, vengono ritardati solo gli hit con un ID dati supplementare.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit subiscono un ritardo di ulteriori 5-7 minuti.

Tieni presente che l’aumento della latenza inizia dopo l’implementazione del servizio Identity, anche se non hai implementato completamente questa integrazione.
