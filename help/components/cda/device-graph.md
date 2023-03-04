---
title: Device Graph
description: Comprendi i prerequisiti e le limitazioni dell’unione di dati utilizzando il grafico dei dispositivi.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 7%

---

# Device Graph

Analytics tra dispositivi può utilizzare Private Graph per unire i dati. Private Graph è un archivio di ID dispositivo con hash specifico per la tua organizzazione. CDA comunica regolarmente con il grafico dei dispositivi per collegare i dispositivi.

## Prerequisiti specifici per il grafico dei dispositivi

Se intendi implementare Cross-Device Analytics utilizzando il metodo del grafico dei dispositivi, sono necessari i seguenti elementi. Collabora con i team della tua organizzazione e con il tuo account team Adobe per assicurarti di soddisfare tutte le seguenti esigenze.

>[!WARNING]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di abilitare Cross-Device Analytics o risultati errati durante l’unione dei dati.

* Tutti i prerequisiti elencati in [pagina panoramica](overview.md).
* La tua organizzazione deve utilizzare [Grafico privato del servizio Adobe Experience Platform Identity](https://business.adobe.com/products/experience-platform/identity-service.html). Consulta anche [Home page](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it) nella guida utente del servizio Identity.
* L&#39;implementazione deve utilizzare la versione più recente del servizio ID Experience Cloud (ECID). Consulta la [Home page](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) nella guida utente del servizio ID. La maggior parte delle implementazioni di [Tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it) in Adobe Experience Platform probabilmente il servizio ID è già stato distribuito.
* L’implementazione deve chiamare `setCustomerIDs` (o equivalente all’SDK) ogni volta che un individuo può essere identificato, ad esempio quando un utente accede o apre un’e-mail. Questo requisito si applica a tutte le piattaforme, incluse le app mobili se utilizzate. Consulta [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) nella guida utente del servizio ID.

## Limitazioni specifiche del grafico dei dispositivi

* Gli ID legacy di Analytics non sono supportati. Solo i visitatori con ID Experience Cloud sono uniti.
* Se l’organizzazione utilizza un grafico privato, i nuovi dispositivi richiedono fino a 24 ore per essere uniti.
* I grafici dei dispositivi di terze parti non sono supportati.

## Passaggi successivi

Una volta soddisfatti tutti i requisiti e compresi i limiti, puoi iniziare [Configurazione di Analytics tra dispositivi](setup.md).
