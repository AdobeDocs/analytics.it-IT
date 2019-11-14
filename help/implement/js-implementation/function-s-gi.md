---
description: La funzione s_gi() viene utilizzata per creare o trovare l'istanza di AppMeasurement per ID suite di rapporti. Internamente, AppMeasurement tiene traccia di ogni istanza creata e s_gi() restituisce l'istanza esistente per una suite di rapporti, se esistente. Se un'istanza non esiste, viene creata e restituita una nuova istanza.
keywords: Analytics Implementation
solution: Analytics
title: La funzione s_gi()
topic: Developer and implementation
uuid: a77de90e-c60e-4946-90cf-deaf8aa3d755
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# La funzione s_gi()

La funzione s_gi() viene utilizzata per creare o trovare l'istanza di AppMeasurement per ID suite di rapporti. Internamente, AppMeasurement tiene traccia di ogni istanza creata e s_gi() restituisce l'istanza esistente per una suite di rapporti, se esistente. Se un'istanza non esiste, viene creata e restituita una nuova istanza.

È consigliabile chiamare `s_gi()` prima di impostare le variabili e effettuare chiamate di tracciamento per tutto il codice della pagina. In questo modo l’oggetto corretto viene utilizzato per effettuare la chiamata di tracciamento nel caso in cui la variabile s venga inavvertitamente sovrascritta.

## Utilizzo di più suite di rapporti {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

L'oggetto restituito varia in base agli ID suite di rapporti passati. Ad esempio, se effettui la seguente chiamata iniziale a `s_gi()`:

```
var s=s_gi('rsid1,rsid2')
```

Nella tabella seguente sono riportati i risultati restituiti dalle chiamate successive:

| **Chiamata successiva a s_gi** | **Descrizione dell'oggetto restituito** |
|---|---|
| `s=s_gi('rsid1,rsid2')` | Lo stesso oggetto a cui si fa riferimento in precedenza. |
| `s=s_gi('rsid1')` | Una copia dell’oggetto creato in precedenza, ma non l’originale. |
| `s=s_gi('rsid1,rsid3')` | Una copia dell’oggetto creato in precedenza, ma non l’originale. |
| `s=s_gi('rsid3')` | Un nuovo oggetto vuoto, senza variabili di configurazione (ad esempio linkTrackVars è vuoto, così come linkDownloadFileTypes). |
