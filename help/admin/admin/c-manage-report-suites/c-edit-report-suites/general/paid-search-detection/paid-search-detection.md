---
description: La funzione Rilevamento ricerca a pagamento differenzia le ricerche naturali nei report Motori di ricerca e Parole chiave di ricerca.
title: Rilevamento di ricerca a pagamento
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: ht
source-wordcount: '171'
ht-degree: 100%

---

# Rilevamento di ricerca a pagamento

[!UICONTROL Paid Search Detection] si distingue dalle ricerche naturali nei rapporti [!UICONTROL Search Engines] e [!UICONTROL Search Keywords]. Puoi specificare i motori di ricerca in cui utilizzi gli annunci a pagamento e specificare una stringa di caratteri trovata nell’URL di una visita da un annuncio a pagamento.

## Opzioni di configurazione {#section_0C2CFA0AF77B47098BE37CB024665D0D}

Nella tabella seguente sono descritti i campi e le opzioni utilizzati per [configurare il rilevamento di ricerche a pagamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md).

| Opzione | Descrizione |
| --- | --- |
| [!UICONTROL Search Engine] | Seleziona un motore di ricerca dall’elenco a discesa. È possibile specificare il motore se si utilizzano parametri di stringa di query diversi per motori di ricerca diversi. Di solito, il valore `Any` è sufficiente. |
| [!UICONTROL Query string] | Specifica una stringa per una corrispondenza sensibile a maiuscole e minuscole con qualsiasi parte del parametro della stringa query, che è la parte dell&#39;url dopo il “?”. <br>**Nota**: [!UICONTROL Paid Search Detection] fa distinzione tra maiuscole e minuscole. Ad esempio, una regola che specifica “PID” come parametro di stringa query non corrisponderà a “pid”. Se l’organizzazione utilizza casi misti, inserisci i valori esatti come regole separate, in modo che tutti i parametri della stringa di query desiderati possano essere rilevati. |
