---
title: Device Graph
description: Comprendere i prerequisiti e i limiti dell'unione dei dati utilizzando il grafico del dispositivo.
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 5%

---


# Device Graph

Analytics tra dispositivi offre due metodi distinti per unire i dati. Questo metodo utilizza Adobe Experience Platform Identity Service Co-op Graph o Private Graph per unire i dati. CDA comunica regolarmente con il grafico del dispositivo per collegare i dispositivi.

## Differenze tra grafico a cooperativa e grafico privato

 Adobe offre due tipi di grafici dispositivo come parte del servizio ID:

* **Grafico** cooperativo: Un archivio degli ID dispositivo con hash a cui qualsiasi cliente può contribuire e fare riferimento. Poiché questo tipo di grafico del dispositivo è collaborativo, in genere corrisponde a più dispositivi rispetto a un grafico privato.
* **Grafico** privato: Un archivio di ID dispositivo con hash a cui fa riferimento solo la tua organizzazione.

## Prerequisiti specifici per il grafico del dispositivo

Se intendete implementare Analytics cross-Device con il metodo grafico del dispositivo, sono necessari i seguenti elementi. Collaborate con i team all&#39;interno dell&#39;organizzazione e con l&#39;Account Manager del Adobe  per garantire che vengano rispettate tutte le condizioni seguenti.

>[!IMPORTANT]
>
>Se non vengono soddisfatti tutti i prerequisiti, potrebbe non essere possibile abilitare l&#39;analisi multi-dispositivo o non essere possibile ottenere risultati soddisfacenti durante l&#39;unione dei dati.

* Tutti i prerequisiti elencati nella [pagina di panoramica](overview.md).
* L’organizzazione deve utilizzare Adobe Experience Platform Identity Service Co-op Graph o Private Graph. Consulta la [Home Page](https://docs.adobe.com/content/help/it-IT/device-co-op/using/home.html) nella guida utente di Device Co-op.
* L’implementazione deve utilizzare la versione più recente del servizio ID Experience Cloud . Vedere la [Home Page](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) nella guida utente del servizio identità  Experience Cloud. La maggior parte delle implementazioni che utilizzano  Adobe Experience Platform Launch probabilmente hanno già implementato ECID.
* L&#39;implementazione deve chiamare la funzione `setCustomerIDs` (o equivalente SDK) ogni volta che è possibile identificare un individuo, ad esempio quando un utente accede o apre un&#39;e-mail. Questo requisito si applica a tutte le piattaforme, comprese le app mobili se utilizzate. Vedere [`setCustomerIDs`](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) nella guida utente del servizio identità  Experience Cloud.

## Limitazioni specifiche per il grafico del dispositivo

* Gli ID Analytics legacy non sono supportati. Solo i visitatori con  ID Experience Cloud sono cuciti.
* Se l’organizzazione utilizza un grafico privato, i nuovi dispositivi impiegano fino a 24 ore per essere cuciti.
* Se l&#39;organizzazione utilizza Co-op Graph, per l&#39;installazione di nuovi dispositivi in visita nel sito possono essere necessarie fino a due settimane. Il livello di cucitura in CDA per le ultime due settimane è generalmente inferiore a quello degli intervalli di date superiori a due settimane.
* I grafici dei dispositivi 3rd-party non sono supportati.

## Passaggi successivi

Una volta che l&#39;organizzazione soddisfa tutti i requisiti e ha compreso i limiti, puoi avviare la [configurazione di Analytics multi-dispositivo](setup.md).

