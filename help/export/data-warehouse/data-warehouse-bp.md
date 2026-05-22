---
description: Scopri le linee guida per ridurre il tempo necessario per recuperare i dati da Data Warehouse.
keywords: best practice;errore;timeout;risoluzione dei problemi
title: Best practice per Data Warehouse
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
TQID: 'https://experienceleague.adobe.com/fWshdRnbrh11kLLT3DiW0a-qMJ13o8v4EMH-t-ceWC8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 3%

---

# Data Warehouse Best Practices (Procedure consigliate per l’archivio dati)

Data Warehouse offre un’interfaccia flessibile per l’esecuzione di rapporti personalizzati. Utilizza le seguenti linee guida per ridurre il tempo necessario per recuperare i dati:

| Linea guida | Descrizione |
|--- |--- |
| Comprendere la quantità di dati richiesti | Un rapporto pluriennale su una suite di rapporti di grandi dimensioni può contenere decine di miliardi di righe di dati. L’elaborazione e la valutazione di questi dati può richiedere giorni o anche settimane. Valuta come viene utilizzato il rapporto per determinare se alcuni dei dati pluriennali sono disponibili o se è possibile suddividere il rapporto in più richieste. |
| Abbina il periodo del rapporto alla granularità | La granularità del reporting richiede un tempo di elaborazione aggiuntivo. Se generi rapporti con granularità mensile per un intero anno, l’elaborazione dei rapporti sarà molto più rapida se invii una richiesta di rapporto per ogni mese. |
| Rapporto sugli intervalli di dati completati | I rapporti di Data Warehouse vengono generati quando l’intervallo di date richiesto è completo. Ad esempio, se richiedi un rapporto per la settimana corrente il mercoledì, il rapporto non viene generato fino alla domenica della settimana successiva. |
| Generare rapporti sui percorsi in Data Warehouse | Metriche dei percorsi (entrate, uscite, mancati recapiti, ecc.) non sono disponibili in data warehouse. |
| Suite di rapporti virtuali | Il reporting di Data Warehouse sulle suite di rapporti virtuali supporta il fuso orario alternativo configurato nella suite di rapporti virtuale. |

