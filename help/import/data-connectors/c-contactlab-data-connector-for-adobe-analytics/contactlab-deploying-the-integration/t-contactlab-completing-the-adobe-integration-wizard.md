---
description: Procedura per completare la procedura guidata di integrazione nell'interfaccia Connettori dati.
seo-description: Procedura per completare la procedura guidata di integrazione nell'interfaccia Connettori dati.
seo-title: Completamento della procedura guidata di integrazione di Adobe
solution: Analytics
title: Completamento della procedura guidata di integrazione di Adobe
uuid: a8135be3-fba3-436d-8959-faed40b15088
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Completamento della procedura guidata di integrazione di Adobe{#completing-the-adobe-integration-wizard}

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
   | ID destinatario | Seleziona un'eVar per raccogliere gli ID dei destinatari in tempo reale. |
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
