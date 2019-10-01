---
description: nulle
seo-description: nulle
seo-title: Implementazione dell'integrazione
solution: Analytics
title: Implementazione dell'integrazione
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: 34b18e7769e0850283fd3840c2557818d5d742f0

---


# Implementazione dell'integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice, che consiste nel completare la procedura guidata di integrazione Adobe, distribuire il codice del plug-in (javascript) e verificare l'integrazione.

## Completa la procedura guidata di integrazione di Adobe{#complete-the-adobe-integration-wizard}

Per attivare l'integrazione, è necessario completare la procedura guidata di configurazione all'interno dell'interfaccia Connettori dati.

1. Accedi ad Adobe Experience Cloud.
1. Andate a **[!UICONTROL Data Connectors]** (già Genesis).
1. Avviate la procedura guidata di integrazione di Kampyle.
1. Selezionate la suite di rapporti desiderata e specificate un nome per l'integrazione.
1. Configura i seguenti elementi:

   1. **[!UICONTROL Email address]** - l'indirizzo e-mail del contatto principale.
   1. **[!UICONTROL Description]** - (facoltativo) descrizione di questa configurazione dell'integrazione.
   1. **[!UICONTROL Kampyle Key]** - Trovate questa chiave nell'applicazione Kampyle in **[!UICONTROL Feedback Form]** &gt; **[!UICONTROL Feedback Form Customization]**.
   1. **[!UICONTROL Tracking Server]** - l'impostazione del server di tracciamento (dominio) che utilizzate per tenere traccia dei dati di Adobe Analytics.
   1. **[!UICONTROL Tracking Server Secure]** - se il server di tracciamento è diverso per il traffico protetto/https, specifica questa impostazione.
1. Configurate i seguenti **[!UICONTROL Variable Mappings]** elementi:

   1. **[!UICONTROL Kampyle Feedback ID]** -Selezionate una variabile eVar disponibile dalla suite di rapporti
   1. **[!UICONTROL Feedback Grade]** - Selezionate un evento di successo disponibile (digitate "contatore") dalla suite di rapporti.
   1. **[!UICONTROL Feedback Items]** - Selezionate un evento di successo disponibile (digitate "contatore") dalla suite di rapporti.
   1. **[!UICONTROL Feedback with Grade]** - Selezionate un evento di successo disponibile (digitate "contatore") dalla suite di rapporti.
1. Selezionare la casella per creare automaticamente il dashboard Integrazione Kampyle (consigliato).
1. Rivedete tutti gli elementi di configurazione e fate clic su **[!UICONTROL Activate Now]**.

## Distribuzione dell'oggetto di configurazione dell'integrazione{#deploy-the-integration-configuration-object}

Dopo aver completato la procedura guidata di integrazione, è necessario distribuire l'oggetto di configurazione dell'integrazione nella proprietà Web.

In molti casi, il modo più semplice per distribuire l'oggetto di configurazione dell'integrazione consiste nell'includerlo nel codice di distribuzione di Adobe Analytics.

>[!NOTE]
>
>Se utilizzate Adobe TagManager o Gestione tag dinamica per distribuire Adobe Analytics, potete aggiungere facilmente l'oggetto di configurazione dell'integrazione tramite tale strumento.

1. Passate alla scheda **[!UICONTROL Resources]** &gt; **[!UICONTROL Support]** dell'integrazione.
1. Scaricate e salvate la **[!UICONTROL Kampyle Integration Code (JS)]** risorsa. Il codice è simile al seguente:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Distribuite il codice utilizzando uno dei seguenti metodi:

   | **Puoi usare Adobe TagManager o Gestione tag dinamica.** | Utilizzate l'interfaccia di gestione tag per aggiungere il codice. |
   |---|---|
   | **In tutti gli altri casi** | Consegnate il codice alla risorsa organizzativa incaricata di aggiornare il codice di distribuzione di Adobe Analytics. |

## Verificare l'integrazione{#verify-the-integration}

Verificare che l'integrazione trasferisca correttamente i dati completando un paio di controlli.

### Registro attività integrazione {#section-0472df9180db4f218db5f6040cab07af}

Visualizza la configurazione dell’integrazione di Kampyle in Adobe Experience Cloud accedendo a **[!UICONTROL Support]** &gt; **[!UICONTROL Integration Activity Log]**. Nella **[!UICONTROL Data In]** scheda, è possibile visualizzare le voci che indicano che i dati di classificazione sono stati importati correttamente.

>[!NOTE]
>
>Le voci di registro devono essere visualizzate entro 24 ore dalla distribuzione completata.

![](assets/integration_activity_log.png)

### Dati di Adobe Reporting {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Visualizzare i rapporti di feedback di Kampyle con Adobe Analytics andando alla generazione di rapporti di Kampyle all'interno della struttura di menu appropriata.

>[!NOTE]
>
>I dati di reporting devono essere visualizzati entro 24-48 ore dalla distribuzione riuscita, partendo dal presupposto che i moduli di feedback integrati ricevano attivamente gli invii.

![](assets/adobe_reporting_data.png)

