---
title: IP e domini utilizzati nell'Adobe Experience Cloud
description: Se il firewall aziendale blocca indirizzi IP che provengono da  Adobe, utilizzate questo elenco per aggiornare le impostazioni del firewall.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 1%

---


# IP e domini utilizzati nell&#39;Adobe Experience Cloud

Alcune configurazioni del firewall bloccano gli indirizzi IP di  Adobe  server o server responsabili dell&#39;accesso ai dati. Il seguente elenco di blocchi indirizzo IP include gli indirizzi attualmente noti coinvolti nell&#39;Adobe Experience Cloud. Puoi utilizzare questo elenco di intervalli per modificare le impostazioni del firewall aziendale per consentire l’accesso e l’invio di dati dall’interno dell’organizzazione.

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

## Tutti i blocchi di indirizzi IP  Adobe

La tabella seguente illustra tutti gli indirizzi IP pubblici di Adobe Experience Cloud di proprietà  Adobe. Questi intervalli includono server di raccolta dati standard e server di raccolta dati regionali per  Adobe Analytics. Non includono singoli host AWS.

Molti dei  servizi e delle funzionalità  Adobe condividono blocchi e intervalli IP, tuttavia alcuni hanno un proprio spazio dedicato. I blocchi che utilizzano solo una singola soluzione sono indicati come tali.

| Blocco IP (Notazione CIDR) | Note |
| --- | --- |
| `62.210.161.0/24` | Specifico per  Adobe Campaign |
| `63.140.32.0/19` |  |
| `66.117.16.0/20` |  |
| `66.235.128.0/19` |  |
| `67.226.212.0/23` | Specifico per Adobe Advertising Cloud |
| `103.202.219.0/24` | Specifico per Adobe Advertising Cloud |
| `130.248.0.0/16` |  |
| `172.82.192.0/18` |  |
| `185.34.188.0/22` |  |
| `185.148.48.0/24` | Specifico per Adobe Advertising Cloud |
| `192.243.224.0/19` |  |
| `198.98.22.0/23` | Specifico per Adobe Advertising Cloud |
| `205.219.231.0/24` |  |
| `208.67.40.0/22` |  |
| `208.77.136.0/22` |  |
| `208.91.168.0/21` | Specifico per Adobe Advertising Cloud |

## Blocchi indirizzo IP raccolta dati e FTP

Se l&#39;organizzazione preferisce consentire intervalli di indirizzi IP specifici, è possibile utilizzare la tabella seguente. Tutti gli intervalli di questa sezione sono inclusi nella tabella precedente.

