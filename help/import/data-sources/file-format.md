---
title: Formato del file di origine dati
description: Genera correttamente un file da utilizzare nelle origini dati.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 6%

---

# Formato del file di origine dati

I file di origine dati hanno le seguenti proprietà:

* Il file è in `.txt` formato.
* Le righe con commenti iniziano con &quot;`#`&quot; e sono facoltativi.
* La prima riga senza commento contiene le intestazioni del file.
* Il primo valore di ogni riga è la data, che utilizza il formato `MM/DD/YYYY` o `MM/DD/YYYY/HH/mm/SS`.
* I valori su ogni riga, comprese le intestazioni, sono delimitati da tabulazioni.
* Ogni riga deve avere almeno una dimensione e una metrica.

## Commenti

Qualsiasi riga che inizia con &#39;`#`&quot; è un commento. Quando si scarica un file modello origine dati, le prime due righe sono commenti.

* Il primo commento indica il tipo di modello configurato per l’origine dati, l’ID utente backend che ha creato l’origine dati e l’ID dell’origine dati.
* Il secondo commento fornisce nomi descrittivi per ciascuna delle intestazioni incluse nel file modello.

Tutte le righe di commento vengono ignorate per Adobe quando il file viene elaborato, in modo da poter rimuovere i commenti del modello o aggiungere il proprio in tutto il file. Possono essere commentate solo le righe intere; non è possibile commentare campi singoli o righe parziali.

## Intestazioni

Quando si caricano i file di origine dati, le intestazioni di colonna sono necessarie. Queste intestazioni di colonna non fanno distinzione tra maiuscole e minuscole, ma sono necessari spazi (ad esempio, `eVar1` è un&#39;intestazione non valida, mentre `EVAR 1` è valido). Le intestazioni di colonna si applicano a tutte le suite di rapporti. Utilizza le tabelle seguenti per assicurarti che ogni intestazione del file di origine dati sia impostata correttamente.

>[!TIP]
>
>È possibile creare un file origini dati da zero se si includono le intestazioni corrette nel file di origine dati. Non esiste alcun limite al numero di intestazioni che è possibile includere all&#39;interno di un singolo file; tuttavia, ogni riga può avere un massimo di 4096 byte.

| Dimensione | Intestazione dell&#39;origine dati |
| --- | --- |
| [Categoria](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [Canale di marketing](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [Dettaglio del canale di marketing](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [Prodotto](/help/components/dimensions/product.md) | `Product` |
| [Codice di tracciamento](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [ID transazione](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [Codice di avviamento postale](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Dimension e metriche entrano nella stessa riga di intestazione.

| Metrica | Intestazione dell&#39;origine dati |
| --- | --- |
| [Aggiunte carrello](/help/components/metrics/cart-additions.md) | `Cart Adds` |
| [Rimozioni carrello](/help/components/metrics/cart-removals.md) | `Cart Removes` |
| [Visualizzazioni carrello](/help/components/metrics/cart-views.md) | `Cart Views` |
| [Carrelli](/help/components/metrics/carts.md) | `Cart Opens` |
| [Pagamenti](/help/components/metrics/checkouts.md) | `Checkouts` |
| [Eventi personalizzati](/help/components/metrics/custom-events.md) | `Event 1` - `Event 1000` |
| [Ordini](/help/components/metrics/orders.md) | `Orders` |
| [Ricavi](/help/components/metrics/revenue.md) | `Price` |
| [Unità](/help/components/metrics/units.md) | `Quantity` |

{style="table-layout:auto"}

Adobe non supporta origini dati per altre dimensioni o metriche. Se sono necessarie variabili che vanno oltre quelle elencate nelle tabelle precedenti, considera l’utilizzo dei [API di inserimento dati in blocco](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) invece.

## Data

Il primo valore in ogni riga **deve** sia la data. Il formato della data deve essere in uno dei seguenti formati:

* **`MM/DD/YY/HH/mm/SS`**
* **`MM/DD/YY`**

Se si omette l&#39;ora/minuti/secondi, la marca temporale viene impostata automaticamente su 12 PM per quel giorno.

Un singolo file di origine dati supporta fino a 90 giorni univoci. Se desideri includere più di 90 giorni unici in un caricamento, suddividi i dati in più file.

## Dati Dimension e metrica

I valori successivi dopo la data in ogni riga contengono i dati da caricare. Ogni riga corrisponde a quella rispettiva marca temporale. Assicurati che su ogni riga esista lo stesso numero di schede. Le colonne possono essere in qualsiasi ordine; assicurati che i dati di ogni riga siano allineati con le intestazioni nella parte superiore. La quantità massima di dati che una singola riga può avere è di 4096 byte.

I dati del Dimension non possono contenere punti e virgola (`;`). Le righe contenenti punto e virgola vengono ignorate.

## Passaggi successivi

[Caricamento file](file-upload.md): Scopri il processo per caricare un file origini dati da acquisire per Adobe.
