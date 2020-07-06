---
description: 'null'
title: Distribuzione dell'integrazione
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 2%

---


# Distribuzione dell&#39;integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice, che consiste nel completare la procedura guidata di integrazione Adobe, distribuire il codice plug-in (JavaScript) e verificare l&#39;integrazione.

## Completa la procedura guidata di integrazione di Adobe{#complete-the-adobe-integration-wizard}

Per attivare l&#39;integrazione, completare la procedura guidata di configurazione nell&#39;interfaccia Connettori dati.

1. Accedi ad Adobe Experience Cloud.
1. Passa a **[!UICONTROL Data Connectors]**.
1. Avviate la procedura guidata di integrazione di Kampyle.
1. Selezionate la suite di rapporti desiderata e specificate un nome per l&#39;integrazione.
1. Configurate i seguenti elementi:
   1. **[!UICONTROL Email address]**: L&#39;indirizzo e-mail del contatto principale.
   1. **[!UICONTROL Description]** (facoltativo): Descrizione per questa configurazione di integrazione.
   1. **[!UICONTROL Kampyle Key]**: Trova questa chiave nell’applicazione Kampyle in **[!UICONTROL Feedback Form]** > **[!UICONTROL Feedback Form Customization]**.
   1. **[!UICONTROL Tracking Server]**: Il valore del server di tracciamento utilizzato per tenere traccia dei dati di Adobe  Analytics.
   1. **[!UICONTROL Tracking Server Secure]**: Se il server di tracciamento è diverso per il traffico protetto/https, specifica questa impostazione.
1. Configurate i seguenti **[!UICONTROL Variable Mappings]** elementi:
   1. **[!UICONTROL Kampyle Feedback ID]**: Seleziona una variabile eVar disponibile dalla suite di rapporti
   1. **[!UICONTROL Feedback Grade]**: Seleziona un evento di successo disponibile (tipo &quot;contatore&quot;) dalla suite di rapporti.
   1. **[!UICONTROL Feedback Items]**: Seleziona un evento di successo disponibile (tipo &quot;contatore&quot;) dalla suite di rapporti.
   1. **[!UICONTROL Feedback with Grade]**: Seleziona un evento di successo disponibile (tipo &quot;contatore&quot;) dalla suite di rapporti.
1. Selezionare la casella per creare automaticamente il dashboard Integrazione Kampyle (consigliato).
1. Rivedete tutti gli elementi di configurazione e fate clic su **[!UICONTROL Activate Now]**.

## Implementare l&#39;oggetto di configurazione dell&#39;integrazione{#deploy-the-integration-configuration-object}

Dopo aver completato la procedura guidata di integrazione, distribuite l&#39;oggetto di configurazione dell&#39;integrazione nella proprietà Web. In molti casi, il modo più semplice per distribuire l&#39;oggetto di configurazione dell&#39;integrazione consiste nell&#39;includerlo nel codice di distribuzione Analytics  Adobe.

>[!NOTE]
>
>Se si utilizza  Adobe Experience Platform Launch, è possibile aggiungere facilmente l&#39;oggetto di configurazione dell&#39;integrazione tramite tale strumento.

1. Passate alla scheda **[!UICONTROL Resources]** > **[!UICONTROL Support]** dell&#39;integrazione.
1. Scaricate e salvate la **[!UICONTROL Kampyle Integration Code (JS)]** risorsa. Il codice è simile al seguente:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Distribuite il codice utilizzando uno dei seguenti metodi:

   * Utilizzate  lancio Adobe Experience Platform.
   * Consegnate il codice alla risorsa organizzativa che gestisce la distribuzione di Adobe  Analytics.

## Verificare l&#39;integrazione{#verify-the-integration}

Verificare che l&#39;integrazione trasferisca correttamente i dati completando un paio di controlli.

### Registro attività integrazione {#section-0472df9180db4f218db5f6040cab07af}

Visualizza la configurazione dell’integrazione di Kampyle in Adobe Experience Cloud accedendo a **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]**. Nella **[!UICONTROL Data In]** scheda, è possibile visualizzare le voci che indicano che i dati di classificazione sono stati importati correttamente.

>[!NOTE]
>
>Le voci di registro vengono visualizzate in genere entro 24 ore dalla distribuzione completata.

![Registro attività integrazione](assets/integration_activity_log.png)

### Dati di Adobe Reporting {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Visualizzate i rapporti di feedback di Kampyle con Adobe  Analytics accedendo al reporting di Kampyle nella struttura di menu appropriata.

>[!NOTE]
>
>I dati di reporting devono essere visualizzati entro 24-48 ore dalla distribuzione riuscita, partendo dal presupposto che i moduli di feedback integrati ricevano attivamente gli invii.

![Dati di reporting Adobe](assets/adobe_reporting_data.png)
