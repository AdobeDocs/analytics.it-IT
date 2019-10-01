---
description: Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.
seo-description: Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.
seo-title: Attivare l'integrazione
title: Attivare l'integrazione
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Attivare l'integrazione {#activate-the-integration}

Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.

1. Avviate Connettori [](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) dati e fate clic **[!UICONTROL + Add New]** per [aggiungere una nuova integrazione](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. Nell' **[!UICONTROL Show]** elenco, selezionare **[!UICONTROL By Name]** e trascinare l'integrazione [!DNL ~Partner~] in uno slot plug-in vuoto.
1. Completa la procedura guidata di integrazione utilizzando le informazioni riportate nella tabella seguente:

| Campo | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti che riceve i dati da questa integrazione. |
| Nome integrazione | Specifica il nome dell'integrazione visualizzato dai Connettori dati nell'elenco Integrazione attiva della suite di rapporti. |
| ID account | Specificate il vostro ID account Aprimo. |
| ID destinatario | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail del sistema Aprimo. Questo "ID destinatario" è associato al comportamento del visitatore a valle sull’ID destinatario del sito (carrello, acquisti, ecc.) che viene inserito nel sistema Aprimo e può essere sfruttato per scopi di remarketing. |
| Clic | (Obbligatorio) Specificate l'evento Adobe Analytics in cui vengono memorizzati i dati e-mail Click importati dal sistema e-mail. L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| ID messaggio | (Obbligatorio) Memorizza l'ID univoco della posta. |
| Aperto | (Obbligatorio) Specificate l'evento Adobe Analytics in cui sono memorizzati i dati di apertura dell'e-mail importati dal sistema e-mail. L’evento Opened (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. |
| ID destinatario | (Obbligatorio) Memorizza l’ID visitatore univoco. |
| Inviato | (Obbligatorio) Specificate l'evento Adobe Analytics in cui sono memorizzati i dati e-mail inviati importati dal sistema e-mail. L'evento Inviato consente di visualizzare il numero di messaggi e-mail inviati. |
| Bounce | (Obbligatorio) Specificate l'evento Adobe Analytics in cui sono memorizzati i dati e-mail Totale bacheche importati dal sistema e-mail. L'evento Totale rimbalzi consente di visualizzare il numero di messaggi e-mail che non sono stati inviati ai destinatari a causa di un problema di consegna. |
| Annulla sottoscrizione | (Obbligatorio) Specificate l'evento Adobe Analytics che memorizza i dati dell'e-mail Annulla sottoscrizione importati dal sistema e-mail. L’evento Annulla sottoscrizione consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail e hanno quindi fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri della vostra organizzazione. |
| Segmenti | Questa integrazione crea i segmenti definiti dal partner visualizzati nella sezione Segmenti partner. Inoltre, puoi selezionare segmenti esistenti a livello di suite di rapporti da includere nell'integrazione. |
|  Richieste di accesso | Abilitate i privilegi di accesso consigliati. |
| Raccolta dati | Selezionate Plug-in **** JavaScript se desiderate utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione. |
Selezionate **Automated Solution** se desiderate utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specificate gli identificatori univoci utilizzati per questa integrazione. Se selezionate questa opzione, specificate gli identificatori univoci utilizzati per l'integrazione:
<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal partner e-mail.</li>
<li>Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal partner e-mail.</li></ul>||Creazione di dashboard e segnalibri|Generazione automatica di dashboard e segnalibri per l'integrazione.|
