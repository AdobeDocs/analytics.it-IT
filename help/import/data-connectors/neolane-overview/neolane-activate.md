---
description: Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.
seo-description: Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.
seo-title: Attivare l'integrazione
title: Attivare l'integrazione
uuid: 93 c 59 f 8 e -3 cf 5-44 c 1-9 a 04-22460 af 93 d 5 d
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
| Clic | Numero totale di clic e-mail. |
| ID campagna | Memorizza l'ID del messaggio univoco. Spesso viene memorizzato nella variabile della campagna. |
| Aperto | Viene aperto il numero totale di messaggi e-mail. |
| Clic su persona | Numero di persone che hanno fatto clic su |
| Elaborato | Numero totale delle e-mail elaborate. |
| Broadlog ID | Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema Neolane. Questo «ID Broadlog» è associato al comportamento dei visitatori a valle sul sito (ID broadlog sul carrello, acquisti, ecc.) viene inserito nel sistema Neolane e può essere sfruttato a scopo di remarketing. |
| Pianificato | Numero di messaggi e-mail pianificati per la consegna. |
| Inviato | Numero di messaggi e-mail inviati. |
| Totale bounce | Numero di messaggi e-mail che non sono stati consegnati ai destinatari a causa di un problema di consegna. |
| Clic univoci | Numero di clic distinti. |
| Aperture univoche | Numero di aperture distinte. |
| Annullato | Numero di visitatori che hanno aperto il messaggio e-mail, quindi hanno fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri dall'organizzazione. |
| Segmenti | Questa integrazione crea i segmenti definiti dall'partner visualizzati nella sezione Segmenti partner. Inoltre, puoi selezionare i segmenti esistenti a livello di suite di rapporti da includere nell'integrazione. |
| Richieste di accesso | Abilitare i privilegi di accesso consigliati. |
| Raccolta dati | Selezionate **Plug-in javascript** se desiderate utilizzare il plug-in s_ code. js come modello di raccolta per questa integrazione. Selezionate **Soluzione automatizzata** se desiderate utilizzare un modello di raccolta automatizzato per questa integrazione, quindi specificate gli identificatori unici utilizzati per tale integrazione. Se selezionate questa opzione, specificate gli identificatori unici utilizzati per questa integrazione: <ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l'ID messaggio aggiunto all'URL della pagina di destinazione dal partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l'URL destinatario della pagina di destinazione per l'URL della pagina di destinazione.</li></ul> |
| Dashboard e Generazione segnalibro | Genera automaticamente un dashboard e segnalibri per l'integrazione. |