---
description: nulle
seo-description: nulle
seo-title: Implementazione dell'integrazione
solution: Analytics
title: Implementazione dell'integrazione
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Implementazione dell'integrazione{#deploying-the-integration}

La distribuzione di questa integrazione è un processo semplice che richiede le seguenti azioni:

## Completamento della procedura guidata di integrazione di Adobe{#completing-the-adobe-integration-wizard}

Procedura per completare la procedura guidata di integrazione nell'interfaccia Connettori dati.

1. Passa all'area Connettori dati (precedentemente Genesis) in Adobe Experience Cloud.
1. Avviate la procedura guidata di integrazione di Responsys.
1. Scegliete la suite di rapporti desiderata e specificate un nome per l'integrazione.
1. Configura i seguenti elementi:

   | Elemento | Descrizione |
   |---|---|
   | Indirizzo e-mail | Indirizzo e-mail del contatto principale |
   | Descrizione | (Facoltativo) Descrizione per questa configurazione di integrazione |
   | ID account | Ottenuto contattando il team di assistenza di Responsys all'indirizzo support@responsys.com |

1. Configurate i seguenti **[!UICONTROL Variable Mappings]** elementi:

   | Elemento | Descrizione |
   |---|---|
   | ID messaggio | Seleziona un'eVar per raccogliere gli ID messaggio in tempo reale. |
   | ID destinatario | Seleziona un'eVar per raccogliere gli ID dei destinatari in tempo reale. |
   | Totale importi | Selezionare un evento numerico per ricevere rimbalzi giornalieri dalle risposte. |
   | E-mail inviata | Selezionare un evento numerico per ricevere le invii giornalieri dalle risposte. |
   | Clic | Selezionare un evento numerico per ricevere i clic totali giornalieri dalle risposte. |
   | Aperto | Selezionare un evento numerico per ricevere il totale giornaliero si apre dalle risposte. |
   | Annulla sottoscrizione | Selezionare un evento numerico per ricevere le sottoscrizioni giornaliere dalle risposte. |
   | Consegnato | Selezionare un evento numerico per ricevere le consegne giornaliere dalle risposte. |

1. Abilita l'accesso ai dati e configura la raccolta dati.
   1. Rinominare le classificazioni in base alle esigenze.
   1. **[!UICONTROL Partner segments]** sono segmenti di remarketing standard inclusi nell’integrazione.
   1. In **[!UICONTROL Access Requests]** questa casella di controllo è possibile esportare le informazioni sui prodotti nelle risposte nei segmenti di remarketing giornalieri.
   1. Configura se raccogliere gli ID aggiornando manualmente il codice di raccolta di Analytics o utilizzando la soluzione automatizzata. Se selezionate **[!UICONTROL Automated Solution]**, dovete includere i parametri utilizzati nei collegamenti e-mail per trasmettere gli ID.
1. Rivedete tutti gli elementi di configurazione e fate clic su **[!UICONTROL Activate Now]**.

## Configurazione all'interno del sistema Responsys{#configuring-within-the-responsys-system}

Per attivare l'integrazione è necessario contattare il supporto di Responsys.

Dopo aver completato la procedura guidata di integrazione, è necessario attivare l’integrazione in Responsys.

A tal fine, contattate il team di assistenza di Responsys all'indirizzo support@responsys.com.