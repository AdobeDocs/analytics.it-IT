---
description: Distribuisci il connettore dati Dynamic Signal da utilizzare in Adobe Analytics.
title: Distribuzione dell'integrazione
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 6%

---


# Distribuzione dell&#39;integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice che consiste nel completare l&#39;Integrazione guidata di Adobe e verificare l&#39;integrazione.

## Completamento dell&#39;integrazione guidata Adobe{#completing-the-adobe-integration-wizard}

Passaggi per completare l&#39;integrazione guidata nell&#39;interfaccia Data Connectors.

1. Passa all’area Data Connectors (precedentemente Genesis) all’interno di Adobe Experience Cloud.
1. Avvia la procedura guidata di integrazione del segnale dinamico.
1. Scegli la suite di rapporti desiderata e specifica un nome per l’integrazione.
1. Configura i seguenti elementi:

   | Elemento | Descrizione |
   |---|---|
   | Indirizzo e-mail | Indirizzo e-mail del contatto principale. |
   | Descrizione | (Facoltativo) Descrizione per questa configurazione di integrazione. |
   | ID community | Puoi ottenere questo ID dal tuo rappresentante di Dynamic Signal. |

1. Configura i seguenti elementi **[!UICONTROL Variable Mappings]**:

   | Elemento | Descrizione |
   |---|---|
   | Codice di tracciamento | Seleziona una variabile eVar disponibile dalla suite di rapporti. |

1. Esamina le classificazioni che verranno create per questa integrazione.
1. Seleziona la casella per creare il dashboard di integrazione del segnale dinamico (opzionale, ma altamente consigliato).
1. Rivedi tutti gli elementi di configurazione e fai clic su **[!UICONTROL Activate Now]**.
1. **Importante**: Una volta completata la procedura guidata, devi informare il rappresentante del segnale dinamico in modo che possa attivare l&#39;integrazione sulla piattaforma VoiceStorm.

## Verifica dell&#39;integrazione{#verifying-the-integration}

Passaggi per visualizzare la configurazione dell&#39;integrazione Dynamic Signal VoiceStorm in Adobe Experience Cloud

1. Visualizza la configurazione dell’integrazione del segnale dinamico nel registro delle attività di integrazione.
   1. In Adobe Experience Cloud, passa a **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]** .

      ![](assets/integration_activity_log.png)

   1. Cerca voci come **[!UICONTROL Classification Data imported successfully]**. Queste voci devono essere visualizzate entro 24 ore dalla distribuzione riuscita.
1. Controlla i rapporti del segnale dinamico in Adobe Analytics utilizzando il dashboard creato automaticamente utilizzando la procedura guidata di integrazione dell’Adobe (passaggio 7). In alternativa, puoi passare al reporting del segnale dinamico all’interno della struttura del menu di Adobe Analytics - fai riferimento alle seguenti schermate.

   **Nota**: Questi dati devono essere visualizzati entro 24-48 ore dalla distribuzione riuscita.

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
