---
description: Procedura per prepararsi all'utilizzo delle origini dati
subtopic: Data sources
title: Preparazione all'utilizzo di Origini dati
topic: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Prepararsi a utilizzare Origini dati

Procedura per prepararsi all&#39;utilizzo delle origini dati

* [Identificare e denominare le metriche](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [Identificare le dimensioni dei dati](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [Codice di tracciamento campagna](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [ID transazione](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [Identificare un intervallo di date valido per i dati di origine dati](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## Identificare e denominare le metriche {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

È importante comprendere le metriche o le misurazioni contenute nelle origini dati, ad esempio *`Off-line Sales Revenue by Product`*, *`Returns by Product`* o *`Ad Impressions by Campaign`*. Questi sono i nomi che puoi associare alle metriche del rapporto (eventi, prop ed eVar).

Dopo aver determinato le mappature metrica-evento appropriate per i dati Origini dati, rinominare gli eventi con nomi descrittivi appropriati per la metrica Origini dati associata.

Consulta Eventi di [successo](https://marketing.adobe.com/resources/help/it_IT/reference/success_event.html) nell’Aiuto di Strumenti di amministrazione.

>[!NOTE] Adobe consiglia vivamente di utilizzare eventi nuovi e vuoti con i dati Origini dati, ma in alcuni rari casi potrebbe essere utile utilizzare un evento preesistente.

## Identificare le dimensioni dei dati {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

Identifica e raccogli i dati (rapporti) che desideri utilizzare per suddividere le metriche importate tramite Origini dati. Questi dati sono noti come *`data dimensions`*.

Ad esempio, se una metrica Origini dati misura ad impression, la dimensione dati è probabilmente il codice di tracciamento della campagna. Se stai misurando le vendite offline, potresti voler usare il codice prodotto (o SKU) come dimensione dati.

Puoi definire più dimensioni dati per una metrica, ma ogni metrica deve fornire un valore rilevante, o una combinazione di valori, per ogni dimensione dati associata. Ad esempio, se importi una metrica Vendita offline e la associ alle dimensioni *`Product`* e ai *`Partner`* dati, la metrica Vendite offline deve essere pertinente per ogni combinazione di prodotto e partner (ad esempio, Ricavi totali).

>[!NOTE] È possibile importare metriche Totale che non possono essere suddivise per alcuna dimensione dati.

Dopo aver definito le dimensioni dati da utilizzare con un&#39;origine dati, integra i dati delle dimensioni nei rapporti di marketing mappandoli a una variabile. Utilizzate rapporti standard (ad esempio, Prodotto, Codice di tracciamento, Parola chiave di ricerca) o variabili Traffico conversione (eVar).

Quando si utilizzano le eVar, è possibile utilizzare eVar esistenti o nuove come dimensioni dati. Dopo aver selezionato un&#39;eVar per ricevere una dimensione dati da Origini dati, accertati di denominarla correttamente.

Consultate Eventi di [successo](https://marketing.adobe.com/resources/help/it_IT/reference/success_event.html) nell&#39;Aiuto di Analytics.

## Codice di tracciamento campagna {#section_468222796FF449ABAA90D88EB3264CB1}

Oltre a importare eventi di successo, puoi importare facoltativamente valori eVar associati. Ad esempio, se monitori l&#39;attività online con un codice di tracciamento campagna e hai codici di tracciamento campagna per le metriche offline, puoi importare le metriche con i codici di tracciamento campagna. Questo approccio consente di visualizzare sia le metriche online che offline nei rapporti delle campagne.

Se non importi le metriche Origini dati con un valore eVar associato, non puoi visualizzare le metriche Origini dati suddivise per eVar. Puoi visualizzare solo le metriche Totale.

## ID transazione {#section_D9513C1204B7496C9B738C5B12CCCFC7}

L&#39;ID transazione viene utilizzato per collegare un evento online a un evento offline.

## Identificare un intervallo di date valido per i dati di origine dati {#section_03AAB1291BDC4403BDC50905A78FDB71}

Dopo aver definito le metriche Origini dati (Eventi personalizzati) e le dimensioni dati (eVar), controlla l&#39;intervallo di date dei dati Origini dati che desideri importare. Non puoi importare Origini dati che non rientrano nell&#39;intervallo di dati di reporting esistenti.

Ad esempio, non puoi importare dati Origini dati da prima di aver implementato il tracciamento dati online. I dati Origini dati devono essere suddivisi per giorno.
