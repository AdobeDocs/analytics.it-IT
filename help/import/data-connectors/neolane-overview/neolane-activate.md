---
description: Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.
seo-description: Use the Adobe Data Connectors Configuration Wizard to set up the integration.
seo-title: Activate the Integration
title: Activate the Integration
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
translation-type: tm+mt
source-git-commit: 34b18e7769e0850283fd3840c2557818d5d742f0

---


# Activate the Integration{#activate-the-integration}

Use the Adobe Data Connectors Configuration Wizard to set up the integration.

1. Start Data Connectors and click  to add a new integration.[](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html)**[!UICONTROL + Add New]**[](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html)
1. In the  list, select  and drag the Partner integration to an empty plug-in slot.**[!UICONTROL Show]****[!UICONTROL By Name]**[!DNL ~~]
1. Complete the Integration Wizard using the information in the following table:

| Campo | Descrizione |
|--- |--- |
| Suite di rapporti | The report suite that receives the data from this integration. |
| Nome integrazione | Specifica il nome dell'integrazione visualizzato dai Connettori dati nell'elenco Integrazione attiva della suite di rapporti. |
| Clicked | Total number of email clicks. |
| Campaign ID | Memorizza l'ID univoco del messaggio. This is often stored in the campaign variable. |
| Aperto | Numero totale di aperture e-mail. |
| Person Clicks | Numero di persone che hanno fatto clic. |
| Elaborato | Numero totale di e-mail elaborate. |
| Broadlog ID | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail del sistema Neolane. Questo "Broadlog ID" è associato al comportamento a valle dei visitatori sul sito (cart Broadlog ID abbandoni, acquisti ecc.) che viene inserito nel sistema Neolane e può essere sfruttato per scopi di remarketing. |
| Pianificato | Numero di messaggi e-mail pianificati per la consegna. |
| Inviato | Numero di messaggi e-mail inviati. |
| Totale importi | Numero di messaggi e-mail non inviati ai destinatari a causa di un problema di consegna. |
| Clic univoci | Numero di clic distinti. |
| Aperture univoche | Number of distinct opens. |
| Annulla sottoscrizione | Numero di visitatori che hanno aperto il messaggio e-mail e che hanno quindi fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri della vostra organizzazione. |
| Segmenti | Questa integrazione crea i segmenti definiti dal partner visualizzati nella sezione Segmenti partner. Inoltre, puoi selezionare segmenti esistenti a livello di suite di rapporti da includere nell'integrazione. |
|  Richieste di accesso | Abilitate i privilegi di accesso consigliati. |
| Raccolta dati | Selezionate Plug-in **** JavaScript se desiderate utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione. Selezionate **Automated Solution** se desiderate utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specificate gli identificatori univoci utilizzati per questa integrazione. Se selezionate questa opzione, specificate gli identificatori univoci utilizzati per l'integrazione: <ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal partner e-mail.</li></ul> |
| Dashboard and Bookmark Generation | Automatically generate a dashboard and bookmarks for the integration. |
