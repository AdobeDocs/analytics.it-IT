---
description: La funzione Rilevamento ricerca a pagamento differenzia le ricerche naturali nei report Motori di ricerca e Parole chiave di ricerca.
title: Rilevamento di ricerca a pagamento
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
TQID: 'https://experienceleague.adobe.com/g26-86nQZ-k3kaID-Dq6qbwYkdqLpHDdUEswP-p361Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 100%

---

# Rilevamento di ricerca a pagamento

[!UICONTROL Paid Search Detection] si distingue dalle ricerche naturali nei rapporti [!UICONTROL Search Engines] e [!UICONTROL Search Keywords]. Puoi specificare i motori di ricerca in cui utilizzi gli annunci a pagamento e specificare una stringa di caratteri trovata nell’URL di una visita da un annuncio a pagamento.

## Opzioni di configurazione {#configuration}

Nella tabella seguente sono descritti i campi e le opzioni utilizzati per [configurare il rilevamento di ricerche a pagamento](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md).

| Opzione | Descrizione |
| --- | --- |
| [!UICONTROL Search Engine] | Seleziona un motore di ricerca dall’elenco a discesa. È possibile specificare il motore se si utilizzano parametri di stringa di query diversi per motori di ricerca diversi. Di solito, il valore `Any` è sufficiente. |
| [!UICONTROL Query string] | Specifica una stringa per una corrispondenza sensibile a maiuscole e minuscole con qualsiasi parte del parametro della stringa query, che è la parte dell&#39;url dopo il “?”. <br>**Nota**: [!UICONTROL Paid Search Detection] fa distinzione tra maiuscole e minuscole. Ad esempio, una regola che specifica “PID” come parametro di stringa query non corrisponderà a “pid”. Se l’organizzazione utilizza casi misti, inserisci i valori esatti come regole separate, in modo che tutti i parametri della stringa di query desiderati possano essere rilevati. |
