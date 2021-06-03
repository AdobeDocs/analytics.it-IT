---
description: Utilizzare la Configurazione guidata connettori dati di Adobe per configurare l'integrazione.
title: Attivare l'integrazione
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
exl-id: d36c26ad-09c4-4a4d-a653-670c18f2ab19
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 5%

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
| Clic | Numero totale di clic e-mail. |
| ID campagna | Memorizza l&#39;ID univoco del messaggio. Questa viene spesso memorizzata nella variabile della campagna. |
| Aperto | Numero totale di aperture e-mail. |
| Clic su persona | Numero di persone che hanno cliccato. |
| Elaborato | Numero totale di e-mail elaborate. |
| Broadlog ID | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema Neolane. Questo &quot;Broadlog ID&quot; è associato al comportamento dei visitatori a valle sul sito (cart Broadlog ID abbandoni, acquisti, ecc.) che viene inserito nel sistema Neolane e può essere utilizzato a scopo di remarketing. |
| Pianificato | Numero di messaggi e-mail pianificati per la consegna. |
| Inviate | Numero di messaggi e-mail inviati. |
| Rimbalzi totali | Numero di messaggi e-mail non recapitati ai destinatari a causa di un problema di consegna. |
| Clic univoci | Numero di clic distinti. |
| Aperture univoche | Numero di aperture distinte. |
| Annulla sottoscrizione | Numero di visitatori che hanno aperto il messaggio e-mail e poi hanno fatto clic sul collegamento Annulla sottoscrizione per rinunciare ai messaggi e-mail futuri della tua organizzazione. |
| Segmenti | Questa integrazione crea i segmenti definiti dai partner visualizzati nella sezione Segmenti partner . Inoltre, puoi selezionare i segmenti esistenti a livello di suite di rapporti da includere nell’integrazione. |
| Richieste di accesso | Abilita i privilegi di accesso consigliati. |
| Raccolta dati | Seleziona **Plug-in JavaScript** se desideri utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione. Seleziona **Soluzione automatizzata** se desideri utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specifica gli identificatori univoci utilizzati per questa integrazione. Se selezioni questa opzione, specifica gli identificatori univoci utilizzati per questa integrazione: <ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal tuo partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal tuo partner e-mail.</li></ul> |
| Generazione dashboard e segnalibro | Genera automaticamente dashboard e segnalibri per l’integrazione. |
