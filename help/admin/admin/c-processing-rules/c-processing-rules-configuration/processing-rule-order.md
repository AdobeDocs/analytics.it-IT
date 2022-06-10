---
description: Dove risiedono le regole di elaborazione nella pipeline dei dati di Analytics.
subtopic: Processing rules
title: Ordine di elaborazione
feature: Processing Rules
exl-id: c7143527-017c-4550-b55e-09ea437d7c85
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 52%

---

# Ordine di elaborazione

Per utilizzare in modo efficace le regole di elaborazione, è essenziale capire quando vengono applicate durante la raccolta dei dati.

![Ordine di elaborazione](assets/analytics_processing_order.png)

Nelle tabelle seguenti sono elencati i dati generalmente disponibili prima e dopo l’applicazione delle regole di elaborazione.

## Prima delle regole di elaborazione

| Dimensione | Descrizione |
|--- |--- |
| [Variabili dinamiche](/help/implement/vars/page-vars/dynamic-variables.md) | Variabili compilate dinamicamente richiamando informazioni dalle intestazioni HTTP o da altre variabili. |
| [AppMeasurement](/help/implement/home.md) | Le funzioni e i plug-in utilizzati nelle librerie AppMeasurement vengono eseguiti nel browser o nell’applicazione client. |
| [Implementazione dei tag](/help/implement/launch/overview.md) | Regole definite nell&#39;estensione Adobe Analytics in Raccolta dati di Adobe Experience Platform. |
| [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/analytics-overview.html) | I dati raccolti tramite l’SDK per web vengono inviati ad Adobe Experience Edge e quindi inoltrati alla suite di rapporti desiderata. |
| [Regole bot](/help/admin/admin/bot-removal/bot-rules.md) | Consente di rimuovere il traffico generato da ragni e bot noti. |

## Dopo le regole di elaborazione

| Dimensione | Descrizione |
|--- |--- |
| Dati aggiunti da VISTA | Le regole di elaborazione vengono applicate prima di VISTA. |
| Numero pagina di visita | Le regole di elaborazione sono a conoscenza solo dei dati contenuti nell&#39;hit corrente. Il numero di pagina della visita viene compilato dopo l’applicazione delle regole di elaborazione. |
| L’URL pulito viene aggiunto come nome della pagina, se non impostato | Dopo aver applicato le regole di elaborazione e VISTA, l’URL pulito viene aggiunto come nome della pagina se quest’ultimo non è stato impostato. Poiché questa logica si verifica dopo l’applicazione delle regole di elaborazione, Adobe consiglia di aggiungere una condizione per verificare se il nome della pagina è vuoto.  Se esegui la **[!UICONTROL Site Content]** > **[!UICONTROL Pages]** Il rapporto e i valori URL visualizzati per i nomi di pagina sono probabilmente vuoti.  È possibile impostare una condizione per verificare la presenza di un nome di pagina vuoto o per verificare se il nome della pagina o l’URL della pagina contiene un valore specifico. Il nome della pagina può quindi essere impostato in base alle esigenze. |
| Regole di elaborazione per il canale di marketing | È possibile utilizzare le regole di elaborazione per preparare i dati per le [regole di elaborazione del canale di marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=it). |
| Ricerca geografica | Include i valori di Stato visitatore e CAP/postale del visitatore. |
| Persistenza eVar | Le eVar contenute in un hit precedente non vengono mantenute in ogni hit durante l’elaborazione delle regole. Sono disponibili solo le eVar impostate sull’hit attualmente in fase di elaborazione. |

## Applicazione delle regole di elaborazione durante la copia degli hit tramite VISTA

Se disponi di una regola VISTA configurata per copiare gli hit in un’altra suite di rapporti, gli hit vengono trattati dalle regole di elaborazione definite nell’altra suite di rapporti.

Se nella suite di rapporti originale sono definite regole di elaborazione, queste possono essere applicate o meno in base alla configurazione della regola VISTA da parte di Engineering Services. Per informazioni, puoi chiedere al tuo specialista dell’implementazione se la regola VISTA copia i valori “prima” o “dopo” nella suite di rapporti aggiuntiva. Se viene copiato il valore “prima”, le regole di elaborazione definite nella suite di rapporti originale non vengono applicate. Se viene copiato il valore “dopo”, le regole di elaborazione vengono applicate prima che l’hit venga copiato.
