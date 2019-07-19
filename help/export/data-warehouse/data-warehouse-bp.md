---
description: Data warehouse fornisce un'interfaccia flessibile per eseguire rapporti personalizzati. Le seguenti linee guida consentono di ridurre il tempo necessario per recuperare i dati.
keywords: best practice; errore; timeout; risoluzione dei problemi
seo-description: Data warehouse fornisce un'interfaccia flessibile per eseguire rapporti personalizzati. Le seguenti linee guida consentono di ridurre il tempo necessario per recuperare i dati.
seo-title: Best practice di Data Warehouse
solution: Analytics
title: Best practice di Data Warehouse
topic: Data warehouse
uuid: d 71 c 9138-22 d 9-4 f 92-885 e -593 f 83 f 2 bb 59
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Best practice di Data Warehouse

Data Warehouse fornisce un'interfaccia flessibile per eseguire rapporti personalizzati. Le seguenti linee guida consentono di ridurre il tempo necessario per recuperare i dati.



| Linee guida | Descrizione |
|--- |--- |
| Eseguire visualizzazioni di pagina, visite, visitatori e altri rapporti standard in Reporting e analisi | Prima di creare un rapporto Data Warehouse, vedi se le informazioni che stai cercando sono già disponibili nei rapporti. In tal caso, il report verrà distribuito più rapidamente a causa dell'elaborazione preliminare eseguita da Reporting e analisi per le metriche comuni. |
| Comprendere la quantità di dati richiesti | Un rapporto pluriennale su una grande suite di rapporti può contenere decine di miliardi di righe dati. L'elaborazione e la valutazione di questi dati possono richiedere giorni o addirittura settimane. Valuta in che modo il rapporto viene utilizzato per determinare se alcuni dei dati multipli sono disponibili o se il rapporto può essere interrotto in più richieste. |
| Adattare il periodo di rapporto alla granularità | La granularità dei rapporti richiede tempo di elaborazione aggiuntivo. Se state segnalando una granularità mensile per un anno intero, i report vengono elaborati più rapidamente se inviate una richiesta di report ogni mese. |
| Report sugli intervalli di dati completati | I rapporti Data Warehouse vengono generati quando l'intervallo di date richiesto è completo. Ad esempio, se richiedi un rapporto per la settimana corrente mercoledì, il rapporto non viene generato fino alla domenica della settimana seguente. |
| Generare rapporti sui percorsi in Data Warehouse | Le metriche di percorsi (voci, uscite, rimbalzi ecc.) non sono disponibili in data warehouse. |
| Suite di rapporti virtuali | La generazione di rapporti di Data Warehouse sulle suite di rapporti virtuali supporta il fuso orario alternativo configurato nella suite di rapporti virtuale. |