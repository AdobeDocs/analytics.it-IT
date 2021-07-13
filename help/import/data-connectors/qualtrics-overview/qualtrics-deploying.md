---
description: La distribuzione di questa integrazione è un processo semplice che richiede le seguenti azioni.
subtopic: Qualtrics
title: Distribuzione dell'integrazione
feature: Data Connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
exl-id: 8637f13d-a07e-412e-9ad7-8a0836301dd6
source-git-commit: 85d199e71fb65e9026156b146201da2e5be37111
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 6%

---

# Distribuzione dell&#39;integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice che richiede le seguenti azioni.

## Completamento dell&#39;integrazione guidata Adobe{#completing-the-adobe-integration-wizard}

Per attivare l’integrazione è necessario completare la procedura guidata di integrazione Qualtrics all’interno dell’interfaccia Data Connectors

1. Passa ai connettori dati e avvia la procedura guidata di integrazione Qualtrics.
1. Seleziona la suite di rapporti che desideri utilizzare per questa integrazione e specifica un nome.

   Completa la procedura guidata di integrazione, fornendo le informazioni descritte nei passaggi seguenti. 1. **Procedura guidata Passaggio 1**

   | Email Address | Indirizzo e-mail del contatto principale. |
   |---|---|
   | Descrizione | (Facoltativo) Descrizione per questa configurazione di integrazione. |
   | ID organizzazione Qualtrics | [Ricerca dell&#39;ID organizzazione Qualtrics](../qualtrics-overview/qualtrics-org-id.md) |
   | Token Adobe SiteCatalyst | [Generazione del token Adobe Analytics Qualtrics](../qualtrics-overview/qualtrics-token.md) |

1. **Procedura guidata 2 - Mappature variabili**

   | Elenco risposte rapide | Seleziona una variabile di elenco disponibile dalla suite di rapporti. (Potrebbe essere necessario abilitare una nuova listVar in Report Suite Manager.) |
   |---|---|
   | ID risposta Qualtrics | Seleziona un eVar o un prop disponibile dalla suite di rapporti. (Potrebbe essere necessario abilitare una nuova listVar in Report Suite Manager.) |
   | Tracking Server | Specifica l’impostazione del server di tracciamento (dominio) che utilizzi per tenere traccia dei dati di Adobe Analytics. Utilizza il server di tracciamento `trackingServerSecure` se è diverso dalle impostazioni del server di tracciamento standard. |
   | Invii sondaggio Qualtrics | Seleziona un evento disponibile dalla suite di rapporti (potrebbe essere necessario abilitare un nuovo evento da Report Suite Manager). |

1. **Procedura guidata 3**: Non è necessario nulla, solo informativo.

   Passaggio 1: **Procedura guidata 4 - Impostazioni di esportazione**

   | eVar | Seleziona fino a cinque eVar da esporre per l’esportazione in Qualtrics |
   |---|---|
   | Eventi | Seleziona fino a cinque eventi personalizzati da esporre per l’esportazione in Qualtrics |
   | Proprietà | Seleziona fino a cinque proprietà da esporre per l&#39;esportazione in Qualtrics |
   | Richieste di accesso | Seleziona la casella per le metriche e le dimensioni standard da esportare in Qualtrics. Per consentire il corretto funzionamento dell’esportazione, è necessario `visitor_id` . |

1. **Procedura guidata 5**: Rivedi la configurazione e fai clic su  **[!UICONTROL Activate Now]**.

## Abilitazione dell’integrazione in Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

Dopo aver completato l’integrazione guidata, è necessario attivare l’integrazione per ogni sondaggio Qualtrics che si desidera connettere.

1. Accedi alla Qualtrics Research Suite.
1. Nella scheda **[!UICONTROL My Surveys]** , fai clic sul pulsante **[!UICONTROL Edit]** per il sondaggio da integrare.
1. Fai clic sul menu **[!UICONTROL Advanced Options]** e seleziona **[!UICONTROL Adobe Analytics]**. (in caso contrario, chiedi all’amministratore di ottenere le autorizzazioni necessarie).

   ![](assets/advanced_options.png)

1. Seleziona la configurazione Adobe Analytics, quindi fai clic su **[!UICONTROL Save]**. Se non sono disponibili configurazioni, è probabile che non si sia ancora completato l&#39;Integrazione guidata Adobe.
   1. La casella di controllo **[!UICONTROL Include Partial Responses]** può essere utilizzata per indicare che desideri acquisire dati in Adobe Analytics al termine di ogni schermata di sondaggio parziale. Se non è selezionato, i dati vengono trasferiti solo per i sondaggi completamente completati.
   1. La casella di controllo **[!UICONTROL Send Timestamp With Beacon]** deve essere utilizzata solo quando si esegue l’integrazione con una suite di rapporti configurata per la ricezione di dati con marca temporale (non comune).

   ![](assets/integration_config.png)

## Verifica dell&#39;integrazione{#verifying-the-integration}

Una volta completati tutti i passaggi di distribuzione, puoi verificare che l’integrazione trasferisca correttamente i dati.

1. **Registro** delle attività di integrazione: Nell’interfaccia utente dei Data Connectors, puoi visualizzare la  **[!UICONTROL Support]** scheda relativa all’integrazione Qualtrics . Sotto l’intestazione **[!UICONTROL Integration Activity Log]** dovresti trovare le voci che indicano che i dati di classificazione sono stati importati correttamente.

   >[!NOTE]
   >
   >Queste voci devono essere visualizzate entro 1 ora dalla distribuzione corretta.

   ![](assets/verify-1.png)

1. **Dati** di reporting: Puoi visualizzare i rapporti dei sondaggi Qualtrics con l’interfaccia utente marketing reports and analytics navigando nel rapporto dei sondaggi Qualtrics (in  **[!UICONTROL List Variables]**).

   >[!NOTE]
   >
   >Questi dati devono essere visualizzati entro 24-48 ore dal successo della distribuzione, partendo dal presupposto che il sondaggio integrato riceva attivamente risposte.

   ![](assets/verify-2.png) ![](assets/verify-3.png)
