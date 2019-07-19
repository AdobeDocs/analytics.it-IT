---
description: Definisce le impostazioni comuni per un sito Web per e-commerce.
seo-description: Definisce le impostazioni comuni per un sito Web per e-commerce.
seo-title: Commerce
solution: Analytics
title: Commerce
topic: Strumenti di amministrazione
uuid: 85 fc 235 d -0180-4245-b 831-0243 ebe 3 c 40 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Commerce

Definisce le impostazioni comuni per un sito Web per e-commerce.

| Variabili di conversione | Type (Tipo) | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Promozioni interne | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Categoria merchandising | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |
| Commerce Variabile 4 | Stringa | Base | Più recente (ultimo) | Visita | `evar4` |
| Commerce Variabile 5 | Stringa | Base | Più recente (ultimo) | Visita | `evar5` |

| Eventi di successo | Type (Tipo) | `s_code` variable |
|---|---|---|
| Registrazioni | Contatore (nessuna sottorelazione) | `event1` |
| Eventi personalizzati 1-5 | Contatore (nessuna sottorelazione) | `event1, event2, event3, event4, event5` |

| Custom Insight Variables (Variabili di Insight personalizzate) | `s_code` variable |
|---|---|
| Proprietà traffico 1 - 5 | `prop1, prop2, prop3, prop4, prop5` |

La tabella seguente contiene un elenco degli eventi di commercio standard. La configurazione iniziale per questi eventi è identica in tutti i modelli delle suite di rapporti. Gli eventi con una variabile s_ code di N/D non devono essere impostati, vengono forniti automaticamente.

| Eventi commerciali standard | Type (Tipo) | `s_code` variable |
|---|---|---|
| Ricavi | Contatore | `purchase` |
| Ordini | Contatore | `purchase` |
| Unità | Contatore | `purchase` |
| Carrelli | Contatore | `scOpen` |
| Visualizzazioni carrello | Contatore | `scView` |
| Istanze | Contatore | N/D |
| Pagamenti | Contatore | `scCheckout` |
| Aggiunte carrello | Contatore | `scAdd` |
| Rimozioni carrello | Contatore | `scRemove` |
| Visite | Contatore (nessuna sottorelazione) | N/D |
| Visualizzazioni pagina | Contatore (nessuna sottorelazione) | N/D |
| Visitatori giornalieri univoci | Contatore (nessuna sottorelazione) | N/D |
| Visitatori univoci | Contatore (nessuna sottorelazione) | N/D |

