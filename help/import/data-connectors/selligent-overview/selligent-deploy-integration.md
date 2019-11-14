---
description: L'implementazione di questa integrazione è un semplice processo in 3 fasi.
solution: Analytics
title: Implementazione dell'integrazione
uuid: c578bf26-34c2-44ea-8e60-2990273f8659
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Implementazione dell'integrazione{#deploying-the-integration}

L'implementazione di questa integrazione è un semplice processo in 3 fasi.

## Completamento dell'Integrazione guidata{#completing-the-integration-wizard}

Per attivare l'integrazione, è necessario completare la procedura guidata di integrazione intelligente nell'interfaccia Connettori dati.

1. Passa all'area Connettori dati in Adobe Experience Cloud.

   ![](assets/selligent-data_connectors.png)

1. In **[!UICONTROL Add Integrations]** questa sezione, trascina e rilascia il plug-in Selligent in Adobe Experience Cloud.

   ![](assets/selligent-add_integration.png)

   Viene aperta l'integrazione del connettore dati intelligente.

1. **Impostazioni** integrazione: Scegliete la suite di rapporti desiderata e specificate un nome per l'integrazione in **[!UICONTROL Integration Settings]**.

1. In **[!UICONTROL Custom Values]**, compila tutte le informazioni relative all’account Selligent.

   ![](assets/selligent-general_settings.png)

1. **Mappatura** variabile: Scegliete le eVar ed eventi riservati appropriate dal menu a discesa:

   ![](assets/selligent-variables.png)

1. **Impostazioni** dati: Puoi scegliere i tuoi segmenti **[!UICONTROL Your Segments]** oltre ai 3 **[!UICONTROL Partner]** segmenti automatizzati.

1. Questa integrazione potrebbe richiedere il download di alcuni punti dati nell'account Selligent. È possibile scegliere di concedere l'accesso per lo stesso in **[!UICONTROL Access Request]**.
1. In **[!UICONTROL Data Collection]**, scegliete una soluzione automatica o manuale (plug-in JavaScript) per raccogliere i parametri delle stringhe di query dall’URL della pagina di destinazione. Se scegli una soluzione automatizzata, immetti il parametro della stringa di query per ID messaggio e ID destinatario, rispettivamente MID e RID. Per il plug-in JavaScript, contattate il vostro consulente Adobe.
1. **Impostazioni** report: In **[!UICONTROL Dashboard Generation]** questa casella selezionare la casella per generare automaticamente il dashboard Selligent.

   ![](assets/selligent-report_settings.png)

1. Rivedete il riepilogo dell'integrazione e fate clic su **[!UICONTROL Activate]**.

## Configurazione all'interno del segmento{#configuration-within-selligent}

Non appena l'integrazione viene abilitata in Adobe Analytics, sul lato del client viene attivata una configurazione automatica.

È stato creato un tracciatore che terrà traccia di ogni e-mail. Se desiderate limitarlo a un determinato dominio, aggiornate la configurazione del tracciatore.

È consigliabile spostare il parametro di tracciamento per Adobe Analytics nell’URL in primo piano. In questo modo le regole di elaborazione Adobe recupereranno i parametri dall’URL della pagina di destinazione. Attivate il tracciamento selezionando la casella di controllo come illustrato di seguito.

![](assets/selligent-tracker.png)

## Verifica dell'integrazione{#verifying-the-integration}

Una volta completati tutti i passaggi di distribuzione, puoi verificare che l'integrazione trasferisca correttamente i dati.

Ci vorranno alcuni giorni prima che inizi lo scambio di dati. Dopo aver attivato l'integrazione, contattate l'amministratore.

### Registro attività integrazione {#section-927e270495db479fba9578915d9ae9c9}

Passa all'integrazione dei segmenti all'interno dei connettori dati. Nella **[!UICONTROL Support]** scheda è possibile visualizzare eventi come Dati metriche importati e/o Dati di classificazione importati correttamente:

![](assets/selligent-verifying.png)

### Dati di reporting {#section-ebd481a162324e66bd6dc8cb4b8d2424}

Visualizzare i rapporti sui messaggi inviati con le metriche appropriate.

1. Vai a Reporting e analisi in Adobe Experience Cloud.
1. Selezionate la suite di rapporti appropriata.
1. In **[!UICONTROL Custom Conversion]**, selezionate il **[!UICONTROL Message ID Reports]** pulsante e scegliete **[!UICONTROL Message ID/Message Name]**.
