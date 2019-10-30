---
description: nulle
seo-description: nulle
seo-title: Implementazione dell'integrazione
solution: Analytics
title: Implementazione dell'integrazione
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Implementazione dell'integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice che consiste nel completare la procedura guidata di integrazione Adobe e verificare l'integrazione.

## Completamento della procedura guidata di integrazione di Adobe{#completing-the-adobe-integration-wizard}

Procedura per completare la procedura guidata di integrazione nell'interfaccia Connettori dati.

1. Passa all'area Connettori dati (precedentemente Genesis) in Adobe Experience Cloud.
1. Avviate la procedura guidata di integrazione del segnale dinamico.
1. Scegliete la suite di rapporti desiderata e specificate un nome per l'integrazione.
1. Configura i seguenti elementi:

   | Elemento | Descrizione |
   |---|---|
   | Indirizzo e-mail | Indirizzo e-mail del contatto principale. |
   | Descrizione | (Facoltativo) Descrizione per questa configurazione di integrazione. |
   | ID community | Puoi ottenere questo ID dal rappresentante del segnale dinamico. |

1. Configurate i seguenti **[!UICONTROL Variable Mappings]** elementi:

   | Elemento | Descrizione |
   |---|---|
   | Codice di tracciamento | Seleziona una variabile eVar disponibile dalla suite di rapporti. |

1. Esaminate le classificazioni che verranno create per questa integrazione.
1. Selezionare la casella per creare il dashboard di integrazione del segnale dinamico (facoltativo, ma altamente consigliato).
1. Rivedete tutti gli elementi di configurazione e fate clic su **[!UICONTROL Activate Now]**.
1. **Importante**: Una volta completata la procedura guidata, devi inviare una notifica al rappresentante del segnale dinamico in modo che possa attivare l'integrazione sulla piattaforma VoiceStorm.

## Verifica dell'integrazione{#verifying-the-integration}

Passaggi per visualizzare la configurazione dell’integrazione VoiceStorm del segnale dinamico in Adobe Experience Cloud

1. Visualizza la configurazione dell'integrazione del segnale dinamico nel registro delle attività di integrazione.
   1. In Adobe Experience Cloud, passa a **[!UICONTROL Support]** &gt; **[!UICONTROL Integration Activity Log]** .

      ![](assets/integration_activity_log.png)

   1. Cerca voci come **[!UICONTROL Classification Data imported successfully]**. Queste voci devono essere visualizzate entro 24 ore dalla distribuzione completata.
1. Rivedete i rapporti del segnale dinamico all'interno di Adobe Analytics utilizzando il dashboard creato automaticamente tramite la procedura guidata di integrazione Adobe (passaggio 7). In alternativa, puoi passare al reporting del segnale dinamico all'interno della struttura del menu di Adobe Analytics. Fai riferimento alle seguenti schermate.

   **Nota**:Questi dati devono essere visualizzati entro 24-48 ore dalla distribuzione completata.

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
