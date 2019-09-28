---
description: Per utilizzare in modo efficace le regole di elaborazione, è essenziale comprendere quando vengono applicate durante la raccolta dei dati.
seo-description: Per utilizzare in modo efficace le regole di elaborazione, è essenziale comprendere quando vengono applicate durante la raccolta dei dati.
seo-title: Ordine di elaborazione
solution: Analytics
subtopic: Regole di elaborazione
title: Ordine di elaborazione
topic: Strumenti di amministrazione
uuid: cea01d13-dfd5-40f7-8b2f-b6e2fe8354df
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Ordine di elaborazione

Per utilizzare in modo efficace le regole di elaborazione, è essenziale comprendere quando vengono applicate durante la raccolta dei dati.

![](assets/analytics_processing_order_test.png)

Nelle tabelle seguenti sono elencati i dati solitamente disponibili prima e dopo l'applicazione delle regole di elaborazione:

## Prima delle regole di elaborazione

| Dimensione | Descrizione |
|--- |--- |
| Ricerca di variabili dinamiche | Le variabili vengono compilate in modo dinamico recuperando informazioni dalle intestazioni HTTP o da altre variabili. Ad esempio, `s.eVar5="D=c1"` inserirà il valore di prop1 in eVar5. |
| AppMeasurement | Le funzioni e i plug-in utilizzati in AppMeasurement vengono eseguiti nel browser o nell'applicazione client. |
| Dynamic Tag Management | Le regole definite in Gestione tag dinamica vengono eseguite come definito. |
| Regole bot | [Le regole](../../../../admin/admin/bot-removal/bot-rules.md) bot consentono di rimuovere il traffico generato da spider e bot noti dalla suite di rapporti. |

## Dopo le regole di elaborazione

| Dimensione | Descrizione |
|--- |--- |
| Dati aggiunti da VISTA | Le regole di elaborazione vengono applicate prima di VISTA. |
| Numero pagina visita | Come regola generale, le regole di elaborazione sono a conoscenza dei dati contenuti solo nell'hit corrente. Il numero di pagina della visita viene compilato dopo l'applicazione delle regole di elaborazione. |
| L’URL pulito viene aggiunto come nome di pagina se non è impostato | Dopo aver applicato le regole di elaborazione e VISTA, l’URL pulito viene aggiunto come nome della pagina se non è impostato alcun nome pagina. Poiché questo si verifica dopo l'applicazione delle regole di elaborazione, si consiglia di aggiungere una condizione per verificare se il nome della pagina è vuoto.  Se eseguite il report Contenuto sito &gt; Pagine e visualizzate i valori https:// per i nomi delle pagine, è probabile che il nome della pagina sia vuoto e che l'URL sia utilizzato.  È possibile impostare una condizione per verificare la presenza di un nome di pagina vuoto o per verificare se il nome della pagina o l’URL della pagina contiene un valore specifico. Il nome della pagina può quindi essere impostato come necessario. |
| Regole di elaborazione del canale di marketing | Potete utilizzare le regole di elaborazione per preparare i dati per l'elaborazione tramite le regole [di elaborazione dei canali](https://marketing.adobe.com/resources/help/en_US/mchannel/c_rules.html)Marketing. |
| Ricerca GEO | Questo include i valori del codice postale per lo stato del visitatore e il codice postale del visitatore. |
| persistenza eVar | Le eVar contenute in un hit precedente non persistono in ogni hit durante l'elaborazione della regola. Sono disponibili solo le eVar impostate sull’hit corrente in elaborazione. |

## Modalità di applicazione delle regole di elaborazione durante la copia degli hit tramite VISTA {#section_576EE8C240A24CBA979BD614E8D5338D}

Se hai una regola VISTA configurata per copiare gli hit in un’altra suite di rapporti, gli hit vengono inviati attraverso qualsiasi regola di elaborazione definita nell’altra suite di rapporti.

Se nella suite di rapporti originale sono definite delle regole di elaborazione, queste possono essere applicate o meno in base alla configurazione della regola VISTA da parte di Engineering Services. Per maggiori informazioni, puoi chiedere al tuo specialista dell'implementazione se la regola VISTA copia i valori "pre" o "post" nella suite di rapporti aggiuntiva. Se il valore "pre" viene copiato, le regole di elaborazione definite nella suite di rapporti originale non vengono applicate. Se il valore "post" viene copiato, le regole di elaborazione vengono applicate prima che l’hit venga copiato.
