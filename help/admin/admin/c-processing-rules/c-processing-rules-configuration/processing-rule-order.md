---
description: Per utilizzare in modo efficace le regole di elaborazione è essenziale capire quando vengono applicate durante la raccolta dei dati.
subtopic: Processing rules
title: Ordine di elaborazione
feature: Processing Rules
exl-id: c7143527-017c-4550-b55e-09ea437d7c85
source-git-commit: 71b3b1937e7fa272f0497008e8e510204bbb4418
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 100%

---

# Ordine di elaborazione

Per utilizzare in modo efficace le regole di elaborazione è essenziale capire quando vengono applicate durante la raccolta dei dati.

![](assets/analytics_processing_order_test.png)

Nelle tabelle seguenti sono elencati i dati generalmente disponibili prima e dopo l’applicazione delle regole di elaborazione:

## Prima delle regole di elaborazione

| Dimensione | Descrizione |
|--- |--- |
| Ricerca dinamica delle variabili | Le variabili vengono compilate dinamicamente estraendo informazioni dalle intestazioni HTTP o da altre variabili. Ad esempio: `s.eVar5="D=c1"` inserirà il valore di prop1 in eVar5. |
| AppMeasurement | Le funzioni e i plug-in utilizzati in AppMeasurement vengono eseguiti nel browser o nell’applicazione client. |
| Tag Management | Le regole definite nell’interfaccia utente della raccolta dati vengono eseguite come definito. |
| Regole bot | Le [regole bot](/help/admin/admin/bot-removal/bot-rules.md) consentono di rimuovere dalla suite di rapporti il traffico generato da spider e bot noti. |

## Dopo le regole di elaborazione

| Dimensione | Descrizione |
|--- |--- |
| Dati aggiunti da VISTA | Le regole di elaborazione vengono applicate prima di VISTA. |
| Numero pagina di visita | Come regola generale, le regole di elaborazione tengono conto dei dati contenuti solo nell’hit corrente. Il numero di pagina della visita viene compilato dopo l’applicazione delle regole di elaborazione. |
| L’URL pulito viene aggiunto come nome della pagina, se non impostato | Dopo aver applicato le regole di elaborazione e VISTA, l’URL pulito viene aggiunto come nome della pagina se quest’ultimo non è stato impostato. Poiché questo si verifica dopo l’applicazione delle regole di elaborazione, è consigliabile aggiungere una condizione per verificare se il nome della pagina è vuoto. Se esegui il rapporto Site Content > Pages (Contenuto sito > Pagine) e trovi dei valori https:// per i nomi di pagina, è probabile che il nome della pagina sia vuoto e che quindi sia stato usato l’URL.  È possibile impostare una condizione per verificare la presenza di un nome di pagina vuoto o per verificare se il nome o l’URL della pagina contiene un valore specifico. Il nome della pagina può quindi essere impostato in base alle esigenze. |
| Regole di elaborazione per il canale di marketing | È possibile utilizzare le regole di elaborazione per preparare i dati per le [regole di elaborazione del canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=it). |
| Ricerca geografica | Questo include i valori dello Stato e del codice postale del visitatore. |
| Persistenza eVar | Le eVar contenute in un hit precedente non vengono mantenute in ogni hit durante l’elaborazione delle regole. Sono disponibili solo le eVar impostate sull’hit attualmente in fase di elaborazione. |

## Applicazione delle regole di elaborazione durante la copia degli hit tramite VISTA {#section_576EE8C240A24CBA979BD614E8D5338D}

Se disponi di una regola VISTA configurata per copiare gli hit in un’altra suite di rapporti, gli hit vengono trattati dalle regole di elaborazione definite nell’altra suite di rapporti.

Se nella suite di rapporti originale sono definite regole di elaborazione, queste possono essere applicate o meno in base alla configurazione della regola VISTA da parte di Engineering Services. Per informazioni, puoi chiedere al tuo specialista dell’implementazione se la regola VISTA copia i valori “prima” o “dopo” nella suite di rapporti aggiuntiva. Se viene copiato il valore “prima”, le regole di elaborazione definite nella suite di rapporti originale non vengono applicate. Se viene copiato il valore “dopo”, le regole di elaborazione vengono applicate prima che l’hit venga copiato.
