---
title: IP e domini utilizzati da Adobe Analytics
description: Se il firewall dell’organizzazione blocca gli indirizzi IP derivanti dall’Adobe, utilizza questo elenco per aggiornare le impostazioni del firewall.
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 4460850971fe822ff8a0ebf3e3269d0e573fa1db
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 3%

---

# IP e domini utilizzati da Adobe Analytics

Alcune configurazioni del firewall bloccano gli indirizzi IP provenienti dai server o dai server di raccolta dati di Adobe responsabili dell’accesso ai dati. Puoi utilizzare questo elenco di intervalli per modificare le impostazioni del firewall della tua organizzazione per consentire l’accesso e l’invio di dati dall’interno della tua organizzazione.

>[!IMPORTANT]
>
>Sebbene Adobe faccia del suo meglio per mantenere aggiornato il documento, non può garantire che l’elenco degli intervalli IP rimanga lo stesso. Eventuali modifiche includono la crescita e l&#39;espansione dell&#39;attività, un registro Internet richiede modifiche allo spazio degli indirizzi IP di Adobe, o un provider di servizi Internet smette di funzionare.

## Consenti domini di tecnologia dipendenti

Adobe Analytics utilizza i seguenti host per migliorare le prestazioni e l’esperienza di prodotto. Adobe consiglia di aggiungere questi domini all’elenco Consentiti del firewall, per un’esperienza ottimale tramite Adobe Analytics.

| Tecnologia | Dominio |
| --- | --- |
| Domini Adobe Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Dominio legacy di Adobe Analytics | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Guadagno | `esp.aptrinsic.com` |
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
| `172.82.192.0/18` |
| `185.34.188.0/22` |
| `192.243.224.0/19` |
| `205.219.231.0/24` |
| `208.67.40.0/22` |
| `208.77.136.0/22` |

## Blocchi di indirizzi IP per la raccolta dati e l’FTP

Se la tua organizzazione preferisce consentire intervalli di indirizzi IP specifici, puoi utilizzare la tabella seguente. Tutti gli intervalli in questa sezione sono inclusi nella tabella precedente.

| Posizione | Intervallo IP (notazione CIDR) |
| --- | --- |
| Amsterdam | `66.117.28.0/23` |
| Dallas | `205.219.231.0/24` |
| Dallas | `66.235.152.0/22` |
| Dallas | `66.235.140.0/22` |
| Dallas | `63.140.32.0/21` |
| Dallas | `172.82.208.0/22` |
| Hong Kong RAS della Cina | `66.117.24.0/22` |
| Londra | `66.235.156.0/24` |
| Londra | `66.235.148.0/23` |
| Londra | `63.140.40.0/22` |
| Londra | `208.67.41.0/24` |
| Londra | `192.243.254.0/23` |
| Londra | `192.243.244.0/22` |
| Londra | `185.34.188.0/23` |
| Londra | `130.248.152.0/21` |
| Londra | `172.82.224.0/21` |
| Londra | `172.82.232.0/21` |
| Oregon | `192.243.240.0/22` |
| Oregon | `192.243.232.0/21` |
| Oregon | `192.243.224.0/21` |
| Oregon | `130.248.160.0/21` |
| Oregon | `130.248.148.0/22` |
| Oregon | `172.82.192.0/21` |
| Oregon | `172.82.216.0/21` |
| Parigi | `208.67.40.0/24` |
| Singapore | `66.235.150.0/24` |
| Singapore | `66.235.130.0/23` |
| Singapore | `63.140.44.0/22` |
| Singapore | `208.67.43.0/24` |
| Singapore | `172.82.240.0/22` |
| Singapore | `172.82.246.0/23` |
| Singapore | `172.82.248.0/21` |
| San Jose | `66.117.20.0/24` |
| San Jose | `66.235.132.0/22` |
| San Jose | `130.248.128.0/22` |
| San Jose | `192.243.248.0/23` |
| San Jose | `172.82.200.0/22` |
| San Jose | `66.235.136.0/22` |
| San Jose | `208.91.175.0/24` |
| San Jose | `208.91.174.0/24` |
| San Jose | `208.91.169.0/24` |
| Sydney | `216.104.216.0/23` |
| Tokyo | `66.235.159.0/24` |
| Tokyo | `66.117.21.0/24` |
| Tokyo | `63.140.52.0/24` |
| Tokyo | `63.140.50.0/23` |
| Virginia | `66.235.144.0/22` |
| Virginia | `208.77.138.0/23` |
| Virginia | `208.77.136.0/23` |
| Virginia | `192.243.250.0/23` |
| Virginia | `130.248.144.0/22` |
| Virginia | `172.82.204.0/22` |
| Virginia | `172.82.212.0/22` |
| Virginia | Consulta Host AWS |

## Host AWS

Adobe Analytics utilizza Amazon Web Services come parte del processo di raccolta dei dati. La tabella seguente include gli host AWS riservati ad Adobe. Questi host sono **non** inclusi nell&#39;intervallo di blocchi aggregati riportato sopra.

| Posizione | Host |
| --- | --- |
| Australia | `13.54.219.183` |
| Australia | `52.62.137.88` |
| Australia | `54.79.162.112` |
| Cina | `52.81.111.133` |
| Cina | `140.179.22.22` |
| Francia | `13.36.218.177` |
| Francia | `15.188.95.229` |
| Francia | `15.236.176.210` |
| India | `65.0.114.116` |
| India | `65.0.115.179` |
| India | `65.0.25.111` |
| India | `13.233.180.137` |
| India | `65.0.111.130` |
| India | `52.66.172.181` |
| Irlanda | `18.202.158.78` |
| Irlanda | `54.72.205.114` |
| Irlanda | `54.78.36.71` |
| Irlanda | `54.220.133.225` |
| Irlanda | `54.74.170.177` |
| Irlanda | `54.195.254.128` |
| Oregon | `44.233.255.254` |
| Oregon | `44.237.54.118` |
| Oregon | `44.238.157.95` |
| Oregon | `54.212.155.93` |
| Oregon | `52.10.149.115` |
| Oregon | `52.40.172.46` |
| Singapore | `52.220.116.94` |
| Singapore | `52.76.68.91` |
| Singapore | `54.179.114.68` |
| Singapore | `54.255.88.178` |
| Singapore | `52.220.235.10` |
| Singapore | `3.1.237.132` |
| Tokyo | `18.182.161.178` |
| Tokyo | `54.168.58.167` |
| Tokyo | `54.178.61.109` |
| Tokyo | `3.113.78.189` |
| Tokyo | `13.115.137.161` |
| Tokyo | `54.178.162.114` |
| Virginia | `3.213.168.181` |
| Virginia | `3.219.249.186` |
| Virginia | `3.220.129.153` |
| Virginia | `18.206.109.10` |
| Virginia | `18.211.197.67` |
| Virginia | `34.227.41.189` |
| Virginia | `34.228.124.176` |
| Virginia | `54.90.190.103` |
| Virginia | `54.174.149.161` |
