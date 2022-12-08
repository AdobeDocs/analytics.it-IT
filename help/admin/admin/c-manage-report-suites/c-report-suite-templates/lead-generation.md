---
description: Definisce le impostazioni comuni per un sito web che fornisce informazioni su servizi e prodotti generalmente venduti attraverso un ulteriore coinvolgimento.
title: Generazione di lead
feature: Report Suite Settings
exl-id: 4a629908-2bb4-4d61-a934-42906edff9df
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 70%

---

# Generazione di lead

Definisce le impostazioni comuni per un sito web che fornisce informazioni su servizi e prodotti generalmente venduti attraverso un ulteriore coinvolgimento.

| Variabili di conversione | Tipo | Sottorelazioni | Allocazione | Scadenza | variabile `s_code` |
|---|---|---|---|---|---|
| Promozione interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Tipo di evento self-service | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |

Nessun evento di successo è configurato da questo modello di suite di rapporti.

| Variabili Custom Insight | variabile `s_code` |
|---|---|
| Protetto/Non protetto | `prop1` |
| Proprietà traffico 2 - 5 | `prop2, prop3, prop4, prop5` |

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
