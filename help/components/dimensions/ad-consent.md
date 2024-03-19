---
title: Consenso annuncio
description: Consulta la configurazione per il consenso pubblicitario per i provider di annunci di terze parti.
feature: Dimensions
source-git-commit: b5aba8a42f524ef3367a779e6fb1a731de680750
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 1%

---

# Consenso annuncio

Il &quot;Consenso dell’annuncio&quot; [dimensione](overview.md) mostra se il consenso viene raccolto per inviare dati a provider pubblicitari di terze parti, come Google, Meta e altri.

Attualmente, questa dimensione viene utilizzata solo per Google. A causa delle normative europee sulla privacy, il Digital Markets Act (DMA), Google richiede che i dati inviati ai propri server e raccolti in Europa indichino se il consenso è raccolto. Alcuni clienti di Analytics inviano i dati di un evento tramite Adobi Advertising come eventi di conversione a Google.

In futuro, questa dimensione può essere utilizzata per supportare la codifica di informazioni sul consenso aggiuntive per altri provider pubblicitari di terze parti.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dai seguenti elementi [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md)

* `contextData.['adConsent']`

Compila la variabile di dati di contesto con i valori pertinenti per i campi di consenso di Google

* `ad_user_data` (primo carattere) e
* `ad_personalization` (secondo carattere).

Consulta [Consenso nel riferimento API di Google Ads](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) per ulteriori informazioni.

I valori possibili per ciascuno di questi campi possono essere:

| Valore | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | Concedi il consenso a Google per i dati degli utenti degli annunci. | Concedi il consenso a Google per la personalizzazione degli annunci. |
| `N` | Nega il consenso a Google per i dati degli utenti dell’annuncio. | Denti il consenso a Google per la personalizzazione degli annunci. |
| `U` | Non specificato. | Non specificato. |

L’esempio seguente concede il consenso a Google per i dati degli utenti degli annunci ma non per la personalizzazione degli annunci:

```
contextData.['adConsent'] = "YN..."
```

I caratteri oltre il primo e il secondo carattere vengono attualmente ignorati.

## Utilizzare i dati

Puoi utilizzare i dati raccolti sull’annuncio e sul consenso:

* Feed di dati: i dati sul consenso degli annunci sono disponibili utilizzando `dataprivacydmaconsent` [colonna](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Data Warehouse rapporti: i dati sul consenso dell’annuncio sono disponibili utilizzando **[!UICONTROL Ad Platform Consent]** dimensione.


La tua organizzazione determina la logica per implementare questa variabile di dati di contesto. Il valore non persiste oltre l’hit su cui è impostato, pertanto devi impostare la variabile di dati di contesto su ogni pagina.

Quando invii dati pubblicitari da Adobe Analytics tramite Adobi Advertising come eventi di conversione a Google, consulta il team di Adobi Advertising per assistenza nell’integrazione.

Per ulteriori informazioni, consulta [Rapporti sulla privacy](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md).
