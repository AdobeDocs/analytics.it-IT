---
title: Importa metriche di ricerca pagate
description: Passaggi per configurare  Adobe Analytics per tenere traccia delle metriche di ricerca a pagamento (ad esempio, Google AdWords, MSN, Yahoo, ecc.) utilizzo di Origini dati.
translation-type: tm+mt
source-git-commit: 81592ab80942b802fff3df62d2cd44b1e376aff8
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 3%

---


# Importa [!UICONTROL Paid Search] metriche utilizzando [!UICONTROL Data Sources]

Per molte organizzazioni di marketing, la ricerca a pagamento è uno dei modi più importanti e affidabili sia &#x200B; raggiungere nuovi clienti sia per mantenere quelli esistenti. La [!UICONTROL Data Sources] funzionalità di  Adobe Analytics semplifica l&#39;importazione di dati di ricerca a pagamento avanzati da piattaforme pubblicitarie digitali come Google AdWords. Puoi integrarlo con gli altri dati di marketing, insieme ai dati comportamentali e degli attributi del cliente sul posto, per consentirti di comprendere meglio le attività di ricerca a pagamento della tua organizzazione.

Questi passaggi mostrano come configurare un&#39;integrazione con AdWords per importare dati di parole chiave, nonché metriche quali impression, clic, costo per clic e altro.

I passaggi spiegano come impostare un&#39;importazione una tantum di dati Pay-Per-Click. Tuttavia, [!UICONTROL Data Sources] consente l&#39;importazione continua di dati utilizzando il formato di file descritto qui. A seconda della piattaforma di ricerca a pagamento, potrebbe essere possibile pianificare esportazioni periodiche (giornaliere, mensili, ecc.), impostare processi automatizzati per trasformare tali esportazioni nel formato di file richiesto da Adobe Analytics, e caricare questi file in  Adobe Analytics per passare alla ricerca a pagamento per i rapporti sull&#39;integrazione.

## Prerequisiti

* È stato implementato il rilevamento delle ricerche a pagamento.
* Stai acquisendo i dati del codice di tracciamento.
* Hai codici di monitoraggio univoci per ogni Ad Group.

## Configura [!UICONTROL Success Events]

Il primo passo è preparare  Adobe Analytics a ricevere le metriche. A tal fine, è necessario impostare alcuni eventi di successo.

[!UICONTROL Success events] sono azioni che possono essere tracciate. Si determina cosa [!UICONTROL success event] è. Ai fini del tracciamento delle [!UICONTROL paid search] metriche, desideriamo configurarci [!UICONTROL success events] intorno [!UICONTROL clicks], [!UICONTROL impressions]e [!UICONTROL total cost] attivarle[!UICONTROL tracking codes].

1. Vai a **[!UICONTROL Adobe Analytics > Admin > Report Suites]**.
1. Seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings > Conversion > Success Events]**.

   ![Eventi di successo](assets/success-events.png)

1. In Eventi di successo personalizzati, utilizzate **[!UICONTROL Add New]** per creare 3 eventi di successo personalizzati: [!UICONTROL Clicks] (Contatore), [!UICONTROL Impressions] (Contatore) e [!UICONTROL Total Cost] (Valuta).

   ![Nuovo evento di successo](assets/new-success-events.png)

1. Fai clic su Salva.
Dovreste ricevere un messaggio che informa che i salvataggi sono stati approvati.
1. Passa a **[!UICONTROL Admin > Report Suites > Edit Settings > Conversion > Conversion Variables]**.
1. Per attivare i codici di tracciamento, seleziona la casella di controllo accanto a **[!UICONTROL Tracking Code]** sotto **[!UICONTROL Campaign > Campaign Variable]**.

   ![Variabile campagna](assets/campaign-variable.png)

## Imposta origini dati

[!UICONTROL Data Sources] consente di condividere dati non di clickstream con  Adobe Analytics. In questo caso utilizziamo  Adobe Analytics per monitorare le metriche di ricerca a pagamento. Utilizziamo il codice di tracciamento come chiave per collegare le due parti di dati - metriche di ricerca a pagamento e  metriche Adobe Analytics - insieme.

1. Passa a **[!UICONTROL Adobe Analytics > Admin > Data Sources]**.
1. Selezionare la **[!UICONTROL Create]** scheda per avviare l&#39;attivazione di nuove origini dati.
1. In **[!UICONTROL Select Category]**, selezionare **[!UICONTROL Ad Campaign]**.

   ![Origini dati](assets/data-sources.png)

1. In **[!UICONTROL Select Type]**, selezionare **[!UICONTROL Generic Pay-Per-Click Service]**.
1. Fai clic su **[!UICONTROL Activate]**.
Viene [!UICONTROL Data Source Activation Wizard] visualizzato quanto segue:

   ![Attivazione guidata](assets/ds-activation-wizard.png)

1. Fare clic **[!UICONTROL Next]** e assegnare un nome all&#39;origine dati. Questo nome viene visualizzato in Gestione origine dati.
1. Accettate il contratto di servizio e fate clic su **[!UICONTROL Next]**.
1. Seleziona le tre metriche standard: [!UICONTROL Impressions], [!UICONTROL Clicks] quindi [!UICONTROL Total Cost] fate clic su **[!UICONTROL Next]**.
1. Ora &quot;mappare&quot; questa nuova origine dati sugli eventi personalizzati creati in [Configura eventi](/help/admin/admin/c-success-events/t-success-events.md)di successo.

   ![Mapping](assets/data-source-mapping.png)

