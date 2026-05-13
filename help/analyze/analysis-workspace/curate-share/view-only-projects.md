---
description: Comprendere l’esperienza dei progetti di sola lettura in Analysis Workspace.
keywords: Progetti di sola lettura
title: Progetti di sola lettura
feature: Curate and Share
role: User, Admin
exl-id: 53372247-6902-4c7f-9132-38a1d453186c
TQID: https://experienceleague.adobe.com/8PyU15pb5sDqq-qZE-T8ceuDJdXDUXyxPQvJYJGUfwg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 52%

---

# Progetti di sola lettura

Puoi condividere i progetti in sola lettura con i destinatari tramite la funzionalità [condividi](share-projects.md). I destinatari inseriti nella mansione **[!UICONTROL Read only]** riceveranno un&#39;esperienza di progetto più limitata.

Potresti desiderare di fare ciò se condividi un progetto con utenti che hanno meno familiarità con la struttura dei dati dell’organizzazione, Analysis Workspace o Adobe Analytics in genere, ma desideri comunque che utilizzino dati e approfondimenti in un ambiente sicuro.

![Condividi come sola lettura](assets/read-only-project-sender.png)

Le interazioni per i destinatari di sola lettura sono limitate.

![Condividi come sola lettura ricevuta](assets/read-only-project-receiver.png)

## Interazioni disattivate

Le interazioni disattivate in un progetto di sola visualizzazione includono:

* Pannello sinistro nascosto
* Intervallo date del calendario del pannello. Nota: se desideri concedere il controllo del calendario ai destinatari, aggiungi un [segmento a discesa con intervalli di date](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=it).
* Segmentazione a forma libera
* Numero di righe a forma libera visibili
* Impostazioni di riga, colonna o visualizzazione a forma libera
* Segmenti del pannello
* Menu Edit, Insert e Component
* Suggerimenti per Workspace

## Interazioni abilitate

Alcune delle interazioni abilitate più rilevanti in un progetto di sola visualizzazione includono:

| Area | Interazioni abilitate |
| --- | --- |
| **Tabelle a forma libera** | <li>Impaginazione e ordinamento</li><li>Passaggio del mouse</li><li>Selezioni di celle che aggiornano le visualizzazioni collegate</li><li>Dal menu di scelta rapida > Ottieni collegamento visualizzazione</li><li>Dal menu di scelta rapida > Copia negli Appunti</li> |
| **Visualizzazioni** | <li>Clic per attivare/disattivare la legenda</li><li>Passaggio del mouse</li><li>Dal menu di scelta rapida > Ottieni collegamento visualizzazione</li><li>Comprimi/espandi</li><li>Flow (espandi nodi Flow)</li><li>Map (zoom)</li></ul> |
| **Pannelli** | <li>Segmenti a discesa interattivi</li><li>Dal menu di scelta rapida > Ottieni collegamento pannello</li><li>Comprimi/espandi</li> |
| **Progetto** | <li>Analisi di tutte le icone delle informazioni</li><li>Menu Progetto (Nuovo, Apri, Imposta come pagina di destinazione, Aggiorna, Scarica CSV/PDF, Informazioni e impostazioni progetto limitate)</li><li>Menu Share (Get project link, Send file now)</li><li>Menu Help (tutte le azioni tranne le opzioni Tips e Debugger)</li> |


## Condividi con chiunque

Se hai selezionato un progetto utilizzando [Condividi con qualcuno](share-projects.md#share-a-project-with-anyone-no-login-required), il destinatario del collegamento può solo visualizzare il progetto e non interagire con esso.

![Condividi con chiunque](assets/share-with-anyone-receiver.png)
