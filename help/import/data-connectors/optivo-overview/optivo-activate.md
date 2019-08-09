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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Attivare l'integrazione{#activate-the-integration}

Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.

1. Avviate [Connettori dati](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) e fate clic per **[!UICONTROL + Add New]**[aggiungere una nuova integrazione](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. Nell **[!UICONTROL Show]** 'elenco, seleziona **[!UICONTROL By Name]** e trascina l'integrazione [!DNL ~Partner~] in uno slot plug-in vuoto.
1. Completate la procedura guidata Integrazione utilizzando le informazioni riportate nella seguente tabella:

| Campo | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti che riceve i dati da questa integrazione. |
| Nome integrazione | Specifica il nome dell'integrazione che Connettori dati visualizza nell'Elenco integrazione attivo della suite di rapporti. |
| Indirizzo e-mail | Fornite un indirizzo e-mail per ricevere informazioni relative all'integrazione. |
| ID account | Questo è l'identificatore univoco assegnato alla tua organizzazione dal provider di servizi e-mail. Verrà utilizzato per la richiesta dei dati della campagna e-mail (ad es. # Sent, # Opened, # Clic, ecc.) from and sending visitor segments to your Email Service Provider. |
| ID destinatario | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema optivo®. Questo "ID destinatario" è associato al comportamento dei visitatori a valle sul sito (carrello, acquisti, ecc.) viene inserito nel sistema optivo® e può essere sfruttato a scopo di remarketing. |
| ID messaggio | (Obbligatorio) Memorizza l'ID della mailing list univoco. Queste dimensioni di classificazione vengono create dalla procedura guidata Connettori dati per l'ID messaggio: a)**Campagne**: Campagne associate al messaggio. b)**Canale**: The channel of transmission, this is constantly "optivo broadmail". c)**Codice paese**: Questo campo contiene il codice paese del paese del mittente di origine. È una costante "DE". d) **Strumento Consegna**: Metodo di trasmissione, sempre "Email". e) **Nome messaggio**: Nome della mailing list, che è configurato in optivo®. f) **Data di inizio**: Marca temporale dell'inizio della mailing list. |
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
| Raccolta dati | Selezionate **Plug-in javascript** se desiderate utilizzare il plug-in s_ code. js come modello di raccolta per questa integrazione. Selezionate **Soluzione automatizzata** se desiderate utilizzare un modello di raccolta automatizzato per questa integrazione, quindi specificate gli identificatori unici utilizzati per tale integrazione. Se selezionate questa opzione, specificate gli identificatori unici utilizzati per questa integrazione:<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l'ID messaggio aggiunto all'URL della pagina di destinazione dal vostro partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l'URL destinatario della pagina di destinazione per l'URL della pagina di destinazione.</li></ul> |
| Dashboard e Generazione segnalibro | Genera automaticamente un dashboard e segnalibri per l'integrazione. |