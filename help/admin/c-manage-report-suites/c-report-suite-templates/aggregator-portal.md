---
description: Definisce le impostazioni comuni per un sito web che aggrega il contenuto, ad esempio un portale di notizie.
title: Portale Aggregator
feature: Admin Tools
uuid: d227c209-4d88-4eff-b126-994b2a179c51
exl-id: 48f57f27-289c-4e26-9fb2-e34d48c1f2e6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 26%

---

# Portale Aggregator

Definisce le impostazioni comuni per un sito web che aggrega il contenuto, ad esempio un portale di notizie.

| Variabili di conversione | Tipo | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Campagna interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Categoria di riferimento | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |

| Eventi di successo | Tipo | `s_code` variable |
|---|---|---|
| Accesso | Contatore (nessuna sottorelazione) | `event1` |
| Visualizzazione di riferimento | Contatore (nessuna sottorelazione) | `event2` |
| Clic di riferimento | Contatore (nessuna sottorelazione) | `event3` |

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
