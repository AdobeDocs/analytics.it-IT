---
description: Definisce le impostazioni comuni per un sito Web che aggrega il contenuto, ad esempio un portale di notizie.
title: Portale Aggregator
feature: Report Suite Settings
exl-id: 48f57f27-289c-4e26-9fb2-e34d48c1f2e6
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 80%

---

# Portale Aggregator

Definisce le impostazioni comuni per un sito Web che aggrega il contenuto, ad esempio un portale di notizie.

| Variabili di conversione | Tipo | Sottorelazioni | Allocazione | Scadenza | variabile `s_code` |
|---|---|---|---|---|---|
| Campagna interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Categoria di riferimento | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |

| Eventi di successo | Tipo | variabile `s_code` |
|---|---|---|
| Accedi | Contatore (nessuna sottorelazione) | `event1` |
| Visualizzazione referral | Contatore (nessuna sottorelazione) | `event2` |
| Clic sui riferimenti | Contatore (nessuna sottorelazione) | `event3` |

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
