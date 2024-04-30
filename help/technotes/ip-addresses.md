---
title: IP e domini utilizzati da Adobe Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP provenienti da Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: ea859717c6a40b4eeeb9eca54b95718859af9c7b
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 1%

---

# IP e domini utilizzati da Adobe Analytics

Alcune configurazioni del firewall bloccano i domini su cui Adobe Analytics si basa per l’interfaccia di prodotto. È possibile utilizzare questo elenco di domini per modificare le impostazioni di rete dell&#39;organizzazione per consentire l&#39;accesso ai prodotti dall&#39;interno dell&#39;organizzazione.

## Consenti domini tecnologici dipendenti

Adobe Analytics utilizza i seguenti host per migliorare le prestazioni e l’esperienza di utilizzo del prodotto. Adobe consiglia di consentire a questi domini di utilizzare il firewall dell’organizzazione per un’esperienza ottimale con Adobe Analytics.

| Tecnologia | Dominio |
| --- | --- |
| Domini Adobe Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Dominio legacy di Adobe Analytics | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDark | `app.launchdarkly.com` |
| Archiviazione BLOB di Microsoft Azure | `awaascicdprodva7.blob.core.windows.net` |
| CDN di Microsoft Azure | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Blocchi di indirizzi IP di Adobe Experience Cloud

Oltre ai domini di cui sopra, Adobe Analytics si basa su diversi blocchi di indirizzi IP per la raccolta dei dati e l’esportazione dei rapporti.

Per l’elenco completo degli intervalli IP, consulta Indirizzi IP di Adobe Experience Cloud.

## Indirizzi IP per l’ottimizzazione delle prestazioni della Cina

Il pacchetto del componente aggiuntivo China Performance Optimization è un servizio aggiuntivo a pagamento che migliora le prestazioni di raccolta dati di AppMeasurement per i visitatori in Cina. Per ulteriori informazioni sull’utilizzo di questa funzione, contatta il team del tuo account di Adobe.

>[!IMPORTANT]
>
>RDC Cina non disponibile per la raccolta dati dell’SDK web. Questi server sono applicabili solo alle librerie AppMeasurement.

I server di raccolta dati regionali in Cina utilizzano i seguenti indirizzi IP:

| Posizione | Host |
| --- | --- |
| Cina | `52.80.168.159` |
| Cina | `52.80.199.104` |
| Cina | `54.223.199.8` |

{style="table-layout:auto"}
