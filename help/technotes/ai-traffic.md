---
description: Comprendere come creare rapporti sul traffico proveniente dai chatbot di intelligenza artificiale
title: Analizzare il traffico dai chatbot di intelligenza artificiale
feature: Metrics, Data Configuration and Collection
exl-id: 0b013b7d-02a2-405d-bdd6-c991f0baac8e
TQID: https://experienceleague.adobe.com/lyzSP-7iZ8Y5XiTG1t7Axsg1f5AJf6BbcZbu7MmkwWU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: b7156124-d291-4de4-ac0c-ed17d8078449
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 643
ht-degree: 0%

---

# Analizzare il traffico dagli strumenti di intelligenza artificiale per conversazioni

Adobe Analytics fornisce strumenti per l’analisi del traffico AI sul sito web.

Quando analizzi il traffico AI, devi innanzitutto comprendere i tipi di traffico AI che possono verificarsi e quali tipi generano hit. Quindi puoi analizzare il traffico in Analysis Workspace.

## Comprendere il traffico AI

### Comprendere i tipi di traffico AI

Il traffico di IA sul sito web può verificarsi in una delle seguenti circostanze:

* **Durante la formazione preliminare**: si verifica raramente quando il contenuto del sito Web viene raschiato e acquisito nei dati di formazione di IA.

* **Quando si rispondono alle richieste su richiesta**: si verifica nel momento in cui l&#39;utente richiede l&#39;IA con una domanda e il chatbot di IA risponde. Il chatbot AI esegue una ricerca web e il contenuto del sito web viene incluso nella risposta. Questo tipo di interazioni è a volte indicato come Generazione aumentata di recupero (Retrieval-Augmented Generation, RAG).

  Alcune risposte chatbot basate sull’intelligenza artificiale includono collegamenti al materiale sorgente sul sito, mentre altre no.

* **Durante l&#39;esecuzione di flussi di lavoro agenti**: si verifica ogni volta che un agente di IA visita il sito Web quando si fa clic su una serie di pagine Web in un browser per rispondere a una richiesta dell&#39;utente. In questo caso, l’IA agisce come agente per l’utente che ha effettuato la richiesta.

### Comprendere quando vengono generati hit per il traffico AI

Un hit viene generato su una pagina web quando JavaScript viene eseguito sulla pagina. A seconda del tipo di traffico AI che si verifica sul sito, JavaScript potrebbe essere eseguito o meno.

| Tipo di traffico AI | Genera hit | Considerazioni |
|---------|----------|---------|
| **Formazione preliminare** | Sì | Gli hit vengono generati durante la pre-formazione quando il contenuto del sito web viene acquisito nell’intelligenza artificiale. Tuttavia, la pre-formazione si verifica raramente e il contenuto incluso nella pre-formazione di un’intelligenza artificiale può essere riutilizzato ripetutamente nelle risposte future senza generare ulteriori hit sul sito web. <p>In altre parole, un singolo hit che si verifica durante la pre-formazione di un’intelligenza artificiale può essere riutilizzato più volte per più risposte on-demand senza generare hit aggiuntivi sul sito web.</p><p>Per informazioni su come analizzare questo tipo di traffico AI in Analysis Workspace, consulta [Analizzare il traffico AI utilizzando il rilevamento di bot](#analyze-ai-traffic-using-bot-detection).</p> |
| **Richieste su richiesta** | No | La risposta di IA non genera hit perché utilizza una combinazione di:<ul><li>I dati preaddestrati <br/>Le informazioni sono già incluse nelle conoscenze preaddestrate dell&#39;intelligenza artificiale, pertanto l&#39;intelligenza artificiale non esegue JavaScript sulle pagine.</li><li>Ricerca Web su richiesta <br/>Recupera solo il HTML non elaborato della pagina Web durante la ricerca Web, pertanto l&#39;IA non esegue JavaScript sulle pagine.</li></ul> |
| **Collegamenti materiali Source nelle risposte AI** | Sì | Gli hit vengono generati quando un utente fa clic sul collegamento al materiale sorgente incluso nella risposta di IA. Un hit non viene generato se un collegamento è incluso nella risposta e l’utente non fa clic sul collegamento. <p>Alcune risposte chatbot basate sull’intelligenza artificiale includono collegamenti al materiale sorgente, altre no. </p><p>Per informazioni su come analizzare questo tipo di traffico AI in Analysis Workspace, vedi [Analizzare il traffico AI per tipo di referrer](#analyze-ai-traffic-by-referrer-type).</p> |
| **Flussi di lavoro agenti** | Sì | Gli hit vengono generati su ogni pagina quando l’agente di IA fa clic nel flusso di lavoro per conto dell’utente. <p>Per informazioni su come analizzare questo tipo di traffico AI in Analysis Workspace, vedi [Analizzare il traffico AI per tipo di referrer](#analyze-ai-traffic-by-referrer-type).</p> |

## Analizzare il traffico di IA in Analysis Workspace

### Analizza il traffico AI per tipo di referrer

Puoi utilizzare la dimensione Tipo referrer in Analysis Workspace per analizzare i seguenti tipi di traffico AI:

* Collegamenti ai materiali di Source nelle risposte AI

* Flussi di lavoro agenti

La dimensione Tipo referrer include l&#39;elemento dimensione [Strumenti di IA per la conversazione](/help/components/dimensions/referrer-type.md#conversational-ai-tools). Questo elemento dimensione include un elenco predefinito di chatbot di IA.

Per ulteriori informazioni, vedere [Tipo referrer](/help/components/dimensions/referrer-type.md).

### Analizzare il traffico AI tramite il rilevamento di bot

Puoi utilizzare il rilevamento di bot in Analysis Workspace per analizzare il traffico di intelligenza artificiale proveniente dalla pre-formazione.
