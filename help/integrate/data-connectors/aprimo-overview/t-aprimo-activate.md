---
description: Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.
seo-description: Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.
seo-title: Attivare l'integrazione
title: Attivare l'integrazione
uuid: 0 a 5 d 2 d 45-5133-4259-96 ce-c 992 a 1 e 314 ee
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a3310ec57ce4c68539f07e0d294c8175742c49dc

---


# Activate the Integration {#activate-the-integration}

Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.

1. Start [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Completate la procedura guidata Integrazione utilizzando le informazioni riportate nella seguente tabella:

| Campo | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti che riceve i dati da questa integrazione. |
| Nome integrazione | Specifica il nome dell'integrazione che Connettori dati visualizza nell'Elenco integrazione attivo della suite di rapporti. |
| ID account | Specificate il vostro ID account Openmo. |
| ID destinatario | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema Openmo. Questo "ID destinatario" è associato al comportamento dei visitatori a valle sull'ID destinatario del sito (carrello abbandonati, acquisti ecc.) viene inserito nel sistema introduttivo e può essere sfruttato a scopo di remarketing. |
| Clic | (Obbligatorio) Specificate l'evento Adobe Analytics che archivia i dati e-mail importati importati dall'e-mail. L'evento Clic permette di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| ID messaggio | (Obbligatorio) Memorizza l'ID della mailing list univoco. |
| Aperto | (Obbligatorio) Specificate l'evento Adobe Analytics che archivia l'e-mail di dati aperti dall'e-mail. L'evento Aperto permette di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. |
| ID destinatario | (Obbligatorio) Memorizza l'ID visitatore univoco. |
| Inviato | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza l'e-mail di invio dei dati inviati dall'e-mail. L'evento Inviato permette di visualizzare il numero di messaggi e-mail inviati. |
| Non recapitate | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza l'e-mail Total Bounences data importata dall'e-mail. L'evento Rimbalzi totali permette di visualizzare il numero di messaggi e-mail che non sono stati consegnati ai destinatari a causa di un problema di consegna. |
| Annullato | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza l'e-mail e annulla l'iscrizione dei dati importati dall'e-mail. L'evento Non iscritto consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail, quindi hanno fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri dall'organizzazione. |
| Segmenti | Questa integrazione crea i segmenti definiti dall'partner visualizzati nella sezione Segmenti partner. Inoltre, puoi selezionare i segmenti esistenti a livello di suite di rapporti da includere nell'integrazione. |
| Richieste di accesso | Abilitare i privilegi di accesso consigliati. |
| Raccolta dati | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. |
Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Se selezionate questa opzione, specificate gli identificatori unici utilizzati per questa integrazione:
<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l'ID messaggio aggiunto all'URL della pagina di destinazione dal partner e-mail.</li>
<li>Parametro stringa query ID destinatario: Questo valore rappresenta l'URL destinatario della pagina di destinazione per l'URL della pagina di destinazione.</li></ul>|
| Dashboard e Generazione segnalibro | Genera automaticamente un dashboard e segnalibri per l'integrazione.|
