---
description: Utilizzare la Configurazione guidata connettori dati di Adobe per configurare l'integrazione.
title: Attivare l'integrazione
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
exl-id: 520a2b59-5595-4337-b71c-ea0448bf9267
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Attivare l&#39;integrazione {#activate-the-integration}

Utilizzare la Configurazione guidata connettori dati di Adobe per configurare l&#39;integrazione.

1. Avvia [Data Connectors](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html) e fai clic su **[!UICONTROL + Add New]** per [aggiungere una nuova integrazione](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. Nell’elenco **[!UICONTROL Show]**, seleziona **[!UICONTROL By Name]** e trascina l’integrazione [!DNL ~Partner~] in uno slot per plug-in vuoto.
1. Completa l&#39;Integrazione guidata utilizzando le informazioni riportate nella tabella seguente:

| Campo | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti che riceve i dati da questa integrazione. |
| Nome integrazione | Specifica il nome dell&#39;integrazione visualizzato da Data Connectors nell&#39;elenco Integrazione attiva della suite di rapporti. |
| ID account | Specifica l&#39;ID account Aprimo. |
| Recipient ID | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema Aprimo. Questo &quot;ID destinatario&quot; è associato al comportamento dei visitatori a valle sull’ID destinatario del sito (abbandoni del carrello, acquisti, ecc.) che viene inserito nel sistema Aprimo e può essere utilizzato a scopo di remarketing. |
| Clic | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati dell’e-mail selezionati importati dal sistema e-mail. L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| ID messaggio | (Obbligatorio) Memorizza l&#39;ID di spedizione univoco. |
| Aperto | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati di apertura dell’e-mail importati dal sistema e-mail. L’evento Open (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. |
| ID destinatario | (Obbligatorio) Memorizza l&#39;ID visitatore univoco. |
| Inviate | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati inviati per e-mail importati dal sistema e-mail. L’evento Inviato ti consente di visualizzare il numero di messaggi e-mail inviati. |
| Rimbalzi | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati di e-mail Totale rimbalzi importati dal sistema e-mail. L’evento Total-Bounces ti consente di visualizzare il numero di messaggi e-mail che non sono stati recapitati ai destinatari a causa di un problema di consegna. |
| Annulla sottoscrizione | (Obbligatorio) Specifica l’evento Adobe Analytics che memorizza i dati di annullamento dell’abbonamento all’e-mail importati dal sistema e-mail. L’evento Annulla sottoscrizione ti consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail e poi hanno fatto clic sul collegamento Annulla sottoscrizione per rinunciare ai messaggi e-mail futuri della tua organizzazione. |
| Segmenti | Questa integrazione crea i segmenti definiti dai partner visualizzati nella sezione Segmenti partner . Inoltre, puoi selezionare i segmenti esistenti a livello di suite di rapporti da includere nell’integrazione. |
| Richieste di accesso | Abilita i privilegi di accesso consigliati. |
| Raccolta dati | Seleziona **Plug-in JavaScript** se desideri utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione. |
Seleziona **Soluzione automatizzata** se desideri utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specifica gli identificatori univoci utilizzati per questa integrazione. Se selezioni questa opzione, specifica gli identificatori univoci utilizzati per questa integrazione:
<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal tuo partner e-mail.</li>
<li>Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal tuo partner e-mail.</li></ul>|
|Generazione dashboard e segnalibri|Genera automaticamente dashboard e segnalibri per l'integrazione.|
