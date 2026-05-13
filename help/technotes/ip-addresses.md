---
title: Indirizzi IP utilizzati da Adobe Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP provenienti da Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
TQID: https://experienceleague.adobe.com/-4XZdprTBXpIaFnHeXBQsAr5YoZMW4ocnZRY50bHGUs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 208
ht-degree: 0%

---

# Indirizzi IP utilizzati da Adobe Analytics

Alcune configurazioni del firewall bloccano gli indirizzi IP provenienti dai server di raccolta dati o dai server responsabili dell’accesso ai dati di Adobe. Puoi utilizzare questo elenco di intervalli per modificare le impostazioni del firewall dell’organizzazione per consentire l’accesso e l’invio di dati dall’interno dell’organizzazione.

Tutti gli indirizzi IP utilizzati da Adobe Analytics fanno parte di [indirizzi IP utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses), ad eccezione del pacchetto aggiuntivo di ottimizzazione delle prestazioni per la Cina.

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
>[Indirizzi IP utilizzati da Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)
>
>[Domini utilizzati da Adobe Analytics](domains.md)
