---
description: Definisce le impostazioni comuni per un sito Web che aggrega il contenuto, ad esempio un portale di notizie.
seo-description: Definisce le impostazioni comuni per un sito Web che aggrega il contenuto, ad esempio un portale di notizie.
seo-title: Portale Aggregator
solution: Analytics
title: Portale Aggregator
topic: Strumenti di amministrazione
uuid: d227c209-4d88-4eff-b126-994b2a179c51
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Portale Aggregator

Definisce le impostazioni comuni per un sito Web che aggrega il contenuto, ad esempio un portale di notizie.

| Variabili di conversione | Type (Tipo) | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Campagna interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Categoria di riferimento | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |

| Eventi di successo | Type (Tipo) | `s_code` variable |
|---|---|---|
| Accesso | Contatore (nessuna sottorelazione) | `event1` |
| Visualizzazione riferimento | Contatore (nessuna sottorelazione) | `event2` |
| Clic Di Riferimento | Contatore (nessuna sottorelazione) | `event3` |

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

