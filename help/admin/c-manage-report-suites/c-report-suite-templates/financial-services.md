---
description: Definisce le impostazioni comuni per le banche e altri istituti che consentono l'accesso ai servizi online.
seo-description: Definisce le impostazioni comuni per le banche e altri istituti che consentono l'accesso ai servizi online.
seo-title: Servizi finanziari
solution: Analytics
title: Servizi finanziari
topic: Strumenti di amministrazione
uuid: a 321 b 409-24 a 4-4 d 9 f -9 aac -65761261 e 991
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Servizi finanziari

Definisce le impostazioni comuni per le banche e altri istituti che consentono l'accesso ai servizi online.

| Conversion Variables (Variabili di conversione) (eVars) | Type (Tipo) | Sottorelazioni | Allocazione | Scadenza | `s_code` variable |
|---|---|---|---|---|---|
| Promozione interna | Stringa | Base | Più recente (ultimo) | Visita | `evar1` |
| Termini di ricerca interni | Stringa | Base | Più recente (ultimo) | Visita | `evar2` |
| Tipo evento self-service | Stringa | Base | Più recente (ultimo) | Visita | `evar3` |

Nessun evento di successo è configurato da questo modello di suite di rapporti.

| Custom Insight Variables (Variabili di Insight personalizzate) | `s_code` variable |
|---|---|
| Protetto/Non protetto | `prop1` |
| Proprietà traffico 2 - 5 | `prop2, prop3, prop4, prop5` |

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

