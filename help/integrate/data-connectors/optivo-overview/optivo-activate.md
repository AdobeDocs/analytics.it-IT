---
description: Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.
seo-description: Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.
seo-title: Attivare l'integrazione
title: Attivare l'integrazione
uuid: 3 b 2 acdb 8-9 a 1 f -4 f 17-92 f 2-6 a 3780 a 8 f 626
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d10546972c03efae1bc365b7391000a40a79b0a4

---


# Activate the Integration{#activate-the-integration}

Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.

1. Start [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Completate la procedura guidata Integrazione utilizzando le informazioni riportate nella seguente tabella:

| Campo | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti che riceve i dati da questa integrazione. |
| Nome integrazione | Specifica il nome dell'integrazione che Connettori dati visualizza nell'Elenco integrazione attivo della suite di rapporti. |
| Indirizzo e-mail | Fornite un indirizzo e-mail per ricevere informazioni relative all'integrazione. |
| ID account | Questo è l'identificatore univoco assegnato alla tua organizzazione dal provider di servizi e-mail. Verrà utilizzato per la richiesta dei dati della campagna e-mail (ad es. # Sent, # Opened, # Clic, ecc.) from and sending visitor segments to your Email Service Provider. |
| ID destinatario | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema optivo®. Questo "ID destinatario" è associato al comportamento dei visitatori a valle sul sito (carrello, acquisti, ecc.) viene inserito nel sistema optivo® e può essere sfruttato a scopo di remarketing. |
| ID messaggio | (Obbligatorio) Memorizza l'ID della mailing list univoco. These classification dimensions are created by the Data Connectors wizard for the Message ID: a)**Campaigns**: Campaigns associated with the message. b)**Channel**: The channel of transmission, this is constantly "optivo broadmail". c)**Country Code**: This field contains the country code of the origin sender country. È una costante "DE". d) **Delivery Tool**: Method of transmission, always "Email". e) **Message Name**: The name of the mailing, as it is configured in optivo® broadmail. f) **Start Date**: Timestamp of the start of this mailing. |
| Ora clic su post | (Obbligatorio) Questa funzione è necessaria per trasmettere informazioni su un'azione del destinatario all'indirizzo optivo® dopo che il destinatario ha fatto clic su un collegamento in una mailing list. |
| Prodotto post-click | (Obbligatorio) Questa funzione è necessaria per trasmettere informazioni su un'azione del destinatario all'indirizzo optivo® dopo che il destinatario ha fatto clic su un collegamento in una mailing list. |
| Azione post clic | (Obbligatorio) Questa funzione è necessaria per trasmettere informazioni su un'azione del destinatario all'indirizzo optivo® dopo che il destinatario ha fatto clic su un collegamento in una mailing list. |
| Rimbalzi rigidi | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza i dati rigidi importati dall'e-mail. Numero di messaggi e-mail che non sono stati consegnati ai destinatari e considerati non inviabili definitivamente. |
| Bounce leggero | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza i dati di rimbalzo software importati dall'e-mail. Numero di messaggi e-mail che non sono stati consegnati ai destinatari a causa di un problema di consegna. |
| Clic | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza i dati con clic e-mail importati dall'e-mail. L'evento Clic permette di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| Aperto | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza i dati aperti e-mail importati dall'e-mail. L'evento Aperto permette di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. |
| Inviato | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza i dati inviati e-mail importati dall'e-mail. L'evento Inviato permette di visualizzare il numero di messaggi e-mail inviati. |
| Annullato | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza l'e-mail di cancellazione dei dati importati dall'e-mail. L'evento Non iscritto consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail, quindi hanno fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri dall'organizzazione. |
| Segmenti | Abilitare i segmenti esistenti da utilizzare insieme a questa integrazione (facoltativo). |
| Richieste di accesso | Abilitare i privilegi di accesso consigliati. |
| Raccolta dati | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Se selezionate questa opzione, specificate gli identificatori unici utilizzati per questa integrazione:<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l'ID messaggio aggiunto all'URL della pagina di destinazione dal vostro partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l'URL destinatario della pagina di destinazione per l'URL della pagina di destinazione.</li></ul> |
| Dashboard e Generazione segnalibro | Genera automaticamente un dashboard e segnalibri per l'integrazione. |