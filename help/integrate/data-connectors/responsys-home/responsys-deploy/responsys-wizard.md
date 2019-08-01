---
description: Procedura per completare la procedura guidata di integrazione nell'interfaccia dei Connettori dati.
seo-description: Procedura per completare la procedura guidata di integrazione nell'interfaccia dei Connettori dati.
seo-title: Completamento della procedura guidata Integrazione Adobe
solution: Analytics
title: Completamento della procedura guidata Integrazione Adobe
uuid: fb 106251-78 cf -4 a 2 a -8 ba 2-2 a 39188 ba 910
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Procedura per completare la procedura guidata di integrazione nell'interfaccia dei Connettori dati.

1. Passa all'area Connettori dati (precedentemente Genesis) all'interno di Adobe Marketing Cloud.
1. Avviate la procedura guidata di integrazione Responsys.
1. Scegli la suite di rapporti desiderata e specifica un nome per l'integrazione.
1. Configurate i seguenti elementi:

   | Elemento | Descrizione |
   |---|---|
   | Indirizzo e-mail | Indirizzo e-mail del contatto principale |
   | Descrizione | (Facoltativo) Descrizione per questa configurazione integrazione |
   | ID account | Ottenuto contattando il team di assistenza di Responsys all'indirizzo support@responsys.com |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   | Elemento | Descrizione |
   |---|---|
   | ID messaggio | Seleziona un evar per la raccolta di ID messaggio in tempo reale. |
   | ID destinatario | Seleziona un evar per raccogliere l'ID destinatario in tempo reale. |
   | Totale bounce | Selezionare un evento numerico per ricevere rimbalzi giornalieri da Responsys. |
   | E-mail inviata | Selezionare un evento numerico da ricevere quotidianamente da Responsys. |
   | Clic | Selezionare un evento numerico per ricevere i clic totali giornalieri di Responsys. |
   | Aperto | Seleziona un evento numerico per ricevere il totale giornaliero da Responsys. |
   | Annullato | Selezionate un evento numerico per ricevere le sottoscrizioni giornaliere da Responsys. |
   | Consegnato | Selezionare un evento numerico per ricevere le consegne giornaliere di Responsys. |

1. Abilita l'accesso ai dati e la configurazione della raccolta dati.
   1. Rinominare le classificazioni in base alle esigenze.
   1. **[!UICONTROL Partner segments]** sono segmenti di remarketing standard inclusi nell'integrazione.
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to Responsys in daily remarketing segments.
   1. Configura se raccogliere gli ID aggiornando manualmente il codice di raccolta di Analytics o utilizzando la soluzione automatizzata. If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID’s.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
