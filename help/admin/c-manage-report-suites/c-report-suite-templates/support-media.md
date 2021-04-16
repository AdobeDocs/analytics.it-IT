---
description: Fornisce impostazioni comuni per un sito web che fornisce articoli e video di supporto ai prodotti.
title: Supporto media
feature: Strumenti di amministrazione
uuid: 6072f14c-a67d-470c-b977-c18e26e901db
exl-id: f522173a-8f58-4fa4-868b-251158a71e26
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 26%

---

# Supporto media

Fornisce impostazioni comuni per un sito web che fornisce articoli e video di supporto ai prodotti.

| Variabili di conversione | Tipo | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Promozione interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Tipo di evento self-service | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |

Nessun evento di successo è configurato da questo modello di suite di rapporti.

| Variabili Custom Insight | `s_code` variable |
|---|---|
| Protetto/Non protetto | `prop1` |
| Proprietà traffico 2 - 5 | `prop2, prop3, prop4, prop5` |

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
