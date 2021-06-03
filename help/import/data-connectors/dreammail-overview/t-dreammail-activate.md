---
description: Utilizzare la Configurazione guidata connettori dati di Adobe per configurare l'integrazione.
title: Attivare l'integrazione
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
exl-id: b0d6849b-975a-4476-a2d3-36abeee12273
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 4%

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
| UUID integrazione | Specifica l&#39;UUID dell&#39;integrazione DreamMail. |
| Nome client | Specifica il nome client DreamMail. |
| Nome del sito | Specifica il nome del sito DreamMail. |
| Rimbalzo | Numero di messaggi e-mail non recapitati ai destinatari a causa di un problema di consegna. |
| Consegnate | Numero di consegne riuscite dei messaggi. |
| Errori di consegna | Consegne di messaggi non riuscite. |
| Aperture HTML | Numero di visitatori che hanno aperto il messaggio e-mail. |
| Invalida | Numero di indirizzi e-mail non validi. |
| Campaign | ID campagna di marketing. |
| Passa Along | L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| Email eVar | Indirizzo e-mail dal sistema DreamMail. Questo &quot;Email eVar&quot; è associato al comportamento dei visitatori a valle sul sito (cart abbandoni, acquisti, ecc.) che viene inserito nel sistema DreamMail e può essere utilizzato a scopo di remarketing. |
| Evento Spotlight | Evento che può essere esportato nei segmenti di remarketing. |
| Acquisti in evidenza | Evento che può essere esportato nei segmenti di remarketing. |
| Valore chiaro | Evento di ricavi che può essere esportato nei segmenti di remarketing. |
| Totale clic | L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| Segmenti | Questa integrazione crea i segmenti definiti dai partner visualizzati nella sezione Segmenti partner . Inoltre, puoi selezionare i segmenti esistenti a livello di suite di rapporti da includere nell’integrazione. |
| Richieste di accesso | Abilita i privilegi di accesso consigliati. |
| Raccolta dati | Seleziona **Plug-in JavaScript** se desideri utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione (vedi ). Seleziona **Soluzione automatizzata** se desideri utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specifica gli identificatori univoci utilizzati per questa integrazione. Se selezioni questa opzione, specifica gli identificatori univoci utilizzati per questa integrazione:<ul><li>Parametro stringa query ID messaggio: Questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal tuo partner e-mail.</li><li>Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal tuo partner e-mail.</li></ul> |
| Generazione dashboard e segnalibro | Genera automaticamente dashboard e segnalibri per l’integrazione. |
