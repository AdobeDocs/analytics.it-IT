---
title: Device Graph
description: Comprendi i prerequisiti e le limitazioni dell’unione dei dati utilizzando il grafico del dispositivo.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 7%

---

# Device Graph

Analisi multidispositivo può utilizzare Private Graph per unire i dati. Private Graph è un archivio di ID dispositivo con hash specifici per la tua organizzazione. CDA comunica regolarmente con il grafico del dispositivo per collegare i dispositivi.

## Prerequisiti specifici per il grafico del dispositivo

Se intendi implementare Cross-Device Analytics utilizzando il metodo grafico dei dispositivi, sono necessari i seguenti elementi. Collabora con i team all’interno della tua organizzazione e con il tuo Adobe Account Manager per assicurarti di soddisfare tutte le seguenti esigenze.

>[!WARNING]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di abilitare Cross-Device Analytics o risultati errati durante l’unione dei dati.

* Tutti i prerequisiti elencati nel [pagina panoramica](overview.md).
* La tua organizzazione deve utilizzare [Grafico privato del servizio Adobe Experience Platform Identity](https://business.adobe.com/products/experience-platform/identity-service.html). Vedi anche [Home page](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it) nella guida utente del servizio Identity.
* L’implementazione deve utilizzare la versione più recente del servizio Experience Cloud ID (ECID). Consulta la sezione [Home page](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) nella guida utente del servizio ID. La maggior parte delle implementazioni che utilizzano [Tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it) probabilmente in Adobe Experience Platform è già stato implementato il servizio ID.
* L’implementazione deve chiamare il `setCustomerIDs` (o equivalente SDK) ogni volta che è possibile identificare un individuo, ad esempio quando un utente accede o apre un’e-mail. Questo requisito si applica a tutte le piattaforme, incluse le app mobili se utilizzate. Vedi [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) nella guida utente del servizio ID.

## Limitazioni specifiche del grafico del dispositivo

* Gli ID Analytics legacy non sono supportati. Solo i visitatori con ID Experience Cloud sono uniti.
* Se l’organizzazione utilizza un Private Graph, i nuovi dispositivi richiedono fino a 24 ore per essere uniti.
* Grafici dei dispositivi di terze parti non supportati.

## Passaggi successivi

Una volta che la tua organizzazione soddisfa tutti i requisiti e comprende i limiti, puoi iniziare [Configurazione di Analytics tra dispositivi](setup.md).
