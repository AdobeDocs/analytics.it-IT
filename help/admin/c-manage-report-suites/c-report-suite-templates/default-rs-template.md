---
description: Configura diverse variabili comuni e eventi di successo per un sito Web tipico.
seo-description: Configura diverse variabili comuni e eventi di successo per un sito Web tipico.
seo-title: Modello predefinito
solution: Analytics
title: Modello predefinito
topic: Strumenti di amministrazione
uuid: edcf 1 b 97-4 ff 2-4 e 98-b 84 c -199 af 2181 d 68
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Modello predefinito

Configura diverse variabili comuni e eventi di successo per un sito Web tipico.

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

