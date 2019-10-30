---
description: Definisce le impostazioni comuni per un sito Web che fornisce informazioni su servizi e prodotti solitamente venduti attraverso un ulteriore coinvolgimento.
seo-description: Definisce le impostazioni comuni per un sito Web che fornisce informazioni su servizi e prodotti solitamente venduti attraverso un ulteriore coinvolgimento.
seo-title: Generazione di lead
solution: Analytics
title: Generazione di lead
topic: Strumenti di amministrazione
uuid: e7d3cc4a-1bee-4722-92c1-4454f7613d39
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Generazione di lead

Definisce le impostazioni comuni per un sito Web che fornisce informazioni su servizi e prodotti solitamente venduti attraverso un ulteriore coinvolgimento.

| Variabili di conversione | Type (Tipo) | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Promozione interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Tipo evento self-service | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |

Nessun evento di successo è configurato da questo modello di suite di rapporti.

| Variabili di analisi personalizzate | `s_code` variable |
|---|---|
| Protetto/Non Protetto | `prop1` |
| Proprietà traffico 2 - 5 | `prop2, prop3, prop4, prop5` |

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

