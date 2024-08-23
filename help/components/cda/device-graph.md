---
title: Device Graph
description: Comprendi i prerequisiti e le limitazioni dell’unione di dati utilizzando il grafico dei dispositivi.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
feature: CDA
role: Admin
source-git-commit: cc0b8703d6b6488adf9a2ea41a51001538d1cbee
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 3%

---


# Device Graph

{{available-existing-customers}}

Analytics tra dispositivi può utilizzare Private Graph per unire i dati. Private Graph è un archivio di ID dispositivo con hash specifico per la tua organizzazione. CDA comunica regolarmente con il grafico dei dispositivi per collegare i dispositivi.

## Prerequisiti specifici per il grafico dei dispositivi

Se intendi implementare Cross-Device Analytics utilizzando il metodo del grafico dei dispositivi, sono necessari i seguenti elementi. Collabora con i team della tua organizzazione e con il tuo account team Adobe per assicurarti di soddisfare tutte le seguenti esigenze.

>[!WARNING]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di abilitare Cross-Device Analytics o risultati errati durante l’unione dei dati.
>

* Tutti i prerequisiti elencati nella [pagina della panoramica](overview.md).
* L&#39;organizzazione deve utilizzare il [grafo privato del servizio Adobe Experience Platform Identity](https://business.adobe.com/products/experience-platform/identity-service.html). Vedi anche la [home page](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it) nella guida utente del servizio Identity.
* L&#39;implementazione deve utilizzare la versione più recente del servizio ID Experience Cloud (ECID). Consulta la [home page](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) nella guida utente del servizio ID. È probabile che il servizio ID sia già stato distribuito per la maggior parte delle implementazioni che utilizzano [Tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it) in Adobe Experience Platform.
* L&#39;implementazione deve chiamare la funzione `setCustomerIDs` (o l&#39;equivalente SDK) ogni volta che un utente può essere identificato, ad esempio quando un utente accede o apre un messaggio e-mail. Questo requisito si applica a tutte le piattaforme, incluse le app mobili se utilizzate. Vedi [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) nella guida utente del servizio ID.

## Limitazioni specifiche del grafico dei dispositivi

* Gli ID legacy di Analytics non sono supportati. Solo i visitatori con ID Experience Cloud sono uniti.
* Se l’organizzazione utilizza un grafico privato, i nuovi dispositivi richiedono fino a 24 ore per essere uniti.
* I grafici dei dispositivi di terze parti non sono supportati.

## Passaggi successivi

Quando l&#39;organizzazione soddisfa tutti i requisiti e comprende i limiti, puoi avviare [Configurazione di Cross-Device Analytics](setup.md).
