---
description: Procedura per completare la procedura guidata di integrazione nell'interfaccia Connettori dati.
seo-description: Procedura per completare la procedura guidata di integrazione nell'interfaccia Connettori dati.
seo-title: Completamento della procedura guidata di integrazione di Adobe
solution: Analytics
title: Completamento della procedura guidata di integrazione di Adobe
uuid: fb106251-78cf-4a2a-8ba2-2a39188ba910
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Completamento della procedura guidata di integrazione di Adobe{#completing-the-adobe-integration-wizard}

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
