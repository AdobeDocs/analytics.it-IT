---
description: Configura diverse variabili comuni ed eventi di successo per un sito Web tipico.
title: Modello predefinito
topic: Admin tools
uuid: edcf1b97-4ff2-4e98-b84c-199af2181d68
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Modello predefinito

Configura diverse variabili comuni ed eventi di successo per un sito Web tipico.

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
| Visitatori giornalieri unici | Contatore (nessuna sottorelazione) | N/D |
| Visitatori unici | Contatore (nessuna sottorelazione) | N/D |

