---
description: Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.
title: Attivare l'integrazione
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Attivare l&#39;integrazione {#activate-the-integration}

Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l&#39;integrazione.

1. Avviate Connettori [](https://docs.adobe.com/content/help/en/analytics/import/dataconnectors/getting-started-data-connectors.html) dati e fate clic **[!UICONTROL + Add New]** per [aggiungere una nuova integrazione](https://docs.adobe.com/content/help/en/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. Nell&#39; **[!UICONTROL Show]** elenco, selezionare **[!UICONTROL By Name]** e trascinare l&#39;integrazione [!DNL ~Partner~] in uno slot plug-in vuoto.
1. Completa la procedura guidata di integrazione utilizzando le informazioni riportate nella tabella seguente:

| Campo | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti che riceve i dati da questa integrazione. |
| Nome integrazione | Specifica il nome dell&#39;integrazione visualizzato dai Connettori dati nell&#39;Elenco integrazione attiva della suite di rapporti. |
| ID account | Specificate il vostro ID account Aprimo. |
| Recipient ID | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail del sistema Aprimo. Questo &quot;ID destinatario&quot; è associato al comportamento del visitatore a valle sull’ID destinatario del sito (abbandono del carrello, acquisti, ecc.) che viene inserito nel sistema Aprimo e può essere sfruttato per scopi di remarketing. |
| Clic | (Obbligatorio) Specificate l&#39;evento Adobe Analytics in cui sono memorizzati i dati del clic del messaggio e-mail importati dal sistema e-mail. L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| ID messaggio | (Obbligatorio) Memorizza l&#39;ID univoco della posta. |
| Aperto | (Obbligatorio) Specificate l&#39;evento Adobe Analytics in cui sono memorizzati i dati di apertura dell&#39;e-mail importati dal sistema e-mail. L’evento Opened (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. |
| Recipient ID | (Obbligatorio) Memorizza l’ID visitatore univoco. |
| Inviato | (Obbligatorio) Specificate l&#39;evento Adobe Analytics in cui sono memorizzati i dati e-mail inviati importati dal sistema e-mail. L&#39;evento Inviato consente di visualizzare il numero di messaggi e-mail inviati. |
| Rimbalzi | (Obbligatorio) Specificate l&#39;evento Adobe Analytics in cui sono memorizzati i dati e-mail Totale bacheche importati dal sistema e-mail. L&#39;evento Totale rimbalzi consente di visualizzare il numero di messaggi e-mail che non sono stati inviati ai destinatari a causa di un problema di consegna. |
| Annulla sottoscrizione | (Obbligatorio) Specificate l&#39;evento Adobe Analytics che memorizza i dati dell&#39;e-mail Annulla sottoscrizione importati dal sistema e-mail. L’evento Annulla sottoscrizione consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail e hanno quindi fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri della vostra organizzazione. |
| Segmenti | Questa integrazione crea i segmenti definiti dal partner visualizzati nella sezione Segmenti partner. Inoltre, puoi selezionare segmenti esistenti a livello di suite di rapporti da includere nell&#39;integrazione. |
| Richieste di accesso | Abilitate i privilegi di accesso consigliati. |
| Raccolta dati | Selezionate Plug-in **** JavaScript se desiderate utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione. |
Selezionate **Automated Solution** se desiderate utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specificate gli identificatori univoci utilizzati per questa integrazione. Se selezionate questa opzione, specificate gli identificatori univoci utilizzati per l&#39;integrazione:
<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal partner e-mail.</li>
<li>Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal partner e-mail.</li></ul>||Creazione di dashboard e segnalibri|Generazione automatica di dashboard e segnalibri per l'integrazione.|
