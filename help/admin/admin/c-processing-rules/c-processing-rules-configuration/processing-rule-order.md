---
description: Per utilizzare in modo efficace le regole di elaborazione è essenziale comprendere quando vengono applicate durante la raccolta di dati.
seo-description: Per utilizzare in modo efficace le regole di elaborazione è essenziale comprendere quando vengono applicate durante la raccolta di dati.
seo-title: Ordine di elaborazione
solution: Analytics
subtopic: Regole di elaborazione
title: Ordine di elaborazione
topic: Strumenti di amministrazione
uuid: cea 01 d 13-dfd 5-40 f 7-8 b 2 f-b 6 e 2 fe 8354 df
translation-type: tm+mt
source-git-commit: 9942536df7c7ee4fc8da9ae4189063ca4e543b7d

---


# Ordine di elaborazione

Per utilizzare in modo efficace le regole di elaborazione è essenziale comprendere quando vengono applicate durante la raccolta di dati.

![](assets/analytics_processing_order_test.png)

Nelle tabelle seguenti sono elencati i dati disponibili in genere prima e dopo l'applicazione delle regole di elaborazione:

## Prima delle regole di elaborazione

| Dimensione | Descrizione |
|--- |--- |
| Ricerca variabile dinamica | Le variabili vengono popolate dinamicamente richiamando informazioni da intestazioni HTTP o altre variabili. For example, `s.eVar5="D=c1"` will put the value of prop1 into eVar5. |
| AppMeasurement | Le funzioni e i plug-in utilizzati in appmeasurement vengono eseguiti nel browser o nell'applicazione client. |
| Dynamic Tag Management | Le regole definite in Gestione tag dinamica vengono eseguite come definito. |
| Regole bot | [Le regole](../../../../admin/admin/bot-rules/bot-rules.md) bot consentono di rimuovere il traffico generato da spider noti e bot dalla suite di rapporti. |

## Dopo le regole di elaborazione

| Dimensione | Descrizione |
|--- |--- |
| Dati aggiunti da VISTA | Le regole di elaborazione vengono applicate prima di VISTA. |
| Numero pagina visita | Come regola generale, le regole di elaborazione sono a conoscenza dei dati contenuti solo nell'hit corrente. Il numero di pagina visita viene compilato dopo l'applicazione delle regole di elaborazione. |
| L'URL pulito viene aggiunto come nome pagina se non è impostato | Dopo l'applicazione delle regole di elaborazione e di VISTA, l'URL pulito viene aggiunto come nome della pagina se non è impostato alcun nome di pagina. Poiché questo si verifica dopo l'applicazione delle regole di elaborazione, consigliamo di aggiungere una condizione per verificare se il nome della pagina è vuoto. Se eseguite il contenuto del sito &gt; Pagine e visualizzate i valori https:// per i nomi delle pagine, è probabile che il nome della pagina sia vuoto e che l'URL sia in uso. Potete configurare una condizione per verificare il nome di una pagina vuota, oppure per verificare se il nome della pagina o l'URL della pagina contiene un valore specifico. Il nome della pagina può quindi essere impostato come necessario. |
| Regole di elaborazione canale marketing | You can use processing rules to prepare data for processing by [Marketing Channel Processing Rules](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html?f=c_rules). |
| Ricerca GEO | Sono inclusi i valori del codice Visitor State (Stato visitatore) e del codice ZIP del visitatore. |
| Persistenza evar | Le evar contenute in un hit precedente non vengono persistenti a ogni hit durante l'elaborazione delle regole. Sono disponibili solo le evar impostate sull'hit corrente. |

## How Processing Rules are Applied when Copying Hits using VISTA {#section_576EE8C240A24CBA979BD614E8D5338D}

Se hai una regola VISTA configurata per copiare hit in un'altra suite di rapporti, gli hit vengono inviati anche per tutte le regole di elaborazione definite nell'altra suite di rapporti.

Se hai regole di elaborazione definite nella suite di rapporti originale, queste possono o meno essere applicate in base alla configurazione della regola VISTA da parte di Engineering Services. Per scoprire, potete chiedere al vostro specialista di implementazione se la regola VISTA copia i valori "post" o "post" nella suite di rapporti aggiuntiva. Se il valore "pre" viene copiato, le regole di elaborazione definite nella suite di rapporti originale non vengono applicate. Se il valore "post" viene copiato, le regole di elaborazione vengono applicate prima che l'hit venga copiato.
