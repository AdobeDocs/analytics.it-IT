---
description: Dimensioni e metriche disponibili che è possibile leggere e scrivere utilizzando le regole di elaborazione.
subtopic: Processing rules
title: Dimensioni e metriche disponibili per le regole di elaborazione
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 9%

---

# Dimensioni e metriche disponibili per le regole di elaborazione

Dimensioni e metriche disponibili che è possibile leggere e scrivere utilizzando le regole di elaborazione.

## Valori personalizzati e dati contestuali

| Valore | Stato lettura/scrittura | Descrizione |
| --- | --- | --- |
| **Valore personalizzato** | Sola lettura | Testo o valori personalizzati digitati direttamente nell’azione di una regola di elaborazione. |
| **Valore concatenato** | Sola lettura | Valori creati combinando due valori. Ad esempio, è possibile combinare il nome del canale e della pagina per creare una sottocategoria. |

## Attributi di hit

| Attributo | Stato lettura/scrittura | Descrizione |
| --- | --- | --- |
| **URL della pagina** | Lettura e scrittura | La dimensione [URL pagina](/help/components/dimensions/page-url.md). Gli hit di tracciamento dei collegamenti eliminano questa dimensione prima di raggiungere le regole di elaborazione. Se inserisci nuovamente un valore URL della pagina utilizzando le regole di elaborazione, l&#39;hit viene considerato come [Visualizzazione pagina](/help/components/metrics/page-views.md) invece di [Evento pagina](/help/components/metrics/page-events.md). Adobe consiglia di verificare la presenza di un valore nella dimensione pagina prima di modificarlo. |
| **Nome pagina** | Lettura e scrittura | La dimensione [Pagina](/help/components/dimensions/page.md). Gli hit di tracciamento dei collegamenti eliminano questa dimensione prima di raggiungere le regole di elaborazione. Se inserisci nuovamente un valore di pagina utilizzando le regole di elaborazione, l&#39;hit viene considerato come [Visualizzazione pagina](/help/components/metrics/page-views.md) invece di [Evento pagina](/help/components/metrics/page-events.md). Adobe consiglia di verificare la presenza di un valore nella dimensione pagina prima di modificarlo. |
| **ID suite di rapporti** | Sola lettura | La suite di rapporti su cui viene eseguita la regola di elaborazione. Questa suite di rapporti può essere diversa dalla suite di rapporti inviata originariamente tramite AppMeasurement, ad esempio quando si utilizzano le regole VISTA. |
| **Versione codice AppMeasurement** | Sola lettura | Versione della libreria AppMeasurement utilizzata per generare la richiesta di immagine. |
| **Indirizzo IP** | Sola lettura | L’indirizzo IP del visitatore. |
| **Agente utente** | Sola lettura | Agente utente del visitatore. |
| **Referrer** | Sola lettura | La dimensione [Referrer](/help/components/dimensions/referrer.md). |
| **Parametro stringa query** | Sola lettura | Il valore di un parametro di stringa di query specificato nell’URL corrente. |
| **Parametro stringa query di riferimento** | Sola lettura | Il valore di un parametro di stringa di query specificato nell’URL di riferimento o una stringa vuota se non ne esiste alcuna. |
| **Dominio di riferimento** | Sola lettura | Il dominio della pagina dell’URL di riferimento, inclusi i sottodomini. |
| **Dominio principale di riferimento** | Sola lettura | Il dominio della pagina dell’URL di riferimento, esclusi i sottodomini. |
| **Stringa query pagina** | Sola lettura | Tutti i parametri della stringa di query e i relativi valori nell’URL corrente. |
| **Stringa di query di riferimento** | Sola lettura | Tutti i parametri della stringa di query e i relativi valori nell’URL di riferimento. |
| **Percorso pagina** | Sola lettura | Percorso della pagina dell’URL corrente. Il percorso della pagina non include i parametri di protocollo, dominio o stringa di query. |
| **Dominio pagina** | Sola lettura | Il dominio della pagina dell’URL corrente, inclusi i sottodomini. Il dominio della pagina non include il percorso della pagina o i parametri della stringa di query. |
| **Dominio principale pagina** | Sola lettura | Il dominio della pagina dell’URL corrente, esclusi i sottodomini. |
| **Prospettiva del cliente** | Lettura e scrittura | Flag che determina se l’hit è un hit di sfondo per dispositivi mobili. |

