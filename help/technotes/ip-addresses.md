---
title: IP e domini utilizzati da Adobe Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP derivanti dall’Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 30b4ab97798019c391e5427c97f82b1ea4a379d4
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 3%

---

# IP e domini utilizzati da Adobe Analytics

Alcune configurazioni del firewall bloccano gli indirizzi IP provenienti dai server o dai server di raccolta dati di Adobe responsabili dell’accesso ai dati. Puoi utilizzare questo elenco di intervalli per modificare le impostazioni del firewall della tua organizzazione per consentire l’accesso e l’invio di dati dall’interno della tua organizzazione. Questa pagina include sia i sistemi in entrata (come la raccolta dati) che i sistemi in uscita (come i feed dati) utilizzati da Adobe.

>[!IMPORTANT]
>
>Sebbene Adobe faccia del suo meglio per mantenere aggiornato il documento, non può garantire che l’elenco degli intervalli IP rimanga lo stesso. Eventuali modifiche includono la crescita e l&#39;espansione dell&#39;attività, un registro Internet richiede modifiche allo spazio degli indirizzi IP di Adobe, o un provider di servizi Internet smette di funzionare.

## Consenti domini di tecnologia dipendenti

Adobe Analytics utilizza i seguenti host per migliorare le prestazioni e l’esperienza di prodotto. Adobe consiglia di consentire a questi domini tramite il firewall dell’organizzazione per un’esperienza ottimale tramite Adobe Analytics.

| Tecnologia | Dominio |
| --- | --- |
| Domini Adobe Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Dominio legacy di Adobe Analytics | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Guadagno | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Archiviazione BLOB di Microsoft Azure | `awaascicdprodva7.blob.core.windows.net` |
| CDN Microsoft Azure | `aauicdnva7.azureedge.net` |

## Tutti i blocchi di indirizzi IP per la raccolta dati di Adobe Analytics

La tabella seguente illustra tutti i server di raccolta dati standard e i server di raccolta dati regionali per Adobe Analytics. Non includono singoli host AWS.

| Blocco IP (notazione CIDR) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |

## Blocchi di indirizzi IP per la raccolta dati e l’FTP

Se la tua organizzazione preferisce consentire intervalli di indirizzi IP specifici, puoi utilizzare la tabella seguente. Tutti gli intervalli in questa sezione sono inclusi nella tabella precedente. Le connessioni FTP per Data Warehouse e Data Feeds provengono solo dalle posizioni Londra, Oregon e Singapore.

| Posizione | Intervallo IP (notazione CIDR) |
| --- | --- |
| Australia | `63.140.55.0/24` |
| Australia | `63.140.56.0/23` |
| California | `63.140.32.0/23` |
| California | `63.140.34.0/24` |
| India | `66.117.20.0/24` |
| India | `66.117.22.0/23` |
| Giappone | `130.248.130.0/23` |
| Giappone | `130.248.169.0/23` |
| Giappone | `63.140.50.0/23` |
| Giappone | `66.117.31.0/24` |
| Londra | `66.235.156.0/24` |
| Londra | `185.34.188.0/22` |
| Oregon | `66.235.132.0/22` |
| Singapore | `130.248.170.0/23` |
| Singapore | `130.248.240.0/24` |
| Singapore | `63.140.44.0/22` |
| Singapore | `63.140.48.0/23` |
| Singapore | `66.117.30.0/24` |
| Virginia | `63.140.38.0/23` |
| Virginia | `63.140.54.0/24` |

## Host AWS

Adobe Analytics utilizza Amazon Web Services come parte del processo di raccolta dei dati. La tabella seguente include gli indirizzi host AWS IPv4 riservati per Adobe. Questi host sono **not** incluso nell’intervallo di blocchi aggregati di cui sopra.

| Posizione | Host |
| --- | --- |
| Cina | `52.80.83.220` |
| Cina | `71.132.16.253` |
| Francia | `13.36.218.177` |
| Francia | `15.188.95.229` |
| Francia | `15.236.176.210` |
| Irlanda | `54.74.170.177` |
| Irlanda | `54.195.254.128` |
| Irlanda | `54.220.133.225` |
| Oregon | `52.10.149.115` |
| Oregon | `52.40.172.46` |
| Oregon | `54.212.155.93` |
| Virginia | `3.216.131.23` |
| Virginia | `34.204.237.47` |
| Virginia | `54.163.234.74` |

La tabella seguente include i blocchi indirizzo IPv6 di AWS utilizzati da Adobe. Questi host sono **not** incluso nell’intervallo di blocchi aggregati di cui sopra.

| Posizione | Host |
| --- | --- |
| Australia | `2406:da1c:406:1a00::/56` |
| Australia | `2406:da1c:ce5:b400::/56` |
| California | `2600:1f1c:366:d900::/56` |
| India | `2406:da1a:f34:6a00::/56` |
| Irlanda | `2a05:d018:309:600::/56` |
| Giappone | `2406:da14:b07:ab00::/56` |
| Oregon | `2600:1f14:1eb:7d00::/56` |
| Oregon | `2600:1f14:9d3:2b00::/56` |
| Singapore | `2406:da18:6e8:1e00::/56` |
| Virginia | `2600:1f18:1a20:e800::/56` |
| Virginia | `2600:1f18:4fd:6000::/56` |
| Virginia | `2600:1f18:b00:e100::/56` |
| Virginia | `2600:1f18:d1f:bd00::/56` |
