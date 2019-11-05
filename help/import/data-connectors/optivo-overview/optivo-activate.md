---
description: Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.
seo-description: Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.
seo-title: Attivare l'integrazione
title: Attivare l'integrazione
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

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
| Indirizzo e-mail | Fornite un indirizzo e-mail per ricevere le informazioni relative all'integrazione. |
| ID account | Questo è l’identificatore univoco assegnato all’organizzazione dal provider di servizi e-mail. Sarà utilizzato per richiedere i dati delle campagne e-mail (ad es. # Inviato, # Aperto, # Clic, ecc.) da e inviando segmenti di visitatori al provider di servizi e-mail. |
| Recipient ID | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema di trasmissione di Reader®. Questo "ID destinatario" è associato al comportamento a valle dei visitatori sul sito (carrelli abbandonati, acquisti, ecc.) che viene inserito nel sistema di distribuzione del prodotto opzionale® e può essere sfruttato per scopi di remarketing. |
| ID messaggio | (Obbligatorio) Memorizza l'ID univoco della posta. Queste dimensioni di classificazione vengono create dalla procedura guidata Connettori dati per l'ID messaggio: <br>a)**Campagne**: Campagne associate al messaggio. <br>b)**Canale**: Il canale di trasmissione, questo è costantemente "optivo broadcast". <br>c)Codice **** del paese: Questo campo contiene il codice del paese del paese mittente di origine. È una costante "DE". <br>d) **Strumento** di consegna: Metodo di trasmissione, sempre "Email".<br> e) Nome **** messaggio: Il nome della mailing, così come è configurato in optivo® broadcast. <br>f) Data **di** inizio: Timestamp dell'inizio della spedizione. |
| Ora clic post | (Obbligatorio) Questa opzione è necessaria per trasmettere informazioni su un'azione del destinatario a un servizio di trasmissione optivo® dopo che il destinatario ha fatto clic su un collegamento in un messaggio. |
| Post Click Product | (Obbligatorio) Questa opzione è necessaria per trasmettere informazioni su un'azione del destinatario a un servizio di trasmissione optivo® dopo che il destinatario ha fatto clic su un collegamento in un messaggio. |
| Azione Post Click | (Obbligatorio) Questa opzione è necessaria per trasmettere informazioni su un'azione del destinatario a un servizio di trasmissione optivo® dopo che il destinatario ha fatto clic su un collegamento in un messaggio. |
| Rimbalzo duro | (Obbligatorio) Specifica l'evento Adobe Analytics in cui sono memorizzati i dati dei rimbalzi fissi importati dal sistema e-mail. Numero di messaggi e-mail che non sono stati inviati ai destinatari e che sono considerati definitivamente non consegnabili. |
| Rimbalzo morbido | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza i dati relativi ai rimbalzi software importati dal sistema e-mail. Numero di messaggi e-mail non inviati ai destinatari a causa di un problema di consegna. |
| Clic | (Obbligatorio) Specifica l'evento Adobe Analytics in cui sono memorizzati i dati del clic del messaggio e-mail importati dal sistema e-mail. L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| Aperto | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza i dati dell'e-mail aperta importati dal sistema e-mail. L’evento Opened (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. |
| Inviato | (Obbligatorio) Specificate l'evento Adobe Analytics in cui vengono memorizzati i dati e-mail inviati importati dal sistema e-mail. L'evento Inviato consente di visualizzare il numero di messaggi e-mail inviati. |
| Annulla sottoscrizione | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza i dati di annullamento della sottoscrizione dell'e-mail importati dal sistema e-mail. L’evento Annulla sottoscrizione consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail e hanno quindi fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri della vostra organizzazione. |
| Segmenti | Consente l'utilizzo di segmenti esistenti con questa integrazione (facoltativo). |
|  Richieste di accesso | Abilitate i privilegi di accesso consigliati. |
| Raccolta dati | Selezionate Plug-in **** JavaScript se desiderate utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione. Selezionate **Automated Solution** se desiderate utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specificate gli identificatori univoci utilizzati per questa integrazione. Se selezionate questa opzione, specificate gli identificatori univoci utilizzati per l'integrazione:<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal partner e-mail.</li></ul> |
| Generazione di dashboard e segnalibri | Genera automaticamente dashboard e segnalibri per l'integrazione. |
