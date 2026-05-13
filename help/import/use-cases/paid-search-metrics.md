---
title: Importare metriche di ricerca a pagamento
description: Passaggi per configurare Adobe Analytics per tenere traccia delle metriche di ricerca a pagamento (ad esempio, Google Ads, Microsoft Advertising, ecc.) utilizzo di Origini dati.
exl-id: b25a2a26-d277-4a51-9194-973acb425095
feature: Data Sources
TQID: https://experienceleague.adobe.com/QGwbmxtBYd0zgg5Zum-ErovDVJK2-wQnrXfqJztLjrA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: beb7a3c1-66ab-4786-b879-7621375b3c40
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1109
ht-degree: 3%

---

# Importa metriche [!UICONTROL Paid Search] tramite [!UICONTROL Data Sources]

Per molte organizzazioni di marketing, la ricerca a pagamento è uno dei modi più importanti e affidabili&#x200B; sia per raggiungere nuovi clienti che per mantenere quelli esistenti. La funzionalità [!UICONTROL Data Sources] di Adobe Analytics semplifica l&#39;importazione di dati di ricerca avanzata a pagamento da piattaforme di pubblicità digitale come Google Ads. Puoi integrarli con gli altri dati di marketing, insieme ai dati comportamentali e agli attributi cliente sul sito, per consentirti di ottenere informazioni migliori sulle attività di ricerca a pagamento della tua organizzazione.

Questi passaggi mostrano come configurare un’integrazione con Ads per importare dati da parole chiave, nonché metriche quali impression, clic, costo per clic e altro ancora.

I passaggi spiegano come impostare un’importazione una tantum di dati pay-per-click. Tuttavia, [!UICONTROL Data Sources] consente l&#39;importazione continua dei dati utilizzando il formato di file descritto qui. A seconda della piattaforma di ricerca a pagamento, puoi pianificare esportazioni periodiche (giornaliere, mensili ecc.), impostare processi automatizzati per trasformare tali esportazioni nel formato di file richiesto da Adobe Analytics e caricare tali file in Adobe Analytics per i rapporti sull’integrazione della ricerca a pagamento.

## Prerequisiti

* Hai implementato il rilevamento di ricerche a pagamento.
* Stai acquisendo i dati del codice di tracciamento.
* Disponi di codici di tracciamento univoci per ciascun gruppo di annunci.

## Configura [!UICONTROL Success Events]

Il primo passaggio consiste nel preparare Adobe Analytics a ricevere le metriche. A questo scopo, devi impostare alcuni eventi di successo.

[!UICONTROL Success events] sono azioni che possono essere tracciate. È possibile determinare l&#39;entità di [!UICONTROL success event]. Ai fini del tracciamento delle metriche [!UICONTROL paid search], è necessario impostare [!UICONTROL success events] intorno a [!UICONTROL clicks], [!UICONTROL impressions], [!UICONTROL total cost] e abilitare [!UICONTROL tracking codes].

1. Vai a **[!UICONTROL Adobe Analytics > Admin > Report Suites]**.
1. Seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings > Conversion > Success Events]**.

   ![Eventi di successo](assets/success-events.png)

1. In Eventi di successo personalizzati, utilizzare **[!UICONTROL Add New]** per creare 3 eventi di successo personalizzati: [!UICONTROL Clicks] (contatore), [!UICONTROL Impressions] (contatore) e [!UICONTROL Total Cost] (valuta).

   ![Nuovo evento di successo](assets/new-success-events.png)

1. Fai clic su Salva.
Dovresti ricevere un messaggio che informa che i tuoi salvataggi sono stati approvati.
1. Passa a **[!UICONTROL Admin > Report Suites > Edit Settings > Conversion > Conversion Variables]**.
1. Abilitare i codici di tracciamento selezionando la casella di controllo accanto a **[!UICONTROL Tracking Code]** in **[!UICONTROL Campaign > Campaign Variable]**.

   ![Variabile di Campaign](assets/campaign-variable.png)

## Configurare le origini dati

[!UICONTROL Data Sources] ti consente di condividere dati non clickstream con Adobe Analytics. In questo caso usiamo Adobe Analytics per tenere traccia delle metriche di ricerca a pagamento. Utilizziamo il codice di tracciamento come chiave per collegare i due dati (metriche di ricerca a pagamento e metriche di Adobe Analytics).

1. Passa a **[!UICONTROL Adobe Analytics > Admin > All admin > Data sources]**.
1. Selezionare la scheda **[!UICONTROL Create]** per avviare l&#39;attivazione di nuove origini dati.
1. Sotto **[!UICONTROL Select Category]**, seleziona **[!UICONTROL Ad Campaign]**.

   ![Origini dati](assets/data-sources.png)

1. Sotto **[!UICONTROL Select Type]**, seleziona **[!UICONTROL Generic Pay-Per-Click Service]**.
1. Fai clic su **[!UICONTROL Activate]**.
[!UICONTROL Data Source Activation Wizard] visualizza:

   ![Attivazione guidata](assets/ds-activation-wizard.png)

1. Fare clic su **[!UICONTROL Next]** e assegnare un nome all&#39;origine dati. Questo nome viene visualizzato in Data Source Manager.
1. Accettare il contratto di assistenza e fare clic su **[!UICONTROL Next]**.
1. Selezionare le tre metriche standard [!UICONTROL Impressions], [!UICONTROL Clicks] e [!UICONTROL Total Cost] e fare clic su **[!UICONTROL Next]**.
1. Ora &quot;mappare&quot; questa nuova origine dati agli eventi personalizzati creati in [Eventi di successo](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md).

   ![Mappatura](assets/data-source-mapping.png)