## Variabili di conversione

| Variabile | Stato lettura/scrittura | Descrizione |
| --- | --- | --- |
| **eVar 1-250** | Lettura e scrittura | [dimensioni eVar](/help/components/dimensions/evar.md). |
| **Campaign** | Lettura e scrittura | La dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md). |
| **ID acquisto** | Lettura e scrittura | La variabile di implementazione [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). |
| **Stato** | Lettura e scrittura | (Ritirato) La variabile di implementazione [`state`](/help/implement/vars/page-vars/state.md). |
| **ZIP** | Lettura e scrittura | La dimensione [Codice postale](/help/components/dimensions/zip-code.md). |
| **Codice valuta** | Lettura e scrittura | La variabile di implementazione [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). IMPORTANTE: se imposti questa variabile su un valore non valido, l’hit viene scartato. |
| **ID transazione** | Lettura e scrittura | La variabile di implementazione [`transactionID`](/help/import/data-sources/transactionid.md). |

>[!NOTE]
>Adobe non supporta l&#39;impostazione della variabile di implementazione [`products`](/help/implement/vars/page-vars/products.md) tramite le regole di elaborazione.

## Variabili traffico

| Variabile | Stato lettura/scrittura | Descrizione |
| --- | --- | --- |
| **Prop 1-75** | Lettura e scrittura | [Prop](/help/components/dimensions/prop.md) dimensioni. |
| **Gerarchia 1-5** | Lettura e scrittura | (Ritirato) [Gerarchia](/help/components/dimensions/hierarchy.md) dimensioni. |
| **Server** | Lettura e scrittura | La dimensione [Server](/help/components/dimensions/server.md). |
| **Canale** | Lettura e scrittura | La dimensione [Sezione del sito](/help/components/dimensions/site-section.md). |

## Variabili di contesto

Tutte le [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) visualizzate da questa suite di rapporti negli ultimi 30 giorni. Per esempi di utilizzo, vedi [Casi di utilizzo delle regole di elaborazione](pr-use-cases.md).

>[!IMPORTANT]
>
>Se le regole di elaborazione non mappano una determinata variabile di dati di contesto a un’altra variabile (ad esempio una proprietà o un’eVar), il valore nella variabile di dati di contesto viene perso definitivamente.

## Eventi di successo

Le regole di elaborazione possono impostare gli eventi ma non possono leggerli come condizioni. Impostare l&#39;elenco a discesa dell&#39;azione regola su **[!UICONTROL Set event]** per visualizzare le metriche disponibili da incrementare.

| Variabile | Stato lettura/scrittura | Descrizione |
| --- | --- | --- |
| **Ordini** | Solo scrittura | La metrica [Ordini](/help/components/metrics/orders.md). |
| **Carrelli** | Solo scrittura | La metrica [Carrelli](/help/components/metrics/carts.md). |
| **Visualizzazioni del carrello** | Solo scrittura | La metrica [Visualizzazioni carrello](/help/components/metrics/cart-views.md). |
| **Pagamenti** | Solo scrittura | La metrica [Casse](/help/components/metrics/checkouts.md). |
| **Aggiunte al carrello** | Solo scrittura | La metrica [Aggiunte carrello](/help/components/metrics/cart-additions.md). |
| **Rimozioni dal carrello** | Solo scrittura | La metrica [Rimozioni dal carrello](/help/components/metrics/cart-removals.md). |
| **Evento 1-1000** | Solo scrittura | [Eventi personalizzati](/help/components/metrics/custom-events.md). |
| **Visualizzazioni di prodotti** | Solo scrittura | La metrica [Visualizzazioni prodotto](/help/components/metrics/product-views.md). |
