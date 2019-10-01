---
description: Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.
seo-description: Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.
seo-title: Attivare l'integrazione
title: Attivare l'integrazione
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Attivare l'integrazione{#activate-the-integration}

Utilizzare la Configurazione guidata Connettori dati di Adobe per configurare l'integrazione.

1. Avviate Connettori [](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) dati e fate clic **[!UICONTROL + Add New]** per [aggiungere una nuova integrazione](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. Nell' **[!UICONTROL Show]** elenco, selezionare **[!UICONTROL By Name]** e trascinare l'integrazione [!DNL ~Partner~] in uno slot plug-in vuoto.
1. Completa la procedura guidata di integrazione utilizzando le informazioni riportate nella tabella seguente:

| Campo | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti che riceve i dati da questa integrazione. |
| Nome integrazione | Specifica il nome dell'integrazione visualizzato dai Connettori dati nell'elenco Integrazione attiva della suite di rapporti. |
| UUID integrazione | Specificate l'UUID integrazione DreamMail. |
| Nome client | Specificate il nome client DreamMail. |
| Nome sito | Specificate il nome del sito DreamMail. |
| Rimbalzi | Numero di messaggi e-mail non inviati ai destinatari a causa di un problema di consegna. |
| Consegnato | Numero di invii di messaggi riusciti. |
| Errori di consegna | Distribuzione di messaggi non riuscita. |
| Aperture HTML | Numero di visitatori che hanno aperto il messaggio e-mail. |
| Invalidi | Numero di indirizzi e-mail non validi. |
| Campagna | ID campagna marketing. |
| Along Pass | L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| Email eVar | Un indirizzo e-mail dal sistema DreamMail. Questa eVar e-mail è associata al comportamento dei visitatori a valle sul sito (carrelli abbandonati, acquisti, ecc.) che viene inserito nel sistema DreamMail e può essere utilizzato a scopo di remarketing. |
| Evento Spotlight | Evento che può essere esportato nei segmenti di remarketing. |
| Acquisti Spotlight | Evento che può essere esportato nei segmenti di remarketing. |
| Valore Spotlight | Evento Revenue che può essere esportato nei segmenti di ricommercializzazione. |
| TotaleClic | L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| Segmenti | Questa integrazione crea i segmenti definiti dal partner visualizzati nella sezione Segmenti partner. Inoltre, puoi selezionare segmenti esistenti a livello di suite di rapporti da includere nell'integrazione. |
|  Richieste di accesso | Abilitate i privilegi di accesso consigliati. |
| Raccolta dati | Selezionate Plug-in **** JavaScript se desiderate utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione (vedete ). Selezionate **Automated Solution** se desiderate utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specificate gli identificatori univoci utilizzati per questa integrazione. Se selezionate questa opzione, specificate gli identificatori univoci utilizzati per l'integrazione:<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal partner e-mail.</li></ul> |
| Generazione di dashboard e segnalibri | Genera automaticamente dashboard e segnalibri per l'integrazione. |