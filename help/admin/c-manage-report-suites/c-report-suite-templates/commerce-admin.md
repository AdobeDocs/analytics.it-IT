---
description: Definisce le impostazioni comuni per un sito web di e-commerce.
title: Commerce
feature: Strumenti di amministrazione
uuid: 85fc235d-0180-4245-b831-0243ebe3c40c
exl-id: 90e5d446-10b8-4d40-8bd0-8b13e1c2f603
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 27%

---

# Commerce

Definisce le impostazioni comuni per un sito web di e-commerce.

| Variabili di conversione | Tipo | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Promozioni interne | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Categoria merchandising | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |
| Variabile Commerce 4 | Stringa | Base | Più recente (ultimo) | Visita | `evar4` |
| Variabile Commerce 5 | Stringa | Base | Più recente (ultimo) | Visita | `evar5` |

| Eventi di successo | Tipo | `s_code` variable |
|---|---|---|
| Registrazioni | Contatore (nessuna sottorelazione) | `event1` |
| Eventi personalizzati 1-5 | Contatore (nessuna sottorelazione) | `event1, event2, event3, event4, event5` |

| Variabili Custom Insight | `s_code` variable |
|---|---|
| Proprietà traffico 1 - 5 | `prop1, prop2, prop3, prop4, prop5` |

La tabella seguente contiene un elenco degli eventi di e-commerce standard. La configurazione iniziale di questi eventi è identica in tutti i modelli della suite di rapporti. Gli eventi con una variabile s_code di N/D non devono essere impostati, ma vengono forniti automaticamente.

| Eventi Commerce standard | Tipo | `s_code` variable |
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