| Posizione | Intervallo IP (notazione CIDR) | Note |
| --- | --- | --- |
| Amsterdam | `66.117.28.0/23` |  |
| Dallas | `205.219.231.0/24` |  |
| Dallas | `66.235.152.0/22` |  |
| Dallas | `66.235.140.0/22` |  |
| Dallas | `63.140.32.0/21` |  |
| Dallas | `172.82.208.0/22` |  |
| Hong Kong - RTE della Cina | `66.117.24.0/22` |  |
| London | `66.235.156.0/24` |  |
| London | `66.235.148.0/23` |  |
| London | `66.117.16.0/23` | Specifico per  Adobe Campaign |
| London | `63.140.40.0/22` |  |
| London | `208.67.41.0/24` |  |
| London | `192.243.254.0/23` |  |
| London | `192.243.244.0/22` |  |
| London | `185.34.188.0/23` |  |
| London | `130.248.152.0/21` |  |
| London | `172.82.224.0/21` |  |
| London | `172.82.232.0/21` |  |
| Oregon | `192.243.240.0/22` |  |
| Oregon | `192.243.232.0/21` |  |
| Oregon | `192.243.224.0/21` |  |
| Oregon | `130.248.160.0/21` |  |
| Oregon | `130.248.148.0/22` |  |
| Oregon | `172.82.192.0/21` |  |
| Oregon | `172.82.216.0/21` |  |
| Paris | `62.210.161.0/24` | Specifico per  Adobe Campaign |
| Paris | `66.117.18.0/23` | Specifico per  Adobe Campaign |
| Paris | `208.67.40.0/24` |  |
| Singapore | `66.235.150.0/24` |  |
| Singapore | `66.235.130.0/23` |  |
| Singapore | `63.140.44.0/22` |  |
| Singapore | `208.67.43.0/24` |  |
| Singapore | `172.82.240.0/22` |  |
| Singapore | `172.82.246.0/23` |  |
| Singapore | `172.82.248.0/21` |  |
| San Jose | `66.117.20.0/24` |  |
| San Jose | `66.235.132.0/22` |  |
| San Jose | `130.248.128.0/22` |  |
| San Jose | `192.243.248.0/23` |  |
| San Jose | `172.82.200.0/22` |  |
| San Jose | `66.235.136.0/22` |  |
| San Jose | `208.91.175.0/24` |  |
| San Jose | `208.91.174.0/24` |  |
| San Jose | `208.91.169.0/24` |  |
| Sydney | `216.104.216.0/23` |  |
| Tokyo | `66.235.159.0/24` |  |
| Tokyo | `66.117.21.0/24` |  |
| Tokyo | `63.140.52.0/24` |  |
| Tokyo | `63.140.50.0/23` |  |
| Virginia | `66.235.144.0/22` |  |
| Virginia | `208.77.138.0/23` |  |
| Virginia | `208.77.136.0/23` |  |
| Virginia | `192.243.250.0/23` |  |
| Virginia | `130.248.144.0/22` |  |
| Virginia | `172.82.204.0/22` |  |
| Virginia | `172.82.212.0/22` |  |
| Virginia | Vedere Ospitanti AWS |  |

## Host AWS

Alcune funzionalità  Adobe utilizzano  Amazon Web Services per la raccolta dei dati. Nella tabella seguente sono inclusi gli host AWS riservati per  Adobe. Questi host **non** sono inclusi nell&#39;intervallo di blocchi aggregati sopra.

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
| London | `172.82.228.19` |
| Oregon | `52.42.60.49` |
| Oregon | `54.212.169.56` |
| Oregon | `54.214.170.191` |
| Singapore | `13.228.34.224` |
| Singapore | `18.136.20.161` |
| Singapore | `52.74.162.152` |
| Tokyo | `13.112.72.86` |
| Tokyo | `18.178.74.225` |
| Tokyo | `18.179.88.228` |
| Virginia | `34.234.106.101` |
| Virginia | `52.22.231.198` |
| Virginia | `54.157.65.136` |
| Virginia | `107.23.142.4` |
| Virginia | `34.192.14.184` |
| Virginia | `34.192.146.173` |
| Virginia | `34.192.229.76` |
| Virginia | `34.196.183.216` |
| Virginia | `34.196.219.120` |
| Virginia | `34.196.54.55` |
| Virginia | `34.197.179.21` |
| Virginia | `34.197.45.49` |
| Virginia | `34.197.93.163` |
| Virginia | `34.198.80.27` |
| Virginia | `34.199.102.192` |
| Virginia | `34.199.46.40` |
| Virginia | `34.199.99.62` |
| Virginia | `34.200.67.35` |
| Virginia | `34.204.146.235` |
| Virginia | `34.204.164.1` |
| Virginia | `34.204.27.249` |
| Virginia | `34.205.224.111` |
| Virginia | `34.206.69.71` |
| Virginia | `52.193.88.44` |
| Virginia | `52.200.108.250` |
| Virginia | `52.200.171.156` |
| Virginia | `52.201.49.195` |
| Virginia | `52.205.244.105` |
| Virginia | `52.207.161.156` |
| Virginia | `52.22.148.55` |
| Virginia | `52.4.155.255` |
| Virginia | `52.72.182.205` |
| Virginia | `52.72.185.111` |
| Virginia | `54.152.218.194` |
| Virginia | `54.173.37.66` |
| Virginia | `54.173.69.38` |
| Virginia | `54.236.180.248` |
| Virginia | `54.236.71.218` |
| Virginia | `54.80.103.29` |
| Virginia | `54.88.180.124` |
