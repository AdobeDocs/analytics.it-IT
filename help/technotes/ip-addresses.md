---
title: Indirizzi IP utilizzati da Adobe Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP provenienti da Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 5ac6da2eb53d2748e8838ef2c6334a771abc26c9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---

# Indirizzi IP utilizzati da Adobe Analytics

Alcune configurazioni del firewall bloccano gli indirizzi IP provenienti dai server di raccolta dati o dai server responsabili dell’accesso ai dati di Adobe. Puoi utilizzare questo elenco di intervalli per modificare le impostazioni del firewall dell’organizzazione per consentire l’accesso e l’invio di dati dall’interno dell’organizzazione.

Tutti gli indirizzi IP utilizzati da Adobe Analytics fanno parte di [indirizzi IP utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/ip-addresses), ad eccezione del pacchetto aggiuntivo di ottimizzazione delle prestazioni per la Cina.

## Indirizzi IP per l’ottimizzazione delle prestazioni della Cina

Il pacchetto del componente aggiuntivo China Performance Optimization è un servizio aggiuntivo a pagamento che migliora le prestazioni di raccolta dati di AppMeasurement per i visitatori in Cina. Per ulteriori informazioni sull’utilizzo di questa funzione, contatta il team del tuo account di Adobe.

>[!IMPORTANT]
>
>RDC Cina non disponibile per la raccolta dati di Web SDK. Questi server sono applicabili solo alle librerie AppMeasurement.

I server di raccolta dati regionali in Cina utilizzano i seguenti indirizzi IP:

| Posizione | Host |
| --- | --- |
| Cina | `52.80.168.159` |
| Cina | `52.80.199.104` |
| Cina | `54.223.199.8` |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>
>[Indirizzi IP utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/it/docs/core-services/interface/data-collection/ip-addresses)
>
>[Domini utilizzati da Adobe Analytics](domains.md)
