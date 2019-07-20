---
description: Definisce le impostazioni comuni per un sito Web che sviluppa contenuto originale e visualizza articoli e video.
seo-description: Definisce le impostazioni comuni per un sito Web che sviluppa contenuto originale e visualizza articoli e video.
seo-title: Contenuto e contenuti multimediali
solution: Analytics
title: Contenuto e contenuti multimediali
topic: Strumenti di amministrazione
uuid: 281 b 0 bf 8-59 dc -46 dc-b 5 d 5-5 e 42827 b 785 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Contenuto e contenuti multimediali

Definisce le impostazioni comuni per un sito Web che sviluppa contenuto originale e visualizza articoli e video.

| Variabili di conversione | Type (Tipo) | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Campagna interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Commerce Variabile 3 | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |
| Commerce Variabile 4 | Stringa | Base | Più recente (ultimo) | Visita | `evar4` |

| Eventi di successo | Type (Tipo) | `s_code` variable |
|---|---|---|
| Registrazioni | Contatore (nessuna sottorelazione) | `event1` |
| Registrazioni e-mail | Contatore (nessuna sottorelazione) | `event2` |
| Iscrizioni | Contatore (nessuna sottorelazione) | `event3` |
| Visualizzazioni pagina | Contatore (nessuna sottorelazione) | `event4` |
| Ad Impression | Contatore (nessuna sottorelazione) | `event5` |
| Clic su annunci | Contatore (nessuna sottorelazione) | `event6` |

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

