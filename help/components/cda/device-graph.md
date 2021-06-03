---
title: Device Graph
description: Comprendi i prerequisiti e le limitazioni dell’unione dei dati utilizzando il grafico del dispositivo.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 1%

---

# Device Graph

Analisi multidispositivo fornisce due metodi distinti per unire i dati. Questo metodo utilizza il grafico Co-op o Private Graph del servizio Adobe Experience Platform Identity per unire i dati. CDA comunica regolarmente con il grafico del dispositivo per collegare i dispositivi.

## Differenze tra grafico co-op e grafico privato

Nell&#39;ambito del servizio ID, Adobe offre due tipi di grafici dei dispositivi:

* **Grafico** cooperativo: Un archivio di ID dispositivo con hash a cui qualsiasi cliente può contribuire e fare riferimento. Dato che questo tipo di grafico dei dispositivi è collaborativo, in genere corrisponde a più dispositivi rispetto a un grafico privato.
* **Grafico** privato: Un archivio di ID dispositivo con hash a cui fa riferimento solo la tua organizzazione.

## Prerequisiti specifici per il grafico del dispositivo

Se intendi implementare Cross-Device Analytics utilizzando il metodo grafico dei dispositivi, sono necessari i seguenti elementi. Collabora con i team all’interno della tua organizzazione e con il tuo Adobe Account Manager per assicurarti di soddisfare tutte le seguenti esigenze.

>[!IMPORTANT]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di abilitare Cross-Device Analytics o risultati errati durante l’unione dei dati.

* Tutti i prerequisiti elencati nella [pagina di panoramica](overview.md).
* L’organizzazione deve utilizzare il grafico Co-op o Private Graph del servizio Adobe Experience Platform Identity. Consulta la sezione [Home page](https://experienceleague.adobe.com/docs/device-co-op/using/home.html) nella guida utente di Device Co-op .
* L’implementazione deve utilizzare la versione più recente del servizio Experience Cloud ID. Consulta la sezione [Home page](https://experienceleague.adobe.com/docs/id-service/using/home.html) nella guida utente del servizio Experience Cloud Identity. Probabilmente la maggior parte delle implementazioni che utilizzano Adobe Experience Platform Launch hanno già implementato ECID.
* L’implementazione deve chiamare la funzione `setCustomerIDs` (o equivalente SDK) ogni volta che è possibile identificare un singolo utente, ad esempio quando un utente accede o apre un’e-mail. Questo requisito si applica a tutte le piattaforme, incluse le app mobili se utilizzate. Consulta [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) nella guida utente del servizio Experience Cloud Identity.

## Limitazioni specifiche del grafico del dispositivo

* Gli ID Analytics legacy non sono supportati. Solo i visitatori con ID Experience Cloud sono uniti.
* Se l’organizzazione utilizza un Private Graph, i nuovi dispositivi richiedono fino a 24 ore per essere uniti.
* Se l’organizzazione utilizza Co-op Graph, per unire nuovi dispositivi che visitano il sito possono essere necessarie fino a due settimane. Il livello di unione in CDA per le ultime due settimane è in genere inferiore a quello degli intervalli di date più vecchi di due settimane.
* Grafici dei dispositivi di terze parti non supportati.

## Passaggi successivi

Una volta che l&#39;organizzazione soddisfa tutti i requisiti e comprende i limiti, puoi iniziare a [Configurazione di Analytics tra dispositivi](setup.md).
