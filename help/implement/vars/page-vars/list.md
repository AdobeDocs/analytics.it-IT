---
title: list
description: Variabili personalizzate che contengono più valori nello stesso hit.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 0%

---


# list

Le variabili di elenco sono variabili personalizzate che potete utilizzare come desiderate. Funzionano in modo simile alle eVar, ma possono contenere più valori nello stesso hit. Le variabili di elenco non hanno un limite di caratteri.

Accertatevi di registrare come usate ciascuna variabile di elenco e la relativa logica nel documento [di progettazione della](../../prepare/solution-design.md)soluzione.

>[!NOTE]
>
>Le variabili elenco memorizzano i 250 valori più recenti per visitatore. Se per un determinato visitatore sono presenti più di 250 valori univoci, i valori più vecchi non vengono attribuiti alle metriche.

## Impostare le variabili dell&#39;elenco nelle impostazioni della suite di rapporti

Accertatevi di configurare ogni variabile dell&#39;elenco nelle impostazioni della suite di rapporti prima di utilizzarla nell&#39;implementazione. Consulta Variabili [di](/help/admin/admin/conversion-var-admin/list-var-admin.md) conversione nella guida di amministrazione.

## Elenca le variabili in  Adobe Experience Platform Launch

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.list1 - s.list3 nell&#39;editor di codice personalizzato AppMeasurement e Launch

Ogni variabile dell&#39;elenco è una stringa che contiene valori personalizzati specifici per l&#39;organizzazione. Non hanno un numero massimo di byte; tuttavia, ogni singolo valore ha un massimo di 255 byte. Il carattere di delimitazione utilizzato viene determinato durante la configurazione della variabile nelle impostazioni della suite di rapporti. Non utilizzate gli spazi per delimitare più elementi.

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>Se impostate valori duplicati nello stesso hit, Adobe deduplica tutte le istanze di tali valori. Ad esempio, se impostate `s.list1 = "Example,Example";`, un&#39;istanza viene conteggiata nei report.

## Confronta proprietà elenco con variabili elenco

Le proprietà elenco e le variabili elenco possono contenere più valori nello stesso hit. Esistono tuttavia diverse differenze chiave tra questi due tipi di variabili.

* Qualsiasi proprietà può diventare una proprietà elenco. È possibile avere fino a 75 proprietà elenco, se ogni prop è un prop elenco. Sono disponibili solo 3 variabili elenco.
* Le proprietà elenco hanno un limite di 100 byte per l&#39;intera variabile. Le variabili di elenco hanno un limite di 255 byte per valore e nessun limite totale di byte.
* Le proprietà elenco non persistono oltre l’hit impostato. Le variabili elenco dispongono di un’impostazione di scadenza. Tuttavia, con l&#39;elaborazione [del tempo del](/help/components/vrs/vrs-report-time-processing.md)rapporto, potete applicare l&#39;attribuzione personalizzata sia alle proprietà dell&#39;elenco che alle variabili dell&#39;elenco.
