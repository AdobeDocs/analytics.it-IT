---
title: Utilizzo di dati XDM con Analytics
description: 'Panoramica dell''utilizzo di dati XDM dalla piattaforma Experience in Adobe Analytics '
translation-type: tm+mt
source-git-commit: 31efa43043120b68de90e817a7980addbe2ded39

---




# Utilizzo dei dati Edge di Adobe Experience Platform con Analytics

>[!IMPORTANT]
>
>Adobe Experience Edge Web SDK non viene rilasciato ed è disponibile solo per il test beta tra i clienti invitati. Questa documentazione è destinata solo agli utenti beta e non rappresenta la funzionalità completa del prodotto. Se ti interessa diventare un utente beta per questo prodotto, contatta l’[assistenza clienti](https://helpx.adobe.com/it/contact/enterprise-support.ec.html) Adobe.


Puoi usare l’SDK [Web di](https://docs.adobe.com/content/help/it-IT/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) Adobe Experience Platform (AEP) per inviare dati ad Adobe Analytics. Questo funziona traducendo il modello dati [esperienza (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) in un formato utilizzato da Analytics.

Analytics raccoglie i dati XDM tramite due metodi:

* Mappatura automatica dagli schemi XDM

* Mappatura manuale ai dati contestuali

## Mappatura automatica

La mappatura automatica si basa su uno [schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) predefinito in XDM che popola automaticamente gli oggetti JSON inclusi nella raccolta dati Analytics tipica. Le variabili di [Analytics che vengono mappate automaticamente da XDM](https://git.corp.adobe.com/analytics-data-collection/anedge/blob/master/XDM_Translator.md) alle suite di rapporti configurate non richiedono alcun supporto da parte degli sviluppatori.

## Mappatura manuale

La mappatura manuale dei dati XDM su Analytics si basa sulle variabili dei dati [contestuali di](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) Analytics. Queste variabili vengono inserite in oggetti JSON che corrispondono agli schemi applicabili. In genere, il team di sviluppo aggiunge i dati contestuali al momento dell’implementazione, quindi gli amministratori impostano le regole [di](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) elaborazione per applicare tali dati a specifiche suite di rapporti.


## Configurazione

Per impostare Analytics per la ricezione dei dati XDM:

1. Installa e [configura](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) l’SDK [Web](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)Adobe Experience Platform.

2. Assicurati che le suite di rapporti applicabili siano mappate sui dati desiderati. I dati XDM scorrono automaticamente nella suite di rapporti dalla piattaforma Adobe Experience.