1. Scegli dimensioni dati
Selezionare la casella accanto a Codici di tracciamento e fare clic su **[!UICONTROL Next]**.
1. Mappa dimensioni dati.
Mappa la dimensione dati importata (attributo) sull’attributo Adobe Analytics in cui desideri memorizzarla. Può trattarsi di una dimensione standard o di un’eVar. Dopo aver fatto clic su **[!UICONTROL Next]**, le mappature risultanti vengono visualizzate nel riepilogo:

   ![Riepilogo](assets/data-source-summary.png)

1. Fai clic su **[!UICONTROL Save]**.
1. Fare clic su **[!UICONTROL Download]** per scaricare il file modello per questa origine dati.
Il nome del file corrisponde al tipo di origine dati specificato inizialmente, in questo caso &quot;Generic Pay-Per-Click Service template.txt&quot;.
1. Apri il modello nel tuo editor di testo preferito.
Il file è già compilato con le metriche, le dimensioni e le relative mappature.

## Esportare i dati PPC e caricarli in Analytics

Passaggi simili a questi funzionano per Google Ads, Microsoft Advertising e altri account PPC.

### Esporta dati

1. Accedi al tuo account PPC e crea un nuovo report o esporta.
Assicurati che l’esportazione includa i seguenti campi: data, URL di destinazione (pagina di destinazione), impression, clic e costo. L’esportazione può includere altri campi, ma li eliminerai seguendo la procedura riportata di seguito.
1. Se possibile, salvare il report come file `.csv` o delimitato da tabulazioni. In questo modo sarà più semplice utilizzare nei passaggi seguenti.
1. Apri il file in Microsoft Excel.

### Modificare il file in Microsoft Excel

1. In Microsoft Excel eliminare tutte le colonne diverse da quelle sopra indicate.
1. Elimina eventuali righe in eccesso nella parte superiore.
1. Per isolare i codici di tracciamento dagli URL di destinazione:
a. Copia e incolla dati da tutte le colonne.
b. Fai clic su **[!UICONTROL Data > Text to Columns]**.
c. Nel passaggio 1 della procedura guidata, assicurarsi che **[!UICONTROL Delimited]** sia selezionato e fare clic su **[!UICONTROL Next]**.
d. Nel passaggio 2 della procedura guidata, specifica il delimitatore a seconda di come hai creato gli URL (? o &amp;) e fare clic su **[!UICONTROL Next]**.
e. Nel passaggio 3 della procedura guidata, visualizza l’anteprima dei dati e assicurati che una delle colonne sia &quot;trackingcodename=trackingcode&quot;. Se disponi di variabili aggiuntive, ripeti questi passaggi (utilizzando &amp; come delimitatore).
f. Elimina tutte le colonne ad eccezione dei codici di tracciamento, delle impression, dei clic e dei costi. Aggiungi una nuova colonna denominata Data e organizza le colonne nel seguente ordine: Data :: Codice di tracciamento :: Impression :: Clic :: Costo.
1. Aggiungi questi dati al modello scaricato nella sezione &quot;Imposta origini dati&quot; di cui sopra.
Ora puoi caricare il file.

### Carica il file in Adobe Analytics tramite FTP

Torna alla procedura guidata Source dati per istruzioni e carica il file tramite FTP:

![Carica FTP](assets/upload-ftp.png)

## Creare metriche calcolate

L’aggiunta di metriche calcolate sarà utile quando si prendono decisioni pay-per-click.

Ad esempio, puoi aggiungere queste [metriche calcolate](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md#calculated-metrics):

| Nome | Formula | Tipi di metriche | Descrizione |
| --- | --- | --- | --- |
| Visualizzazioni pagina per visita | Visualizzazioni/visite pagina | Numerici | Se applicato a livello di sito: mostra il numero medio di pagine per visita. Quando applicato nel rapporto Pagine più popolari: mostra il numero medio di volte in cui una pagina specifica è stata visualizzata per visita. |
| Valore medio ordine | Ricavi/Ordini | Valuta | Mostra i ricavi medi per ordine. |
| Ricavo per visita | Ricavo/visita | Valuta | Mostra il reddito medio per visita. |
| Percentuale di click-through (CTR) | Clic/impressioni | Numerici | Misura il rapporto tra clic e impression di un annuncio online o di una campagna di marketing via e-mail. |
| Profitto | Ricavi - Costo | Valuta | Mostra i ricavi di una campagna meno il costo. |
| Profitto per impression (PPI) | (Ricavi - Costo)/Impression | Valuta | Mostra l’importo dei ricavi generati ogni volta che un annuncio veniva visualizzato, bilanciato con il costo. |
| ROAS (Return on Ad Spend) | Importo vendite/spesa pubblicitaria | Valuta | (ROI) Rappresenta i dollari guadagnati per ogni dollaro speso per la corrispondente pubblicità. |

## Configurare ed eseguire rapporti

Il passaggio finale consiste nell’aggiungere le metriche dell’origine dati e tutte le metriche calcolate al rapporto Codice di tracciamento e approfondire una campagna per ottenere una visualizzazione immediata delle prestazioni di ogni gruppo di annunci.

1. In **[!UICONTROL Adobe Analytics > Reports]**, selezionare la suite di rapporti in cui sono state importate le origini dati.
1. Passa a **[!UICONTROL Reports > Campaigns > Tracking Code > Tracking Code]**.
1. Seleziona l’intervallo di date.
1. Fai clic su **[!UICONTROL Metrics > Add]** e aggiungi le metriche dell&#39;origine dati (clic, impression, costo totale) dall&#39;elenco delle metriche standard.
1. Fai lo stesso per qualsiasi metrica calcolata aggiunta. Il rapporto verrà aggiornato man mano che aggiungi le metriche.
