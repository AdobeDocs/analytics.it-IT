---
description: Definisce le impostazioni comuni per un sito web di e-commerce.
title: Commerce
feature: Report Suite Settings
exl-id: 90e5d446-10b8-4d40-8bd0-8b13e1c2f603
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: ht
source-wordcount: '181'
ht-degree: 100%

---

# Commerce

Definisce le impostazioni comuni per un sito web di e-commerce.

| Variabili di conversione | Tipo | Sottorelazioni | Allocazione | Scadenza | variabile `s_code` |
|---|---|---|---|---|---|
| Promozioni interne | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Categoria merchandising | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |
| Variabile Commerce 4 | Stringa | Base | Più recente (ultimo) | Visita | `evar4` |
| Variabile Commerce 5 | Stringa | Base | Più recente (ultimo) | Visita | `evar5` |

| Eventi di successo | Tipo | variabile `s_code` |
|---|---|---|
| Registrazioni | Contatore (nessuna sottorelazione) | `event1` |
| Eventi personalizzati 1-5 | Contatore (nessuna sottorelazione) | `event1, event2, event3, event4, event5` |

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
