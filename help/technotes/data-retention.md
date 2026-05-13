---
title: Criteri di conservazione dei dati
description: Un criterio di conservazione dei dati determina per quanto tempo Adobe archivia i dati.
exl-id: f3bb02d2-380d-4eb7-8449-e0318fc8c0a6
feature: Data Governance
TQID: https://experienceleague.adobe.com/ymM-0bethfijutq5sprEuEfOFgw3Xn4gTsLNNgKTEio
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 616
ht-degree: 92%

---

# Criteri di conservazione dei dati

I dati raccolti da Adobe Analytics vengono conservati per un periodo di tempo specifico. Il periodo di tempo in cui Adobe conserva i dati varia da contratto a contratto ed è descritto nei criteri di conservazione dei dati di un’organizzazione. Questo criterio si applica ai dati stessi, influendo su tutte le funzionalità di reporting di Analytics (Analysis Workspace, API di reporting, ecc.).

**I criteri di conservazione dei dati predefiniti per Adobe Analytics sono di 25 mesi.** I criteri di conservazione della tua organizzazione possono essere diversi, a seconda del contratto.

I dati conservati si basano sulla data corrente e sulla data/ora dei dati storici. La data/ora registrata negli hit può essere diversa dalla data/ora in cui gli hit sono stati ricevuti da Adobe.

## Regolare il periodo di conservazione dei dati predefinito

Se desideri ridurre o estendere il periodo di conservazione dei dati predefinito, contatta il team Adobe Account.

* La riduzione del periodo predefinito di conservazione dei dati non comporta alcun costo.
* L’estensione della conservazione dei dati oltre il periodo predefinito di 25 mesi richiede l’acquisto di estensioni disponibili con incrementi di un anno ciascuna. È possibile acquistare fino a otto estensioni, per un totale di 10 anni e 1 mese (2 anni e 1 mese per il mantenimento in caso di inadempimento, più 8 anni acquistati).

## Conservazione e privacy dei dati

Adobe, in qualità di titolare del trattamento dei dati, deve adottare misure adeguate per assistere la propria clientela nel rispondere alle richieste di accesso, cancellazione e di altro genere da parte di singoli individui. L’applicazione di criteri di cancellazione adeguati, sicuri e puntuali è determinante ai fini della conformità ai suddetti obblighi. Il Regolamento GDPR si applica a tutta la clientela che ha rapporti commerciali con cittadini UE o ne elabora le informazioni. Il CCPA (legge californiana sulla privacy dei consumatori) si applica a tutta la clientela che ha rapporti commerciali con cittadini residenti in California o ne elabora le informazioni. Di conseguenza, la privacy dei dati ha un impatto normativo a livello internazionale.

## Eliminazione dati

Una volta superati i criteri di conservazione dei dati, Adobe si riserva il diritto di eliminarli senza opzione per il ripristino. È necessario assicurarsi che tutti i dati che si desidera conservare rientrino nei criteri di conservazione dei dati dell’organizzazione.

## Visualizzare/gestire i criteri di conservazione dei dati correnti

La finestra di dialogo Governance dei dati in Strumenti di [!UICONTROL Admin] fornisce una panoramica delle suite di rapporti configurate per la governance dei dati. Indica inoltre se sono stati mappati a un’organizzazione Experience Cloud e se per questa suite di rapporti sono applicati i criteri di conservazione dei dati.

## Domande frequenti

+++ Come decido il periodo di conservazione dei dati dell’organizzazione?

La tua azienda, in quanto titolare del trattamento dei dati, deve identificare le parti interessate (ad esempio i team aziendali addetti a marketing, analisi e privacy) all’interno dell’organizzazione, i quali sono responsabili delle decisioni relative alla conservazione dei dati. Di fatto, la tua organizzazione è nella posizione migliore per valutare il periodo di conservazione dei dati di Adobe Analytics.

+++

+++ Come si calcola la finestra di conservazione dei dati?

I criteri di conservazione dei dati definiscono una finestra temporale dinamica per la conservazione dei dati, all’interno della quale i dati completi possono essere visualizzati e utilizzati per la generazione dei rapporti. La data di inizio della conservazione dei dati è determinata dalla data corrente sottraendo il periodo di conservazione dei dati. La data di fine della conservazione dei dati è determinata dalla data corrente. I dati vengono inclusi nella finestra temporale di conservazione dei dati se la marca temporale dei dati è compresa tra la data di inizio e la data di fine.

+++

+++ Posso richiedere una copia dei miei dati prima che vengano cancellati?

Sì. Adobe può fornire un dump di dati storici di dati grezzi a livello di hit. Per ulteriori informazioni, consulta i [Feed di dati](/help/export/analytics-data-feed/data-feed-overview.md) nella guida utente per l’esportazione. Se disponi dei requisiti per l’esportazione dei dati che esulano dall’ambito di ciò che l’interfaccia utente può fornire, contatta il team Adobe account. Si possono effettuare adeguamenti speciali; i costi possono variare.

+++

+++ Quando vengono eliminati i dati da Adobe?

Contatta il tuo team Adobe Account per conoscere il periodo specifico nel quale è programmata la cancellazione dei tuoi dati. I dati vengono in genere eliminati con frequenza mensile.

+++

