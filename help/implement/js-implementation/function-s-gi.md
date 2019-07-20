---
description: La funzione s_ gi () viene utilizzata per creare o trovare l'istanza di appmeasurement tramite ID suite di rapporti. Internamente, appmeasurement tiene traccia di ogni istanza creata e s_ gi () restituisce l'istanza esistente per una suite di rapporti, se presente. Se un'istanza non esiste, viene creata e restituita una nuova istanza.
keywords: Implementazione di Analytics
seo-description: La funzione s_ gi () viene utilizzata per creare o trovare l'istanza di appmeasurement tramite ID suite di rapporti. Internamente, appmeasurement tiene traccia di ogni istanza creata e s_ gi () restituisce l'istanza esistente per una suite di rapporti, se presente. Se un'istanza non esiste, viene creata e restituita una nuova istanza.
seo-title: La funzione s_ gi ()
solution: Analytics
title: La funzione s_ gi ()
topic: Sviluppatore e implementazione
uuid: a 77 de 90 e-c 60 e -4946-90 cf-unknown 8 aa 3 d 755
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# La funzione s_ gi ()

La funzione s_ gi () viene utilizzata per creare o trovare l'istanza di appmeasurement tramite ID suite di rapporti. Internamente, appmeasurement tiene traccia di ogni istanza creata e s_ gi () restituisce l'istanza esistente per una suite di rapporti, se presente. Se un'istanza non esiste, viene creata e restituita una nuova istanza.

We recommend calling `s_gi()` before setting variables and making tracking calls throughout your page code. Questo assicura che l'oggetto corretto venga utilizzato per effettuare la chiamata di tracciamento nel caso in cui la variabile s venga inavvertitamente sovrascritta.

## Using Multiple Report Suites {#section_F2F3B76E7AFD4B4B91CDC8BBEB34BBC5}

L'oggetto restituito varia in base agli ID suite di rapporti passati. For example, if you make the following initial call to `s_gi()`:

```
var s=s_gi('rsid1,rsid2')
```

La tabella seguente delinea ciò che viene restituito dalle chiamate successive:

| ** Chiamata successiva a s_ gi** | ** Descrizione dell'oggetto restituito** |
|---|---|
| `s=s_gi('rsid1,rsid2')` | Lo stesso oggetto a cui fa riferimento in precedenza. |
| `s=s_gi('rsid1')` | Una copia dell'oggetto creato in precedenza, ma non l'originale. |
| `s=s_gi('rsid1,rsid3')` | Una copia dell'oggetto creato in precedenza, ma non l'originale. |
| `s=s_gi('rsid3')` | Un nuovo oggetto vuoto, senza impostazione di variabili di configurazione (ad es. linktrackvars è vuoto, come linkdownloadfiletypes). |

