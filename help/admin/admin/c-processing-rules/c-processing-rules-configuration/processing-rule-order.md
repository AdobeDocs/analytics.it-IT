---
description: Per utilizzare in modo efficace le regole di elaborazione, è essenziale comprendere quando vengono applicate durante la raccolta dei dati.
subtopic: Processing rules
title: Ordine di elaborazione
topic: Admin tools
uuid: cea01d13-dfd5-40f7-8b2f-b6e2fe8354df
translation-type: tm+mt
source-git-commit: 31506d4d3fa26a3012cce2c6a8fdeb7af52c2537
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 1%

---


# Ordine di elaborazione

Per utilizzare in modo efficace le regole di elaborazione, è essenziale comprendere quando vengono applicate durante la raccolta dei dati.

![](assets/analytics_processing_order_test.png)

Nelle tabelle seguenti sono elencati i dati solitamente disponibili prima e dopo l&#39;applicazione delle regole di elaborazione:

## Prima delle regole di elaborazione

| Dimensione | Descrizione |
|--- |--- |
| Ricerca di variabili dinamiche | Le variabili vengono compilate in modo dinamico recuperando informazioni dalle intestazioni HTTP o da altre variabili. Ad esempio, `s.eVar5="D=c1"` inserisce il valore di prop1 in  eVar 5. |
| AppMeasurement | Le funzioni e i plug-in utilizzati in AppMeasurement vengono eseguiti nel browser o nell&#39;applicazione client. |
| Gestione tag | Le regole definite in Lancio  Adobe o Gestione tag dinamica vengono eseguite come definito. |
| Regole bot | [Le regole](/help/admin/admin/bot-removal/bot-rules.md) bot consentono di rimuovere il traffico generato da spider e bot noti dalla suite di rapporti. |

## Dopo le regole di elaborazione

| Dimensione | Descrizione |
|--- |--- |
| Dati aggiunti da VISTA | Le regole di elaborazione vengono applicate prima di VISTA. |
| Numero pagina visita | Come regola generale, le regole di elaborazione sono a conoscenza dei dati contenuti solo nell&#39;hit corrente. Il numero di pagina della visita viene compilato dopo l&#39;applicazione delle regole di elaborazione. |
| L’URL pulito viene aggiunto come nome di pagina se non è impostato | Dopo aver applicato le regole di elaborazione e VISTA, l’URL pulito viene aggiunto come nome della pagina se non è impostato alcun nome pagina. Poiché questo si verifica dopo l&#39;applicazione delle regole di elaborazione, si consiglia di aggiungere una condizione per verificare se il nome della pagina è vuoto.  Se eseguite il report Contenuto sito > Pagine e visualizzate i valori https:// per i nomi delle pagine, è probabile che il nome della pagina sia vuoto e che l&#39;URL sia utilizzato.  È possibile impostare una condizione per verificare la presenza di un nome di pagina vuoto o per verificare se il nome della pagina o l’URL della pagina contiene un valore specifico. Il nome della pagina può quindi essere impostato come necessario. |
| Regole di elaborazione del canale di marketing | Potete utilizzare le regole di elaborazione per preparare i dati per l&#39;elaborazione tramite le regole [di elaborazione dei canali](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-rules.html)Marketing. |
| Ricerca GEO | Questo include i valori del codice postale per lo stato del visitatore e il codice postale del visitatore. |
| persistenza eVar | Le eVar contenute in un hit precedente non persistono in ogni hit durante l&#39;elaborazione della regola. Sono disponibili solo le eVar impostate sull’hit corrente in fase di elaborazione. |

## Modalità di applicazione delle regole di elaborazione durante la copia degli hit tramite VISTA {#section_576EE8C240A24CBA979BD614E8D5338D}

Se hai una regola VISTA configurata per copiare gli hit in un’altra suite di rapporti, gli hit vengono inviati tramite tutte le regole di elaborazione definite nell’altra suite di rapporti.

Se nella suite di rapporti originale sono definite delle regole di elaborazione, queste possono essere applicate o meno in base alla configurazione della regola VISTA da parte di Engineering Services. Per maggiori informazioni, puoi chiedere al tuo specialista dell&#39;implementazione se la regola VISTA copia i valori &quot;pre&quot; o &quot;post&quot; nella suite di rapporti aggiuntiva. Se il valore &quot;pre&quot; viene copiato, le regole di elaborazione definite nella suite di rapporti originale non vengono applicate. Se il valore &quot;post&quot; viene copiato, le regole di elaborazione vengono applicate prima che l’hit venga copiato.
