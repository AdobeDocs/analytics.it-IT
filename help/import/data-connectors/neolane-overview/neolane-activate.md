---
description: Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.
seo-description: Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.
seo-title: Attivare l'integrazione
title: Attivare l'integrazione
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Attivare l'integrazione{#activate-the-integration}

Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.

1. Avviate Connettori [](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) dati e fate clic **[!UICONTROL + Add New]** per [aggiungere una nuova integrazione](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. Nell' **[!UICONTROL Show]** elenco, selezionare **[!UICONTROL By Name]** e trascinare l'integrazione [!DNL ~Partner~] in uno slot plug-in vuoto.
1. Completa la procedura guidata di integrazione utilizzando le informazioni riportate nella tabella seguente:

| Campo | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti che riceve i dati da questa integrazione. |
| Nome integrazione | Specifica il nome dell'integrazione visualizzato dai Connettori dati nell'Elenco integrazione attiva della suite di rapporti. |
| Clic | Numero totale di clic e-mail. |
| ID campagna | Memorizza l'ID univoco del messaggio. Questo viene spesso memorizzato nella variabile della campagna. |
| Aperto | Numero totale di aperture e-mail. |
| Clic sulla persona | Numero di persone che hanno fatto clic. |
| Elaborato | Numero totale di e-mail elaborate. |
| Broadlog ID | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail del sistema Neolane. Questo "Broadlog ID" è associato al comportamento a valle dei visitatori sul sito (cart Broadlog ID abbandoni, acquisti ecc.) che viene inserito nel sistema Neolane e può essere sfruttato per scopi di remarketing. |
| Pianificato | Numero di messaggi e-mail pianificati per la consegna. |
| Inviato | Numero di messaggi e-mail inviati. |
| Totale importi | Numero di messaggi e-mail non inviati ai destinatari a causa di un problema di consegna. |
| Clic univoci | Numero di clic distinti. |
| Aperture univoche | Numero di aperture distinte. |
| Annulla sottoscrizione | Numero di visitatori che hanno aperto il messaggio e-mail e che hanno quindi fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri della vostra organizzazione. |
| Segmenti | Questa integrazione crea i segmenti definiti dal partner visualizzati nella sezione Segmenti partner. Inoltre, puoi selezionare segmenti esistenti a livello di suite di rapporti da includere nell'integrazione. |
|  Richieste di accesso | Abilitate i privilegi di accesso consigliati. |
| Raccolta dati | Selezionate Plug-in **** JavaScript se desiderate utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione. Selezionate **Automated Solution** se desiderate utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specificate gli identificatori univoci utilizzati per questa integrazione. Se selezionate questa opzione, specificate gli identificatori univoci utilizzati per l'integrazione: <ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal partner e-mail.</li></ul> |
| Generazione di dashboard e segnalibri | Genera automaticamente dashboard e segnalibri per l'integrazione. |
