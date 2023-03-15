---
description: Configura diverse variabili comuni ed eventi di successo per un sito web tipico.
title: Modello predefinito
feature: Report Suite Settings
uuid: edcf1b97-4ff2-4e98-b84c-199af2181d68
exl-id: 36aaded4-5c46-41af-a5c6-216bd2fcadb2
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 85%

---

# Modello predefinito

Configura diverse variabili comuni ed eventi di successo per un sito web tipico.

| Variabili di conversione | Tipo | Sottorelazioni | Allocazione | Scadenza | variabile `s_code` |
|---|---|---|---|---|---|
| Campagna interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Variabile Commerce 3 | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |
| Variabile Commerce 4 | Stringa | Base | Più recente (ultimo) | Visita | `evar4` |

| Eventi di successo | Tipo | variabile `s_code` |
|---|---|---|
| Registrazioni | Contatore (nessuna sottorelazione) | `event1` |
| Registrazioni e-mail | Contatore (nessuna sottorelazione) | `event2` |
| Abbonamenti | Contatore (nessuna sottorelazione) | `event3` |
| Visualizzazioni pagina | Contatore (nessuna sottorelazione) | `event4` |
| Impression annuncio | Contatore (nessuna sottorelazione) | `event5` |
| Clic sull’annuncio | Contatore (nessuna sottorelazione) | `event6` |

| Variabili Custom Insight | variabile `s_code` |
|---|---|
| Proprietà traffico 1 - 5 | `prop1, prop2, prop3, prop4, prop5` |

La tabella seguente contiene un elenco degli eventi di e-commerce standard. La configurazione iniziale di questi eventi è identica in tutti i modelli della suite di rapporti. Gli eventi con una variabile s_code di N/D non devono essere impostati, ma vengono forniti automaticamente.

| Eventi Commerce standard | Tipo | variabile `s_code` |
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
| Visitatori univoci giornalieri | Contatore (nessuna sottorelazione) | N/D |
| Visitatori univoci | Contatore (nessuna sottorelazione) | N/D |
