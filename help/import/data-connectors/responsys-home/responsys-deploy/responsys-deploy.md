---
description: Distribuisci il connettore dati Responsys da utilizzare in Adobe Analytics.
title: Distribuzione dell'integrazione
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 4%

---


# Distribuzione dell&#39;integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice che richiede le seguenti azioni:

## Completamento dell&#39;integrazione guidata Adobe{#completing-the-adobe-integration-wizard}

Passaggi per completare l&#39;integrazione guidata nell&#39;interfaccia Data Connectors.

1. Passa all’area Data Connectors (precedentemente Genesis) all’interno di Adobe Experience Cloud.
1. Avvia la procedura guidata di integrazione di Responsys.
1. Scegli la suite di rapporti desiderata e specifica un nome per l’integrazione.
1. Configura i seguenti elementi:

   | Elemento | Descrizione |
   |---|---|
   | Indirizzo e-mail | Indirizzo e-mail del contatto principale |
   | Descrizione | (Facoltativo) Descrizione per questa configurazione di integrazione |
   | ID account | Ottenuto contattando il team di supporto Responsys all&#39;indirizzo support@responsys.com |

1. Configura i seguenti elementi **[!UICONTROL Variable Mappings]**:

   | Elemento | Descrizione |
   |---|---|
   | ID messaggio | Seleziona un eVar per raccogliere gli ID messaggio in tempo reale. |
   | Recipient ID | Seleziona un eVar per raccogliere gli ID dei destinatari in tempo reale. |
   | Rimbalzi totali | Selezionare un evento numerico per ricevere rimbalzi giornalieri da Responsys. |
   | Invia e-mail | Selezionare un evento numerico da ricevere ogni giorno invii da Responsys. |
   | Clic | Selezionare un evento numerico per ricevere i clic totali giornalieri da Responsys. |
   | Aperto | Selezionare un evento numerico per ricevere le aperture totali giornaliere da Responsys. |
   | Annulla sottoscrizione | Selezionare un evento numerico per ricevere gli annullamenti giornalieri delle iscrizioni da Responsys. |
   | Consegnato | Seleziona un evento numerico da ricevere ogni giorno per le consegne da Responsys. |

1. Abilita l’accesso ai dati e configura la raccolta dati.
   1. Rinomina le classificazioni in base alle esigenze.
   1. **[!UICONTROL Partner segments]** sono segmenti di remarketing standard inclusi nell’integrazione.
   1. In **[!UICONTROL Access Requests]**, seleziona la casella per consentire l’esportazione delle informazioni di prodotto in Responsys nei segmenti di remarketing giornalieri.
   1. Configura se raccogliere gli ID aggiornando manualmente il codice di raccolta di Analytics o utilizzando la soluzione automatizzata. Se selezioni **[!UICONTROL Automated Solution]**, devi includere i parametri utilizzati nei collegamenti e-mail per trasmettere gli ID.
1. Rivedi tutti gli elementi di configurazione e fai clic su **[!UICONTROL Activate Now]**.

## Configurazione all&#39;interno del sistema Responsys{#configuring-within-the-responsys-system}

Per attivare l’integrazione è necessario contattare il supporto Responsys.

Dopo aver completato l’integrazione guidata, devi attivare l’integrazione in Responsys.

Per farlo, contatta il team di supporto Responsys all&#39;indirizzo support@responsys.com.
