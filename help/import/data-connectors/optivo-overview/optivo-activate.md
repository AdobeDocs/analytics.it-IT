---
description: Utilizzare la Configurazione guidata connettori dati di Adobe per configurare l'integrazione.
title: Attivare l'integrazione
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
exl-id: 18fb2f55-f1fb-4d97-bd1e-8c5e74dbde69
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 2%

---

# Attivare l&#39;integrazione{#activate-the-integration}

Utilizzare la Configurazione guidata connettori dati di Adobe per configurare l&#39;integrazione.

1. Avvia [Data Connectors](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html) e fai clic su **[!UICONTROL + Add New]** per [aggiungere una nuova integrazione](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. Nell’elenco **[!UICONTROL Show]**, seleziona **[!UICONTROL By Name]** e trascina l’integrazione [!DNL ~Partner~] in uno slot per plug-in vuoto.
1. Completa l&#39;Integrazione guidata utilizzando le informazioni riportate nella tabella seguente:

| Campo | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti che riceve i dati da questa integrazione. |
| Nome integrazione | Specifica il nome dell&#39;integrazione visualizzato da Data Connectors nell&#39;elenco Integrazione attiva della suite di rapporti. |
| Indirizzo e-mail | Fornisci un indirizzo e-mail per ricevere informazioni relative all’integrazione. |
| ID account | Questo è l’identificatore univoco assegnato alla tua organizzazione dal provider di servizi e-mail. Sarà utilizzato per richiedere i dati delle campagne e-mail (ad es. # Inviato, # Aperto, # Clic, ecc.) da e invio di segmenti di visitatori al provider di servizi e-mail. |
| Recipient ID | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema optivo® broadmail. Questo &quot;ID destinatario&quot; è associato al comportamento dei visitatori a valle sul sito (abbandoni il carrello, acquisti, ecc.) che viene inserito nel sistema optivo® broadmail e può essere utilizzato a scopo di remarketing. |
| ID messaggio | (Obbligatorio) Memorizza l&#39;ID di spedizione univoco. Queste dimensioni di classificazione vengono create dalla procedura guidata Connettori dati per l’ID messaggio: <br>a)**Campagne**: Campagne associate al messaggio. <br>b)**Canale**: Il canale di trasmissione, questo è costantemente &quot;optivo broadmail&quot;. <br>c)**Codice del paese**: Questo campo contiene il codice del paese del paese del mittente di origine. È una costante &quot;DE&quot;. <br>d) Strumento  **di consegna**: Metodo di trasmissione, sempre &quot;Email&quot;.<br> e)  **Nome** messaggio: Nome della mailing, come configurato in optivo® broadmail. <br>f) Data  **di inizio**: Timestamp dell&#39;inizio della spedizione. |
| Ora clic post | (Obbligatorio) Questo è necessario per trasmettere informazioni su un&#39;azione del destinatario a optivo® broadmail dopo che il destinatario ha fatto clic su un collegamento in un messaggio. |
| Prodotto post-clic | (Obbligatorio) Questo è necessario per trasmettere informazioni su un&#39;azione del destinatario a optivo® broadmail dopo che il destinatario ha fatto clic su un collegamento in un messaggio. |
| Azione post-clic | (Obbligatorio) Questo è necessario per trasmettere informazioni su un&#39;azione del destinatario a optivo® broadmail dopo che il destinatario ha fatto clic su un collegamento in un messaggio. |
| Rimbalzo duro | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati dei messaggi non recapitati rigidi importati dal sistema e-mail. Numero di messaggi e-mail che non sono stati recapitati ai destinatari e che sono considerati definitivamente non recapitati. |
| Rimbalzo morbido | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati dei messaggi non recapitati non recapitati scaricati dal sistema e-mail. Numero di messaggi e-mail non recapitati ai destinatari a causa di un problema di consegna. |
| Clic | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati dell’e-mail su cui è stato fatto clic importati dal sistema e-mail. L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| Aperto | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati aperti dell’e-mail importati dal sistema e-mail. L’evento Open (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. |
| Inviate | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati e-mail inviati importati dal sistema e-mail. L’evento Inviato ti consente di visualizzare il numero di messaggi e-mail inviati. |
| Annulla sottoscrizione | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati di annullamento dell’abbonamento all’e-mail importati dal sistema e-mail. L’evento Annulla sottoscrizione ti consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail e poi hanno fatto clic sul collegamento Annulla sottoscrizione per rinunciare ai messaggi e-mail futuri della tua organizzazione. |
| Segmenti | Abilita l’utilizzo di segmenti esistenti insieme a questa integrazione (facoltativo). |
| Richieste di accesso | Abilita i privilegi di accesso consigliati. |
| Raccolta dati | Seleziona **Plug-in JavaScript** se desideri utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione. Seleziona **Soluzione automatizzata** se desideri utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specifica gli identificatori univoci utilizzati per questa integrazione. Se selezioni questa opzione, specifica gli identificatori univoci utilizzati per questa integrazione:<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal tuo partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal tuo partner e-mail.</li></ul> |
| Generazione dashboard e segnalibro | Genera automaticamente dashboard e segnalibri per l’integrazione. |
