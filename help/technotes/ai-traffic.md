---
description: Comprendere come creare rapporti sul traffico proveniente dai chatbot di intelligenza artificiale
title: Analizzare il traffico dai chatbot di intelligenza artificiale
feature: Metrics, Data Configuration and Collection
source-git-commit: d16214865a037efe41b9f95682758daa577a12ed
workflow-type: tm+mt
source-wordcount: '638'
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

