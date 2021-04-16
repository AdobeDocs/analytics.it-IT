---
description: Data Warehouse offre un'interfaccia flessibile per l'esecuzione di report personalizzati. Seguire queste linee guida può contribuire a ridurre il tempo necessario al recupero dei dati.
keywords: best practice;errore;timeout;risoluzione dei problemi
title: Data Warehouse Best Practices (Procedure consigliate per l’archivio dati)
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 4%

---

# Data Warehouse Best Practices (Procedure consigliate per l’archivio dati)

Data Warehouse offre un’interfaccia flessibile per l’esecuzione di rapporti personalizzati. Seguire queste linee guida può contribuire a ridurre il tempo necessario al recupero dei dati.



| Indirizzo | Descrizione |
|--- |--- |
| Eseguire visualizzazioni di pagina, visite, visitatori e altri rapporti standard in Reports &amp; Analytics | Prima di creare un rapporto di Data Warehouse, controlla se le informazioni che stai cercando sono già disponibili nei rapporti. In tal caso, il rapporto verrà consegnato molto più rapidamente a causa della pre-elaborazione eseguita da Reports &amp; Analytics per le metriche comuni. |
| Comprendere la quantità di dati da richiedere | Un rapporto pluriennale su una suite di rapporti di grandi dimensioni può contenere decine di miliardi di righe di dati. L’elaborazione e la valutazione di questi dati possono richiedere giorni, o addirittura settimane. Valutare in che modo il rapporto viene utilizzato per determinare se sono disponibili alcuni dei dati pluriennali o se è possibile suddividere il rapporto in più richieste. |
| Associa il periodo del rapporto alla granularità | La granularità del reporting richiede un tempo di elaborazione aggiuntivo. Se si realizza una granularità mensile per un anno intero, i rapporti vengono elaborati molto più rapidamente se si invia una richiesta di rapporto per ogni mese. |
| Rapporto sugli intervalli di dati completati | I rapporti sulle Date Warehouse vengono generati al completamento dell’intervallo di date richiesto. Ad esempio, se richiedi un rapporto per la settimana corrente mercoledì, il rapporto non viene generato fino a domenica della settimana successiva. |
| Generare report sui percorsi nella Data Warehouse | Le metriche dei percorsi (voci, uscite, mancate consegne, ecc.) non sono disponibili nel data warehouse. |
| Suite di rapporti virtuali | La funzione di reporting Data Warehouse nelle suite di rapporti virtuali supporta il fuso orario alternativo configurato nella suite di rapporti virtuali. |
