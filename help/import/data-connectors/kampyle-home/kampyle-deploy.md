---
description: Implementa il connettore dati Kampyle in Adobe Analytics.
title: Distribuzione dell'integrazione
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
exl-id: ac8e1f30-cefe-448a-bec6-cda58ee51025
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 1%

---

# Distribuzione dell&#39;integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice che consiste nel completare l&#39;Integrazione guidata di Adobe, distribuire il codice plug-in (JavaScript) e verificare l&#39;integrazione.

## Completa l&#39;Integrazione guidata Adobe{#complete-the-adobe-integration-wizard}

Per attivare l&#39;integrazione, completa la procedura guidata di configurazione nell&#39;interfaccia Data Connectors.

1. Accedi a Adobe Experience Cloud.
1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data connectors]**.
1. Avvia la procedura guidata di integrazione di Kampyle.
1. Seleziona la suite di rapporti desiderata e specifica un nome per l’integrazione.
1. Configura i seguenti elementi:
   1. **[!UICONTROL Email address]**: Indirizzo e-mail del contatto principale.
   1. **[!UICONTROL Description]** (facoltativo): Descrizione della configurazione dell&#39;integrazione.
   1. **[!UICONTROL Kampyle Key]**: Trova questa chiave nell&#39;applicazione Kampyle in  **[!UICONTROL Feedback Form]** >  **[!UICONTROL Feedback Form Customization]**.
   1. **[!UICONTROL Tracking Server]**: Il valore del server di tracciamento utilizzato per tenere traccia dei dati di Adobe Analytics.
   1. **[!UICONTROL Tracking Server Secure]**: Se il server di tracciamento è diverso per il traffico protetto/https, specifica questa impostazione qui.
1. Configura i seguenti elementi **[!UICONTROL Variable Mappings]**:
   1. **[!UICONTROL Kampyle Feedback ID]**: Seleziona una variabile eVar disponibile dalla suite di rapporti
   1. **[!UICONTROL Feedback Grade]**: Seleziona un evento di successo disponibile (digita &quot;contatore&quot;) dalla suite di rapporti.
   1. **[!UICONTROL Feedback Items]**: Seleziona un evento di successo disponibile (digita &quot;contatore&quot;) dalla suite di rapporti.
   1. **[!UICONTROL Feedback with Grade]**: Seleziona un evento di successo disponibile (digita &quot;contatore&quot;) dalla suite di rapporti.
1. Seleziona la casella per creare automaticamente il dashboard Integrazione Kampyle (consigliato).
1. Rivedi tutti gli elementi di configurazione e fai clic su **[!UICONTROL Activate Now]**.

## Distribuire l&#39;oggetto di configurazione dell&#39;integrazione{#deploy-the-integration-configuration-object}

Dopo aver completato l&#39;integrazione guidata, implementa l&#39;oggetto di configurazione dell&#39;integrazione nella proprietà Web. In molti casi, il modo più semplice per implementare l&#39;oggetto di configurazione dell&#39;integrazione è includerlo con il codice di distribuzione Adobe Analytics.

>[!NOTE]
>
>Se utilizzi Adobe Experience Platform Launch, puoi facilmente aggiungere l’oggetto di configurazione dell’integrazione tramite tale strumento.

1. Passa alla scheda **[!UICONTROL Resources]** > **[!UICONTROL Support]** dell’integrazione.
1. Scarica e salva la risorsa **[!UICONTROL Kampyle Integration Code (JS)]** . Il codice è simile al seguente:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Distribuisci il codice utilizzando uno dei seguenti metodi:

   * Utilizza Adobe Experience Platform Launch.
   * Distribuisci il codice alla risorsa organizzativa che gestisce la distribuzione Adobe Analytics.

## Verifica l&#39;integrazione{#verify-the-integration}

Verifica che l’integrazione trasferisca correttamente i dati completando un paio di controlli.

### Registro delle attività di integrazione {#section-0472df9180db4f218db5f6040cab07af}

Visualizza la configurazione dell&#39;integrazione Kampyle all&#39;interno di Adobe Experience Cloud passando a **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]**. Nella scheda **[!UICONTROL Data In]** , dovresti vedere le voci che indicano che i dati di classificazione sono stati importati correttamente.

>[!NOTE]
>
>Le voci di registro vengono generalmente visualizzate entro 24 ore dalla distribuzione riuscita.

![Registro delle attività di integrazione](assets/integration_activity_log.png)

### Adobe di dati di reporting {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Per visualizzare i rapporti di feedback di Kampyle con Adobe Analytics, passa al reporting di Kampyle all&#39;interno della struttura di menu appropriata.

>[!NOTE]
>
>I dati di reporting devono essere visualizzati entro 24-48 ore dall’invio, partendo dal presupposto che i moduli di feedback integrati ricevano attivamente gli invii.

![Adobe di dati di reporting](assets/adobe_reporting_data.png)
