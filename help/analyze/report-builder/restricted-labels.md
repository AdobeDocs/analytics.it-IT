---
title: Cosa sono le etichette per limitazioni in Report Builder
description: Descrive le etichette per limitazioni in Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: aa2182f9-a140-4239-b2fb-f723e2767260
source-git-commit: c333a82848ed74a002a07f8c5e2857426a78425c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 49%

---

# Etichette per limitazioni in Report Builder

In genere, le impostazioni relative alla governance dei dati in Adobe Analytics vengono ereditate da Adobe Experience Platform. L’integrazione tra Adobe Analytics e Governance dei dati di Adobe Experience Platform consente l’etichettatura dei dati Adobe Analytics sensibili e l’applicazione delle politiche sulla privacy.

Le etichette per la privacy e i criteri creati sui set di dati utilizzati da Experience Platform possono essere visualizzati nel flusso di lavoro delle suite di rapporti di Adobe Analytics. Queste etichette interrompono o avvertono gli utenti che creano metriche e/o dimensioni da campi sensibili. Per informazioni sui set di dati, consulta [Panoramica sui set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=it)

Inoltre, quando i dati vengono esportati da Adobe Analytics (tramite reporting, esportazione, API, ecc.), vengono aggiunti avvisi o etichette per avvisare gli utenti che un rapporto contiene informazioni sensibili che devono essere trattate in un modo specifico.

Questa integrazione consente di gestire più facilmente la conformità. Gli amministratori di dati della tua organizzazione possono impostare criteri per limitare l’utilizzo. Di conseguenza, gli utenti di Adobe Analytics possono utilizzare i dati in modo più affidabile, sapendo che sono conformi ai criteri definiti dagli amministratori dei dati.

Per ulteriori informazioni, consulta [Adobe Analytics e governance dei dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=it)

## Visualizzazione dei dati con limitazioni in Report Builder

In Adobe Analytics vengono visualizzati due criteri definiti da Adobe che influiscono su reporting, download e condivisione:

* Criterio Enforce Analytics (Applica analisi)
* Criterio Enforce Download (Applica download)

I componenti interessati da questi criteri sono visualizzati in grigio. Quando passi il puntatore su un componente a cui è stato applicato un criterio, viene visualizzata una nota per indicare che **a questo campo sono stati applicati criteri che impediscono l’utilizzo dei dati.** Per ulteriori informazioni consulta [Etichette e criteri](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=it).

![Nota del criterio che indica l&#39;utilizzo non consentito dei dati.](assets/rb-restricted-label.png)

## Aggiornare i rapporti contenenti dati con limitazioni

Nei casi in cui un utente abbia creato in Report Builder un rapporto con elementi dati a cui sono state successivamente applicate delle limitazioni, quando il rapporto viene aggiornato viene visualizzato un messaggio di errore.

![Messaggio di errore visualizzato dopo che gli elementi dati saranno stati sottoposti a restrizioni in un secondo momento.](assets/error-restricted-data.png)
