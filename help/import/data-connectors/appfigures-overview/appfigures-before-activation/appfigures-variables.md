---
description: L'integrazione dei connettori dati per appfigures utilizza le variabili Analytics per tenere traccia delle diverse metriche appfigures.
seo-description: L'integrazione dei connettori dati per appfigures utilizza le variabili Analytics per tenere traccia delle diverse metriche appfigures.
seo-title: Variabili integrazione di Analytics
title: Variabili integrazione di Analytics
uuid: 08 d 5 b 714-1 c 97-4 be 6-aae 8-1 f 8192535425
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics Integration Variables{#analytics-integration-variables}

L'integrazione dei connettori dati per appfigures utilizza le variabili Analytics per tenere traccia delle diverse metriche appfigures.

La tabella seguente descrive le variabili di Analytics attivate automaticamente per l'integrazione appfigures.

## Variabili richieste {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>Questa integrazione utilizza le variabili dedicate per i dati dell'app store, quindi non devi assegnare variabili ed eventi di commerce personalizzati.

| Tipo di variabile | Nome | Metodo di compilazione | Descrizione |
|---|---|---|---|
| eVar | ID oggetto App Store | Importato da appfigures. | Configura questa evar con scadenza visita, Allocazione più recente e sottorelazione base. |
| event (numerico) | Download dall'app store | Importato da appfigures. | Numero di download delle applicazioni mobili. |
| event (numerico) | Acquisti app store (nell'app) | Importato da appfigures. | Numero di acquisti in-app e iscrizioni. |
| event (numerico) | Classifica app store | Importato da appfigures. | Utilizzato per definire la metrica calcolata appfigures calcolata. Non utilizzato direttamente. |
| event (numerico) | Divisor classifica app store | Importato da appfigures. | Utilizzato per definire la metrica calcolata appfigures calcolata. Non utilizzato direttamente. |
| event (numerico) | Valutazione app store | Importato da appfigures. | Utilizzato per definire la metrica calcolata appfigures calcolata. Non utilizzato direttamente. |
| event (numerico) | Divisor Valutazione app store | Importato da appfigures. | Utilizzato per definire la metrica calcolata appfigures calcolata. Non utilizzato direttamente. |
| evento (valuta) | Ricavi da app store (nell'app) | Importato da appfigures. | La quantità di entrate in-app meno la tariffa store. |
| evento (valuta) | Ricavi da app store (uno disattivato) | Importato da appfigures. | Entrate totali dagli acquisti dell'app meno la tariffa store. |
| evento (valuta) | Royalty App Store (nell'app) | Importato da appfigures. | Non utilizzato |
| evento (valuta) | Royalty App Store (una disattivato) | Importato da appfigures. | Non utilizzato |

