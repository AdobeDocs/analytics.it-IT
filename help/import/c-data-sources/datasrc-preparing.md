---
description: 'Procedura per prepararsi all''utilizzo di Origini dati:'
subtopic: Data sources
title: Preparazione all'utilizzo di Origini dati
topic-fix: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
exl-id: 3cad7c33-f31c-41a2-9dd2-9535713c7620
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 85%

---

# Preparare l&#39;utilizzo di Origini dati

Procedura per prepararsi all&#39;utilizzo di Origini dati

* [Identificare e denominare le metriche](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [Identificare le dimensioni dei dati](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [Codice di tracciamento campagna](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [ID transazione](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [Identificare un intervallo di date valido per i dati di Origini dati](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## Identificare e denominare le metriche {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

È importante comprendere le metriche o le misurazioni contenute nelle origini dati, ad esempio *`Off-line Sales Revenue by Product`*, *`Returns by Product`* o *`Ad Impressions by Campaign`*. Questi sono i nomi che puoi associare alle metriche del rapporto (eventi, proprietà e eVar).

Dopo aver determinato le mappature metrica-evento opportune per i dati Origini dati, rinominare gli eventi con nomi descrittivi adatti alla metrica Origini dati associata.

Consulta [Eventi di successo](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/success-events/success-event.html) nell&#39;Aiuto di Strumenti di amministrazione.

>[!NOTE]
>
>Adobe consiglia vivamente di utilizzare eventi nuovi e vuoti con i dati Origini dati, ma in rari casi potrebbe essere utile utilizzare un evento preesistente.

## Identificare le dimensioni dei dati {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

Identificare e raccogliere i dati (rapporti) da utilizzare per suddividere le metriche importate tramite Origine dati. Questi dati sono noti come *`data dimensions`*.

Ad esempio, se una metrica Origini dati misura ad impression, la dimensione dati è probabilmente il codice di tracciamento campagna. Se stai misurando una vendita offline, potresti voler utilizzare il codice prodotto (o SKU) come dimensione dati.

Puoi definire più dimensioni dati per una metrica, ma ogni metrica deve fornire un valore rilevante, o una combinazione di valori, per ogni dimensione dati associata. Ad esempio, se importi una metrica Vendita offline e la associ alle dimensioni dati  *`Product`* e le dimensioni  *`Partner`* dei dati, la metrica Vendite offline deve essere rilevante per ogni combinazione di prodotto e partner (ad esempio, Entrate totali).

>[!NOTE]
>
>È possibile importare le metriche Totale che non possono essere suddivise per alcuna dimensione dati.

Dopo aver definito le dimensioni dati da utilizzare con un&#39;origine dati, integra i dati delle dimensioni nei rapporti di marketing mappandoli a una variabile. Usa i rapporti standard (ad esempio, Prodotto, Codice di tracciamento, Cerca parola chiave) o le variabili Traffico conversione (eVars).

Quando utilizzi eVar, puoi usare eVar esistenti o nuove come dimensioni dati. Dopo aver selezionato un&#39;eVar per ricevere una dimensione dati da Origini dati, accertati di denominarla correttamente.

Consulta [Eventi di successo](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) nell&#39;Aiuto di Analytics.

## Codice di tracciamento campagna  {#section_468222796FF449ABAA90D88EB3264CB1}

Oltre a importare eventi di successo, puoi importare facoltativamente valori eVar associati. Ad esempio, se monitori l&#39;attività online con un codice di tracciamento campagna, e hai codici di tracciamento campagna per le metriche offline, puoi importare le metriche con i codici di tracciamento campagna. Questo approccio ti consente di visualizzare le metriche online e offline nei rapporti Campagna.

Se non importi le metriche Origini dati con un valore eVar associato, non puoi visualizzare le metriche Origini dati suddivise per eVar. Puoi visualizzare solo le metriche Totale.

## ID transazione {#section_D9513C1204B7496C9B738C5B12CCCFC7}

L&#39;ID transazione viene utilizzato per collegare un evento online a un evento offline.

## Identificare un intervallo di date valido per i dati di Origini dati  {#section_03AAB1291BDC4403BDC50905A78FDB71}

Dopo aver definito le metriche di Origini dati (Eventi personalizzati) e le dimensioni dati (eVar), controlla l&#39;intervallo di date dei dati Origini dati da importare. Non puoi importare Origini dati che non rientrano nell&#39;intervallo di dati di reporting esistenti.

Ad esempio, non puoi importare dati Origini dati da prima che implementassi il tracciamento dati online. I dati Origini dati devono essere suddivisi per giorno.
