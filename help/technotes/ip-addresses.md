---
title: IP e domini utilizzati da  Adobe Analytics
description: Se il firewall aziendale blocca indirizzi IP che provengono da  Adobe, utilizzate questo elenco per aggiornare le impostazioni del firewall.
translation-type: tm+mt
source-git-commit: 616a6e50e08be831b05f4abdbb3d47f659046d6f
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---


# IP e domini utilizzati da  Adobe Analytics

Alcune configurazioni del firewall bloccano gli indirizzi IP di  Adobe  server o server responsabili dell&#39;accesso ai dati. Puoi utilizzare questo elenco di intervalli per modificare le impostazioni del firewall aziendale per consentire l’accesso e l’invio di dati dall’interno dell’organizzazione.

>[!IMPORTANT]
>
>Sebbene  Adobe faccia del suo meglio per mantenere aggiornato il documento, non può garantire che l&#39;elenco degli intervalli IP resti invariato. Le possibili modifiche includono crescita ed espansione dell&#39;attività, un registro Internet richiede modifiche  spazio indirizzi IP  Adobe, o un provider di servizi Internet interrompe il funzionamento.

## Consenti domini di tecnologia dipendenti

 Adobe Analytics utilizza i seguenti host per migliorare le prestazioni e l&#39;esperienza del prodotto.  Adobe consiglia di aggiungere questi domini al elenco Consentiti  del firewall per un&#39;esperienza ottimale con  Adobe Analytics.

| Tecnologia | Dominio |
| --- | --- |
|  dominio Adobe Analytics | `adobe.com` |
|  dominio legacy Adobe Analytics | `omniture.com` |
|  Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
|  Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Guadagno | `esp.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Archiviazione BLOB di Microsoft Azure | `awaascicdprodva7.blob.core.windows.net` |
| CDN di Microsoft Azure | `aauicdnva7.azureedge.net` |

## Tutti i blocchi indirizzo IP  Adobe Analytics

La tabella seguente illustra tutti i server di raccolta dati standard e i server di raccolta dati regionali per  Adobe Analytics. Non includono singoli host AWS.

| Blocco IP (Notazione CIDR) |
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

## Blocchi indirizzo IP raccolta dati e FTP

Se l&#39;organizzazione preferisce consentire intervalli di indirizzi IP specifici, è possibile utilizzare la tabella seguente. Tutti gli intervalli di questa sezione sono inclusi nella tabella precedente.

| Posizione | Intervallo IP (notazione CIDR) |
| --- | --- |
| Amsterdam | `66.117.28.0/23` |
| Dallas | `205.219.231.0/24` |
| Dallas | `66.235.152.0/22` |
| Dallas | `66.235.140.0/22` |
| Dallas | `63.140.32.0/21` |
| Dallas | `172.82.208.0/22` |
| Hong Kong - RTE della Cina | `66.117.24.0/22` |
| London | `66.235.156.0/24` |
| on | `66.235.148.0/23` |
| London | `63.140.40.0/22` |
| London | `208.67.41.0/24` |
| London | `192.243.254.0/23` |
| London | `192.243.244.0/22` |
| London | `185.34.188.0/23` |
| London | `130.248.152.0/21` |
| London | `172.82.224.0/21` |
| on | `172.82.232.0/21` |
| Oregon | `192.243.240.0/22` |
| Oregon | `192.243.232.0/21` |
| Oregon | `192.243.224.0/21` |
| Oregon | `130.248.160.0/21` |
| Oregon | `130.248.148.0/22` |
| Oregon | `172.82.192.0/21` |
| Oregon | `172.82.216.0/21` |
| Paris | `208.67.40.0/24` |
| Singapore | `66.235.150.0/24` |
| Singapore | `66.235.130.0/23` |
| Singapore | `63.140.44.0/22` |
| Virginia | `208.67.43.0/24` |
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
| Virginia | Vedere Ospitanti AWS |

## Host AWS

 Adobe Analytics utilizza  Amazon Web Services come parte del processo di raccolta dei dati. Nella tabella seguente sono inclusi gli host AWS riservati per  Adobe. Questi host **non** sono inclusi nell&#39;intervallo di blocchi aggregati sopra.

| Posizione | Host |
| --- | --- |
| Australia | `13.238.77.77` |
| Australia | `52.62.21.192` |
| Australia | `54.66.152.159` |
| Francia | `15.188.154.177` |
| Francia | `15.236.175.233` |
| Francia | `15.236.9.100` |
| India | `13.232.177.101` |
| India | `13.235.4.163` |
| India | `3.6.119.69` |
| Irlanda | `52.17.94.37` |
| Irlanda | `52.49.253.16` |
| Irlanda | `52.51.63.15` |
| Oregon | `52.42.60.49` |
| Oregon | `54.212.169.56` |
| Oregon | `54.214.170.191` |
| Virginia | `13.228.34.224` |
| Singapore | `18.136.20.161` |
| Singapore | `52.74.162.152` |
| Tokyo | `13.112.72.86` |
| Tokyo | `18.178.74.225` |
| Tokyo | `18.179.88.228` |
| Virginia | `3.220.129.153` |
| Virginia | `18.211.197.67` |
| Virginia | `34.228.124.176` |
| Virginia | `34.234.106.101` |
| Virginia | `52.22.231.198` |
| Virginia | `54.157.65.136` |
