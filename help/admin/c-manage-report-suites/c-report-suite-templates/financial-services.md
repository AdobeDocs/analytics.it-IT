---
description: Definisce impostazioni comuni per le banche e altre istituzioni che forniscono accesso ai servizi online.
title: Servizi finanziari
feature: Report Suite Settings
exl-id: 2ab435e2-3fc7-46f9-aee9-961f6730f3e8
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 25%

---

# Servizi finanziari

Definisce impostazioni comuni per le banche e altre istituzioni che forniscono accesso ai servizi online.

| Conversion Variables (Variabili di conversione) (eVars) | Tipo | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
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
