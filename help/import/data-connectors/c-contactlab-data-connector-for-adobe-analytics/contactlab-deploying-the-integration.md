---
description: nulle
seo-description: nulle
seo-title: Implementazione dell'integrazione
solution: Analytics
title: Implementazione dell'integrazione
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# Implementazione dell'integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice che richiede le seguenti azioni:

## Completa la procedura guidata di integrazione di Adobe{#completing-the-adobe-integration-wizard}

Procedura per completare la procedura guidata di integrazione nell'interfaccia Connettori dati.

1. Passa all'area Connettori dati (precedentemente Genesis) in Adobe Experience Cloud.
1. Avviate la procedura guidata di integrazione di ContactLab.
1. Scegliete la suite di rapporti desiderata e specificate un nome per l'integrazione.
1. Configura i seguenti elementi:

   | Elemento | Descrizione |
   |---|---|
   | Indirizzo e-mail | Indirizzo e-mail del contatto principale |
   | Descrizione | (Facoltativo) Descrizione per questa configurazione di integrazione |

1. Configurate i seguenti **[!UICONTROL Variable Mappings]** elementi:

   | Elemento | Descrizione |
   |---|---|
   | Collegamento ID | Seleziona un'eVar per raccogliere gli ID collegamento in tempo reale. |
   | ID messaggio | Seleziona un'eVar per raccogliere gli ID messaggio in tempo reale. |
   | Recipient ID | Seleziona un'eVar per raccogliere gli ID dei destinatari in tempo reale. |
   | Bounce | Selezionare un evento numerico per ricevere rimbalzi giornalieri da ContactLab. |
   | Inviato | Selezionare un evento numerico per ricevere le invii giornalieri da ContactLab. |
   | Clic | Selezionare un evento numerico per ricevere i clic totali giornalieri da ContactLab. |
   | Aperto | Selezionare un evento numerico per ricevere il totale giornaliero si apre da ContactLab. |
   | Annulla sottoscrizione | Selezionare un evento numerico per ricevere gli annullamenti giornalieri da ContactLab. |

1. Abilita l'accesso ai dati e configura la raccolta dati.
   1. Rinominare le classificazioni in base alle esigenze.
   1. **[!UICONTROL Partner segments]** sono segmenti di remarketing standard inclusi nell’integrazione.
   1. In **[!UICONTROL Your Segments]**, seleziona i segmenti personalizzati che desideri includere in questa integrazione. Puoi creare altri segmenti personalizzati nel pannello di amministrazione.
   1. In **[!UICONTROL Access Requests]** questa casella di controllo è possibile esportare le informazioni sui prodotti in ContactLab nei segmenti di remarketing giornalieri.
   1. Rinominare le metriche calcolate come necessario.
   1. Configura se raccogliere gli ID aggiornando manualmente il codice di raccolta di Analytics o utilizzando la soluzione automatizzata. Se selezionate **[!UICONTROL Automated Solution]**, dovete includere i parametri utilizzati nei collegamenti e-mail per trasmettere gli ID.
1. Rivedete tutti gli elementi di configurazione e fate clic su **[!UICONTROL Activate Now]**.

## Verificare l'integrazione{#verifying-the-integration}

Visualizza la configurazione dell’integrazione con ContactLab in Adobe Experience Cloud

1. Visualizzare il registro delle attività di integrazione.
   1. In Adobe Experience Cloud, passa a **[!UICONTROL Support]** &gt; **[!UICONTROL Integration Activity Log]**.

      ![](assets/integration_activity_log.png)

   1. Cerca voci come **[!UICONTROL Classification Data imported successfully]**, **[!UICONTROL Metrics Data imported successfully]**, e **[!UICONTROL Metric Data exported successfully]**. Queste voci devono essere visualizzate entro 1 giorno dalla distribuzione completata.
1. Visualizza i tuoi dati di reporting in Adobe Analytics.
   1. Passa a **[!UICONTROL Custom Conversion]** &gt; **[!UICONTROL Custom Conversion 1-10]** &gt; **[!UICONTROL Message ID Reports]**.

      ![](assets/reporting.png)

   1. Cercate i rapporti di ContactLab. Questi dati devono essere visualizzati entro 24-48 ore dalla distribuzione completata.
