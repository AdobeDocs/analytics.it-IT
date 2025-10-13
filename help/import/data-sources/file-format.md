---
title: Formato del file di origine dati
description: Genera correttamente un file da utilizzare nelle origini dati.
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
role: Admin
source-git-commit: cc25fe304d9cab3db3fa2ddd306338ff3bb88a55
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 5%

---

# Formato del file di origine dati

I file di origine dati hanno le seguenti proprietà:

* Il file è in formato `.txt`.
* Le righe con commenti iniziano con &#39;`#`&#39; e sono facoltative.
* La prima riga senza commenti contiene le intestazioni del file.
* Il primo valore di ogni riga è la data, con formato `MM/DD/YYYY` o `MM/DD/YYYY/HH/mm/SS`.
* I valori su ogni riga, comprese le intestazioni, sono delimitati da tabulazioni.
* Ogni riga deve avere almeno una dimensione e una metrica.

## Commenti

Qualsiasi riga che inizia con &#39;`#`&#39; è un commento. Quando si scarica un file modello di origine dati, le prime due righe sono commenti.

* Il primo commento indica il tipo di modello configurato per l&#39;origine dati, l&#39;ID utente backend che ha creato l&#39;origine dati e l&#39;ID origine dati.
* Il secondo commento fornisce nomi descrittivi per ciascuna delle intestazioni incluse nel file modello.

Tutte le righe di commento vengono ignorate da Adobe durante l’elaborazione del file, per consentire di rimuovere i commenti del modello o aggiungerne di nuovi in tutto il file. È possibile aggiungere commenti solo a righe intere, ma non a singoli campi o a righe parziali.

## Intestazioni

Durante il caricamento di file di origine dati, sono necessarie intestazioni di colonna. Nelle intestazioni di colonna non viene fatta distinzione tra maiuscole e minuscole, ma sono necessari spazi obbligatori (ad esempio, `eVar1` è un&#39;intestazione non valida, mentre `EVAR 1` è valido). Le intestazioni di colonna si applicano a tutte le suite di rapporti. Utilizzare le tabelle seguenti per verificare che ogni intestazione nel file di origine dati sia impostata correttamente.

>[!TIP]
>
>È possibile creare un file di origini dati da zero se si includono le intestazioni corrette nel file di origine dati. Non esiste alcun limite al numero di intestazioni che è possibile includere in un singolo file; tuttavia, ogni riga può avere solo un massimo di 4096 byte.

| Dimensione | Intestazione origine dati |
| --- | --- |
| [Categoria](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [Canale di marketing](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [Dettagli canale di marketing](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [Prodotto](/help/components/dimensions/product.md) | `Product` |
| [Codice di tracciamento](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [ID transazione](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [Codice di avviamento postale](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Dimensioni e metriche vanno nella stessa riga di intestazione.

| Metrica | Intestazione origine dati |
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

Adobe non supporta origini dati per altre dimensioni o metriche. Se sono necessarie variabili oltre a quelle elencate nelle tabelle precedenti, provare a utilizzare l&#39;[API di inserimento dati in blocco](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).

## Data

Il primo valore in ogni riga **deve** essere la data. Il formato della data deve essere uno dei seguenti:

* **`MM/DD/YYYY/HH/mm/SS`**
* **`MM/DD/YYYY`**

Se si omettono le ore/minuti/secondi, la marca temporale viene impostata automaticamente sulle 12 di quel giorno.

Un singolo file di origine dati supporta fino a 90 giorni univoci. Se vuoi includere più di 90 giorni univoci in un caricamento, suddividi i dati in più file.

## Dati Dimension e metriche

I valori successivi dopo la data in ogni riga contengono i dati da caricare. Ogni riga corrisponde alla rispettiva marca temporale. Assicurati che su ogni riga esista lo stesso numero di schede. Le colonne possono essere in qualsiasi ordine; assicurati che i dati in ogni riga siano allineati con le intestazioni nella parte superiore. La quantità massima di dati che una singola riga può avere è di 4096 byte.

I dati di Dimension non possono contenere punti e virgola (`;`). Le righe contenenti punti e virgola vengono ignorate.

## Passaggi successivi

[Caricamento file](file-upload.md): scopri come caricare un file di origini dati da acquisire tramite Adobe.