1. Scegliete le dimensioni dei dati: selezionate la casella accanto a Codici di tracciamento e fate clic su **[!UICONTROL Next]**.
1. Mappare Dimension di dati.
Mappa la dimensione dati importata (attributo) sull&#39;attributo Adobe Analytics  in cui vuoi memorizzarla. Può trattarsi di una dimensione standard o di un eVar . Dopo aver fatto clic **[!UICONTROL Next]**, le mappature risultanti vengono visualizzate nel riepilogo:

   ![Riepilogo](assets/data-source-summary.png)

1. Fai clic su **[!UICONTROL Save]**.
1. Fare clic **[!UICONTROL Download]** per scaricare il file modello per questa origine dati.
Il nome del file corrisponde al tipo di origine dati inizialmente specificato, in questo caso &quot;Generic Pay-Per-Click Service template.txt&quot;.
1. Aprite il modello nell’editor di testo preferito.
Il file è già popolato con le metriche e le dimensioni e le relative mappature.

## Esportare i dati PPC e caricarli in Analytics

Passaggi simili a questi lavori per Google Adwords, MSN, Yahoo, e altri account PPC.

### Esporta dati

1. Accedi al tuo account PPC e crea un nuovo rapporto o un&#39;esportazione.
Verificate che l’esportazione includa i campi seguenti: data, URL di destinazione (pagina di destinazione), impression, clic e costi. L&#39;esportazione può includere altri campi, ma sarà possibile eliminarli come segue.
1. Se possibile, salvate il rapporto come file delimitato da tabulazioni `.csv` o tabulazioni. In questo modo sarà più semplice lavorare con i seguenti passaggi.
1. Aprite il file in Microsoft Excel.

### Modificare il file in Microsoft Excel

1. In Microsoft Excel, eliminare tutte le colonne diverse da quelle sopra menzionate.
1. Eliminate eventuali righe aggiuntive nella parte superiore.
1. Per isolare i codici di tracciamento dagli URL di destinazione:
a. Copiare e incollare dati da tutte le colonne.
b. Fate clic **[!UICONTROL Data > Text to Columns]**.
c. Nel passaggio 1 della procedura guidata, accertatevi che **[!UICONTROL Delimited]** sia selezionato e fate clic su **[!UICONTROL Next]**.
d. Nel passaggio 2 della procedura guidata, specificate il delimitatore in base alla modalità di creazione degli URL (o ? o &amp;) e fate clic su **[!UICONTROL Next]**.
e. Nel passaggio 3 della procedura guidata, visualizzate in anteprima i dati e accertatevi che una delle colonne sia &quot;trackingcodename=trackingcode&quot;. Se disponete di ulteriori variabili, ripetete questi passaggi (utilizzando &amp; come delimitatore).
f. Elimina tutte le colonne eccetto i codici di tracciamento, le impression, i clic e i costi. Aggiungi una nuova colonna denominata Data e organizza le colonne nel seguente ordine: Data: Codice tracciamento :: Impressioni :: Clic :: Costo.
1. Aggiungi questi dati al modello scaricato nella sezione &quot;Imposta origini dati&quot; sopra.
Ora è possibile caricare il file.

### Caricare il file su  Adobe Analytics tramite FTP

Torna alla procedura guidata Origine dati per ottenere istruzioni e caricare il file tramite FTP:

![Carica FTP](assets/upload-ftp.png)

## Crea metriche calcolate

L&#39;aggiunta di metriche calcolate sarà utile per prendere decisioni pay-per-click.

Ad esempio, puoi aggiungere le metriche [](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=en#calculated-metrics)calcolate seguenti:

| Nome | Formula | Tipi di metriche | Descrizione |
| --- | --- | --- | --- |
| Visualizzazioni pagina per visita | Visualizzazioni/Visite pagina | Numeriche | Se applicata a livello di sito: mostra il numero medio di pagine per visita. Se applicato nel rapporto Pagine più popolari: mostra il numero medio di volte in cui una pagina specifica è stata visualizzata per visita. |
| Valore ordine medio | Entrate/Ordini | Valuta | Visualizza le entrate medie per ordine. |
| Entrate per visita | Entrate/Visita | Valuta | Mostra le entrate medie per visita. |
| Frequenza Click-through (CTR) | Clic/Impressioni | Numeriche | Misura il rapporto tra clic e impression di una campagna di marketing online per annunci pubblicitari o e-mail. |
| Profitto | Ricavi - Costo | Valuta | Mostra i ricavi di una campagna meno il costo. |
| Profitto per impressione (PPI) | (Entrate - Costo)/Impression | Valuta | Mostra quante entrate venivano generate ogni volta che un annuncio veniva visualizzato, bilanciate con i costi. |
| Ritorno sulla spesa pubblicitaria (ROAS) | Importo vendite/spesa annuncio | Valuta | (ROI) Rappresenta i dollari guadagnati per dollari spesi per la pubblicità corrispondente. |

## Configurare ed eseguire i rapporti

Il passo finale è quello di aggiungere le metriche dell&#39;origine dati e tutte le metriche calcolate al report Codice di tracciamento ed eseguire il drill-down in una campagna per ottenere una visualizzazione immediata delle prestazioni di ciascun Ad Group.

1. In **[!UICONTROL Adobe Analytics > Reports]**, seleziona la suite di rapporti in cui hai importato le origini dati.
1. Passa a **[!UICONTROL Reports > Campaigns > Tracking Code > Tracking Code]**.
1. Selezionare l&#39;intervallo di date.
1. Fai clic su **[!UICONTROL Metrics > Add]** e aggiungi le metriche dell&#39;origine dati (clic, Impressioni, Costo totale) dall&#39;elenco Metriche standard.
1. Esegue le stesse operazioni per tutte le metriche calcolate eventualmente aggiunte. Il rapporto viene aggiornato mano a mano che aggiungi metriche.
