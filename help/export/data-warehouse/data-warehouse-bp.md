---
description: Data warehouse offre un'interfaccia flessibile per l'esecuzione di report personalizzati. Seguendo queste linee guida è possibile ridurre il tempo necessario per recuperare i dati.
keywords: best practices;failure;timeout;troubleshooting
solution: Analytics
title: Data Warehouse Best Practices (Procedure consigliate per l’archivio dati)
topic: Data warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Data Warehouse Best Practices (Procedure consigliate per l’archivio dati)

Data Warehouse offre un'interfaccia flessibile per l'esecuzione di report personalizzati. Seguendo queste linee guida è possibile ridurre il tempo necessario per recuperare i dati.



| Indirizzo | Descrizione |
|--- |--- |
| Eseguire visualizzazioni di pagina, visite, visitatori e altri rapporti standard in Reporting e analisi | Prima di creare un rapporto Data Warehouse, verificare se le informazioni che si desidera trovare sono già disponibili nei rapporti. In tal caso, il report verrà distribuito molto più rapidamente a causa della pre-elaborazione eseguita da Reporting e analisi per metriche comuni. |
| Comprendere la quantità di dati da richiedere | Un rapporto pluriennale su una suite di rapporti di grandi dimensioni può contenere decine di miliardi di righe di dati. L'elaborazione e la valutazione di questi dati possono richiedere giorni o anche settimane. Valutare in che modo viene utilizzato il rapporto per determinare se alcuni dei dati pluriennali sono disponibili o se è possibile suddividere il rapporto in più richieste. |
| Corrispondenza del periodo del rapporto con la granularità | La granularità del reporting richiede un tempo di elaborazione aggiuntivo. Se riferisci la granularità mensile per un intero anno, l'elaborazione dei rapporti risulta molto più rapida se invii una richiesta di rapporto per ogni mese. |
| Report sugli intervalli di dati completati | I report Data Warehouse vengono generati al termine dell'intervallo di date richiesto. Ad esempio, se richiedi un rapporto per la settimana corrente il mercoledì, il rapporto non viene generato fino a domenica della settimana successiva. |
| Generazione di rapporti di percorso in Data Warehouse | Le metriche di percorsi (voci, uscite, rimbalzi, ecc.) non sono disponibili in data warehouse. |
| Suite di rapporti virtuali | Il reporting di Data Warehouse sulle suite di rapporti virtuali supporta il fuso orario alternativo configurato nella suite di rapporti virtuali. |
