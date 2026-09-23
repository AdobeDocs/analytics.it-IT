---
title: Consenso per la piattaforma di annunci
description: Consulta la configurazione per il consenso pubblicitario per i provider di annunci di terze parti.
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
TQID: https://experienceleague.adobe.com/Ou6-B5pFx-ku9H2iEqLN0Ly6-t01CzQUODo0poMk8Bs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 5%
---
# Consenso per la piattaforma di annunci

La &#39;Dimensione del consenso della piattaforma dell&#39;annuncio&#39; [1} indica se viene raccolto il consenso per inviare dati a provider pubblicitari di terze parti, come Google, Meta e altri.](overview.md)

Attualmente, questa dimensione viene utilizzata solo per Google. A causa delle normative europee sulla privacy, il Digital Markets Act (DMA), Google richiede che i dati inviati ai propri server e raccolti in Europa indichino se il consenso è raccolto. Alcuni clienti di Analytics inviano i dati di un evento tramite Adobe Advertising come eventi di conversione a Google.

In futuro, questa dimensione può essere utilizzata per supportare la codifica di informazioni aggiuntive sul consenso per altri provider pubblicitari di terze parti.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalla [variabile di dati di contesto](/help/implement/vars/page-vars/contextdata.md) `contextData.['adConsent']`. Compilare questa variabile con i valori dei campi di consenso pertinenti di Google: `ad_user_data` (primo carattere) e `ad_personalization` (secondo carattere). Per ulteriori informazioni, consulta [Consenso nel riferimento API di Google Ads](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent).

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (impostato tramite la variabile di dati di contesto `adConsent`) |
| **Campo Web SDK / XDM** | Nessuno |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | 100 byte |
| **Persistenza** | Hit |

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

* Feed di dati: i dati del consenso dell&#39;annuncio sono disponibili utilizzando la `dataprivacydmaconsent` [colonna](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Rapporti di Data Warehouse: i dati sul consenso degli annunci sono disponibili utilizzando la dimensione **[!UICONTROL Ad Platform Consent]**.

La tua organizzazione determina la logica per implementare questa variabile di dati di contesto. Il valore non persiste oltre l’hit su cui è impostato, pertanto devi impostare la variabile di dati di contesto su ogni pagina.

Quando invii dati pubblicitari da Adobe Analytics tramite Adobe Advertising come eventi di conversione a Google, consulta il team di Adobe Advertising per assistenza sull’integrazione.

Per ulteriori informazioni, consulta [Informativa sulla privacy](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md).
