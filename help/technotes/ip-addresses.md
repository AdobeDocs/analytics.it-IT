---
title: IP e domini utilizzati da Adobe Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP provenienti da Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 3483e209a6ae8c2b37d45903b270a2adb3b297ca
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# IP e domini utilizzati da Adobe Analytics

Alcune configurazioni del firewall bloccano gli indirizzi IP provenienti dai server di raccolta dati di Adobe o dai server responsabili dell’accesso ai dati. Puoi utilizzare questo elenco di intervalli per modificare le impostazioni del firewall dell’organizzazione per consentire l’accesso e l’invio di dati dall’interno dell’organizzazione. Questa pagina include sia i sistemi in entrata (come la raccolta dati) che i sistemi in uscita (come i feed di dati) utilizzati da Adobe.

>[!IMPORTANT]
>
>Adobe fa del suo meglio per mantenere aggiornato questo documento, ma non può garantire che l’elenco degli intervalli IP rimanga lo stesso. Tra i possibili cambiamenti vi sono la crescita e l&#39;espansione dell&#39;attività, un registro Internet richiede modifiche allo spazio di indirizzi IP di Adobe o un provider di servizi Internet smette di funzionare.

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

## Tutti i blocchi di indirizzi IP di Adobe Analytics

La tabella seguente descrive tutti gli indirizzi IP di proprietà dell’Adobe utilizzati per Adobe Analytics. Non includono tutti i servizi ospitati su cloud pubblici.

| Blocco IP (notazione CIDR) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |
| `185.34.188.0/22` |
| `192.243.240.0/22` |

## Raccolta dei dati e blocchi degli indirizzi IP FTP

Se la tua organizzazione preferisce consentire intervalli di indirizzi IP specifici, puoi utilizzare la tabella seguente. Tutti gli intervalli in questa sezione sono inclusi nella tabella precedente. Le connessioni FTP per Data Warehouse e Data Feeds provengono solo dalle sedi di Londra, Oregon e Singapore.

| Posizione | Intervallo IP (notazione CIDR) |
| --- | --- |
| Australia | `63.140.55.0/24` |
| Australia | `63.140.56.0/23` |
| California | `63.140.32.0/23` |
| California | `63.140.34.0/24` |
| Francia | `63.140.62.0/23` |
| India | `66.117.20.0/24` |
| India | `66.117.22.0/23` |
| Giappone | `130.248.169.0/23` |
| Giappone | `63.140.50.0/23` |
| Giappone | `66.117.31.0/24` |
| Londra | `66.235.156.0/24` |
| Londra | `185.34.188.0/22` |
| Londra | `130.248.152.0/22` |
| Londra | `130.248.244.0/23` |
| Oregon | `66.235.132.0/22` |
| Oregon | `130.248.130.0/23` |
| Oregon | `130.248.150.0/24` |
| Oregon | `130.248.160.0/21` |
| Oregon | `192.243.242.0/24` |
| Singapore | `130.248.170.0/23` |
| Singapore | `130.248.240.0/24` |
| Singapore | `63.140.44.0/22` |
| Singapore | `63.140.48.0/23` |
| Singapore | `66.117.30.0/24` |
| Virginia | `63.140.38.0/23` |
| Virginia | `63.140.54.0/24` |

## Host di AWS

Adobe Analytics utilizza Amazon Web Services come parte del processo di raccolta dei dati. La tabella seguente include gli indirizzi host AWS IPv4 riservati ad Adobe. Questi host sono **non** incluso nell’intervallo di blocchi aggregati indicato sopra.

| Posizione | Host |
| --- | --- |
| Cina | `52.80.168.159` |
| Cina | `52.80.199.104` |
| Cina | `54.223.199.8` |

La tabella seguente include i blocchi di indirizzi IPv6 di AWS utilizzati da Adobe. Questi host sono **non** incluso nell’intervallo di blocchi aggregati indicato sopra.

| Posizione | Host |
| --- | --- |
| Australia | `2406:da1c:406:1a00::/56` |
| Australia | `2406:da1c:ce5:b400::/56` |
| California | `2600:1f1c:366:d900::/56` |
| Francia | `2a05:d012:706:d000::/56` |
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
