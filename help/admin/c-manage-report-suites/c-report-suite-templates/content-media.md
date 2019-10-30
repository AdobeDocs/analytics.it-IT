---
description: Definisce le impostazioni comuni per un sito Web che sviluppa il contenuto originale e visualizza articoli e video.
seo-description: Definisce le impostazioni comuni per un sito Web che sviluppa il contenuto originale e visualizza articoli e video.
seo-title: Contenuto e media
solution: Analytics
title: Contenuto e media
topic: Strumenti di amministrazione
uuid: 281b0bf8-59dc-46dc-b5d5-5e42827b785d
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Contenuto e media

Definisce le impostazioni comuni per un sito Web che sviluppa il contenuto originale e visualizza articoli e video.

| Variabili di conversione | Type (Tipo) | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Campagna interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Variabile Commerce 3 | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |
| Variabile Commerce 4 | Stringa | Base | Più recente (ultimo) | Visita | `evar4` |

| Eventi di successo | Type (Tipo) | `s_code` variable |
|---|---|---|
| Registrazioni | Contatore (nessuna sottorelazione) | `event1` |
| Registrazioni e-mail | Contatore (nessuna sottorelazione) | `event2` |
| Iscrizioni | Contatore (nessuna sottorelazione) | `event3` |
| Visualizzazioni pagina | Contatore (nessuna sottorelazione) | `event4` |
| Ad Impression | Contatore (nessuna sottorelazione) | `event5` |
| Aggiungi clic | Contatore (nessuna sottorelazione) | `event6` |

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

