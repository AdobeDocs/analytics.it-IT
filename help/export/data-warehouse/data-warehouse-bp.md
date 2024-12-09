---
description: Scopri le linee guida per ridurre il tempo necessario per recuperare i dati da Data Warehouse.
keywords: best practice;errore;timeout;risoluzione dei problemi
title: Data Warehouse best practice
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 3%

---

# Data Warehouse Best Practices (Procedure consigliate per l’archivio dati)

Data Warehouse offre un’interfaccia flessibile per l’esecuzione di rapporti personalizzati. Utilizza le seguenti linee guida per ridurre il tempo necessario per recuperare i dati:

| Linea guida | Descrizione |
|--- |--- |
| Comprendere la quantità di dati richiesti | Un rapporto pluriennale su una suite di rapporti di grandi dimensioni può contenere decine di miliardi di righe di dati. L’elaborazione e la valutazione di questi dati può richiedere giorni o anche settimane. Valuta come viene utilizzato il rapporto per determinare se alcuni dei dati pluriennali sono disponibili o se è possibile suddividere il rapporto in più richieste. |
| Abbina il periodo del rapporto alla granularità | La granularità del reporting richiede un tempo di elaborazione aggiuntivo. Se generi rapporti con granularità mensile per un intero anno, l’elaborazione dei rapporti sarà molto più rapida se invii una richiesta di rapporto per ogni mese. |
| Rapporto sugli intervalli di dati completati | I rapporti Data Warehouse vengono generati quando l’intervallo di date richiesto è completo. Ad esempio, se richiedi un rapporto per la settimana corrente il mercoledì, il rapporto non viene generato fino alla domenica della settimana successiva. |
| Generare rapporti sui percorsi in Data Warehouse | Le metriche dei percorsi (entrate, uscite, mancati recapiti, ecc.) non sono disponibili in data warehouse. |
| Suite di rapporti virtuali | Il reporting Data Warehouse sulle suite di rapporti virtuali supporta il fuso orario alternativo configurato nella suite di rapporti virtuale. |

