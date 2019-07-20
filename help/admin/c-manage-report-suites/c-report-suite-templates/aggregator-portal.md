---
description: Definisce le impostazioni comuni per un sito Web che aggrega contenuto, ad esempio un portale di notizie.
seo-description: Definisce le impostazioni comuni per un sito Web che aggrega contenuto, ad esempio un portale di notizie.
seo-title: Portale Aggregator
solution: Analytics
title: Portale Aggregator
topic: Strumenti di amministrazione
uuid: d 227 c 209-4 d 88-4 eff-b 126-994 b 2 a 179 c 51
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Portale Aggregator

Definisce le impostazioni comuni per un sito Web che aggrega contenuto, ad esempio un portale di notizie.

| Variabili di conversione | Type (Tipo) | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Campagna interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Categoria di riferimento | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |

| Eventi di successo | Type (Tipo) | `s_code` variable |
|---|---|---|
| Accesso | Contatore (nessuna sottorelazione) | `event1` |
| Visualizzazione riferimento | Contatore (nessuna sottorelazione) | `event2` |
| Clic sul riferimento | Contatore (nessuna sottorelazione) | `event3` |

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

