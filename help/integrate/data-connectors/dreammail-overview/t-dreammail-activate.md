---
description: Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.
seo-description: Utilizzate la procedura guidata di configurazione dei connettori dati Adobe per configurare l'integrazione.
seo-title: Attivare l'integrazione
title: Attivare l'integrazione
uuid: 9084 b 691-291 d -49 f 7-9 fa 4-abda 507 e 060 d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a3310ec57ce4c68539f07e0d294c8175742c49dc

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
| UUID Integration | Specificate l'UUID integrazione di dreammail. |
| Nome cliente | Specificate il nome client di dreammail. |
| Nome sito | Specificate il nome del sito dreammail. |
| Back-to Bounce | Numero di messaggi e-mail che non sono stati consegnati ai destinatari a causa di un problema di consegna. |
| Consegnato | Numero di consegne di messaggi completati. |
| Errori di consegna | Distribuzione dei messaggi non riuscita. |
| Aperture HTML | Numero di visitatori che hanno aperto il messaggio e-mail. |
| Invalids | Numero di indirizzi e-mail non validi. |
| Campagna | ID campagna di marketing. |
| Passa altezze | L'evento Clic permette di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| Email eVar | Un indirizzo e-mail dal sistema dreammail. Questa sezione è associata al comportamento dei visitatori a valle del sito (carrello, acquisti, ecc.) viene inserito nel sistema dreammail e può essere sfruttato a scopo di remarketing. |
| Evento spotlight | Evento che può essere esportato nei segmenti di ricommercializzazione. |
| Acquisti faretto | Evento che può essere esportato nei segmenti di ricommercializzazione. |
| Valore faretto | Evento Revenue che può essere esportato nei segmenti di ricommercializzazione. |
| Totalclick | L'evento Clic permette di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| Segmenti | Questa integrazione crea i segmenti definiti dall'partner visualizzati nella sezione Segmenti partner. Inoltre, puoi selezionare i segmenti esistenti a livello di suite di rapporti da includere nell'integrazione. |
| Richieste di accesso | Abilitare i privilegi di accesso consigliati. |
| Raccolta dati | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration (see ). Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Se selezionate questa opzione, specificate gli identificatori unici utilizzati per questa integrazione:<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l'ID messaggio aggiunto all'URL della pagina di destinazione dal partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l'URL destinatario della pagina di destinazione per l'URL della pagina di destinazione.</li></ul> |
| Dashboard e Generazione segnalibro | Genera automaticamente un dashboard e segnalibri per l'integrazione. |