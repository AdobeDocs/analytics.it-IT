---
description: Definisce le impostazioni comuni per un sito Web di e-commerce.
seo-description: Definisce le impostazioni comuni per un sito Web di e-commerce.
seo-title: Commercio
solution: Analytics
title: Commercio
topic: Strumenti di amministrazione
uuid: 85fc235d-0180-4245-b831-0243ebe3c40c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Commercio

Definisce le impostazioni comuni per un sito Web di e-commerce.

| Variabili di conversione | Type (Tipo) | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Promozioni interne | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Categoria merchandising | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |
| Variabile Commerce 4 | Stringa | Base | Più recente (ultimo) | Visita | `evar4` |
| Variabile Commerce 5 | Stringa | Base | Più recente (ultimo) | Visita | `evar5` |

| Eventi di successo | Type (Tipo) | `s_code` variable |
|---|---|---|
| Registrazioni | Contatore (nessuna sottorelazione) | `event1` |
| Eventi personalizzati 1-5 | Contatore (nessuna sottorelazione) | `event1, event2, event3, event4, event5` |

| Variabili di analisi personalizzate | `s_code` variable |
|---|---|
| Proprietà Traffico 1 - 5 | `prop1, prop2, prop3, prop4, prop5` |

La tabella seguente contiene un elenco degli eventi commerciali standard. La configurazione iniziale di questi eventi è identica in tutti i modelli delle suite di rapporti. Gli eventi con una variabile s_code di N/D non devono essere impostati, ma vengono forniti automaticamente.

| Eventi Commerce Standard | Type (Tipo) | `s_code` variable |
|---|---|---|
| Ricavi |  Contatore | `purchase` |
| Ordini |  Contatore | `purchase` |
| Unità |  Contatore | `purchase` |
| Carrelli |  Contatore | `scOpen` |
| Visualizzazioni carrello |  Contatore | `scView` |
| Istanze |  Contatore | N/D |
| Pagamenti |  Contatore | `scCheckout` |
| Aggiunte carrello |  Contatore | `scAdd` |
| Rimozioni carrello |  Contatore | `scRemove` |
| Visite | Contatore (nessuna sottorelazione) | N/D |
| Visualizzazioni pagina | Contatore (nessuna sottorelazione) | N/D |
| Visitatori giornalieri unici | Contatore (nessuna sottorelazione) | N/D |
| Visitatori unici | Contatore (nessuna sottorelazione) | N/D |

