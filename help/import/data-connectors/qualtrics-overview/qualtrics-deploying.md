---
description: La distribuzione di questa integrazione è un processo semplice che richiede le seguenti azioni.
solution: Analytics
subtopic: Qualtrics
title: Implementazione dell'integrazione
topic: Data connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Implementazione dell'integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice che richiede le seguenti azioni.

## Completamento della procedura guidata di integrazione di Adobe{#completing-the-adobe-integration-wizard}

Per attivare l'integrazione è necessario completare l'integrazione guidata Qualtrics all'interno dell'interfaccia Connettori dati

1. Passate ai connettori dati e avviate la procedura guidata di integrazione Qualtrics.
1. Selezionate la suite di rapporti da utilizzare per l'integrazione e specificate un nome.

   Completate la procedura guidata di integrazione, fornendo le informazioni descritte nella procedura seguente. 1. Passaggio **procedura guidata 1**

   | Email Address | L'indirizzo e-mail del contatto principale. |
   |---|---|
   | Descrizione | (Facoltativo) Descrizione per questa configurazione di integrazione. |
   | ID organizzazione Qualtrics | [Ricerca del tuo ID organizzazione per la qualità](../qualtrics-overview/qualtrics-org-id.md) |
   | Token di Adobe SiteCatalyst | [Generazione del token Adobe Analytics Qualtrics](../qualtrics-overview/qualtrics-token.md) |

1. **Procedura guidata Passaggio 2 - Mappature** variabili| Elenco di risposte rapide| Selezionate una variabile di elenco disponibile dalla suite di rapporti. (potrebbe essere necessario abilitare una nuova listVar in Report Suite Manager.)  ||—|—|| ID risposta rapida| Selezionate un'eVar o una prop disponibile dalla suite di rapporti. (potrebbe essere necessario abilitare una nuova listVar in Report Suite Manager.)  || Server di monitoraggio|Fornire l'impostazione del server di tracciamento (dominio) utilizzata per tenere traccia dei dati di Adobe Analytics. Usa il server di `trackingServerSecure` tracciamento se è diverso dall’impostazione standard del server di tracciamento.  || Invii sondaggio per qualtrics| Selezionate un evento disponibile dalla suite di rapporti (potrebbe essere necessario abilitare un nuovo evento dall'interno di Report Suite Manager).  |

1. **Passaggio procedura guidata 3**: Non è richiesto nulla, solo informazioni.

   Passaggio 1. **Procedura guidata Passaggio 4 - Impostazioni di esportazione**

   | eVar | Seleziona fino a cinque delle tue eVar da esporre per l'esportazione in formato Qualtrics |
   |---|---|
   | Eventi | Seleziona fino a cinque eventi personalizzati da esporre per l'esportazione in modalità Qualtrics |
   | Proprietà | Seleziona fino a cinque delle tue Prop da esporre per l'esportazione in Qualtrics |
   | Richieste di accesso | Selezionate la casella di controllo per le metriche e le dimensioni standard da esportare in metriche. L’ `visitor_id` opzione è necessaria per consentire il corretto funzionamento dell’esportazione. |

1. **Passaggio procedura guidata 5**: Rivedete la configurazione e fate clic **[!UICONTROL Activate Now]**.

## Abilitazione dell'integrazione in Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

Dopo aver completato la procedura guidata di integrazione, è necessario attivare l’integrazione per ogni sondaggio Qualtrics da connettere.

1. Accedete alla Suite Qualtrics Research.
1. Nella **[!UICONTROL My Surveys]** scheda, fate clic sul **[!UICONTROL Edit]** pulsante relativo al sondaggio da integrare.
1. Fare clic sul **[!UICONTROL Advanced Options]** menu e selezionare **[!UICONTROL Adobe Analytics]**. (in caso contrario, chiedete all’amministratore di ottenere le autorizzazioni necessarie).

   ![](assets/advanced_options.png)

1. Selezionate Configurazione Adobe Analytics, quindi fate clic su **[!UICONTROL Save]**. Se non sono disponibili configurazioni, è probabile che non sia ancora stata completata l'Integrazione guidata Adobe.
   1. La **[!UICONTROL Include Partial Responses]** casella di controllo può essere utilizzata per indicare che si desidera acquisire dati in Adobe Analytics dopo che ciascuna schermata di sondaggio parziale è stata completata. Se non è selezionato, i dati vengono trasferiti solo per le indagini completate.
   1. La **[!UICONTROL Send Timestamp With Beacon]** casella di controllo deve essere utilizzata solo per l'integrazione con una suite di rapporti configurata per la ricezione di dati con marca temporale (non comune).
   ![](assets/integration_config.png)

## Verifica dell'integrazione{#verifying-the-integration}

Una volta completati tutti i passaggi di distribuzione, puoi verificare che l'integrazione trasferisca correttamente i dati.

1. **Registro** attività integrazione: Nell’interfaccia utente Connettori dati, visualizzare la **[!UICONTROL Support]** scheda sull’integrazione Qualtrics. Sotto l'intestazione **[!UICONTROL Integration Activity Log]** dovrebbero essere visualizzate le voci che indicano l'esito positivo dei dati di classificazione importati.

   >[!NOTE]
   >
   >Queste voci devono essere visualizzate entro 1 ora dalla distribuzione completata.

   ![](assets/verify-1.png)

1. **Dati** di reporting: Puoi visualizzare i tuoi rapporti sui sondaggi di qualità con i rapporti di marketing e l’interfaccia utente di analisi navigando nella sezione Reporting dei sondaggi (in **[!UICONTROL List Variables]**).

   >[!NOTE]
   >
   >Questi dati dovrebbero essere visualizzati entro 24-48 ore dalla distribuzione di successo, partendo dal presupposto che il sondaggio integrato riceva attivamente risposte.

   ![](assets/verify-2.png) ![](assets/verify-3.png)


