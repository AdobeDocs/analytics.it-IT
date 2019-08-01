---
description: Procedura per completare la procedura guidata di integrazione nell'interfaccia dei Connettori dati.
seo-description: Procedura per completare la procedura guidata di integrazione nell'interfaccia dei Connettori dati.
seo-title: Completamento della procedura guidata Integrazione Adobe
solution: Analytics
title: Completamento della procedura guidata Integrazione Adobe
uuid: a 8135 be 3-fba 3-436 d -8959-faata 40 b 15088
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Procedura per completare la procedura guidata di integrazione nell'interfaccia dei Connettori dati.

1. Passa all'area Connettori dati (precedentemente Genesis) all'interno di Adobe Marketing Cloud.
1. Avviate la procedura guidata di integrazione di contactlab.
1. Scegli la suite di rapporti desiderata e specifica un nome per l'integrazione.
1. Configurate i seguenti elementi:

   | Elemento | Descrizione |
   |---|---|
   | Indirizzo e-mail | Indirizzo e-mail del contatto principale |
   | Descrizione | (Facoltativo) Descrizione per questa configurazione integrazione |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   | Elemento | Descrizione |
   |---|---|
   | Collegamento ID | Seleziona un evar per la raccolta di ID collegamento in tempo reale. |
   | ID messaggio | Seleziona un evar per la raccolta di ID messaggio in tempo reale. |
   | ID destinatario | Seleziona un evar per raccogliere l'ID destinatario in tempo reale. |
   | Non recapitate | Selezionate un evento numerico per ricevere rimbalzi giornalieri da contactlab. |
   | Inviato | Selezionate un evento numerico per ricevere le mandate giornaliere da contactlab. |
   | Clic | Selezionate un evento numerico per ricevere i clic totali giornalieri da contactlab. |
   | Aperto | Seleziona un evento numerico per ricevere il totale giornaliero da contactlab. |
   | Annullato | Selezionate un evento numerico per ricevere le sottoscrizioni giornaliere da contactlab. |

1. Abilita l'accesso ai dati e la configurazione della raccolta dati.
   1. Rinominare le classificazioni in base alle esigenze.
   1. **[!UICONTROL Partner segments]** sono segmenti di remarketing standard inclusi nell'integrazione.
   1. Under **[!UICONTROL Your Segments]**, select any custom segments that you would like to include in this integration. Puoi creare altri segmenti personalizzati sotto il pannello Amministrazione.
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to ContactLab in daily remarketing segments.
   1. Rinominare le metriche calcolate in base alle esigenze.
   1. Configura se raccogliere gli ID aggiornando manualmente il codice di raccolta di Analytics o utilizzando la soluzione automatizzata. If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID’s.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
