---
description: nulle
seo-description: nulle
seo-title: Conformità GDPR/eprivacy e inoltro lato server
title: Conformità GDPR/eprivacy e inoltro lato server
uuid: 1 b 90 c 567-3321-4 dbd-a 699-38 c 04 e 809 fa 4
translation-type: tm+mt
source-git-commit: 26c3cc9895c27d6abc452e0a4636771fb2415fb3

---


# Conformità GDPR/eprivacy e inoltro lato server

This section explains recent enhancements to server-side forwarding that were prompted by the [EU cookie compliance regulation](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm), which went into effect on Sept. 30, 2017.

Server-side forwarding is used to share data from Adobe Analytics to other [!DNL Experience Cloud Solutions], such as Audience Manager, in real time. Quando abilitata, l'inoltro lato server consente anche ad Analytics di inviare dati ad altre soluzioni Experience Cloud e a quelle soluzioni per inviare dati ad Analytics durante il processo di raccolta dati.

Fino alla fine, l'inoltro lato server non era in grado di delineare tra il consenso e gli eventi/hit pre-autorizzazione. Dal 1 novembre 2018, l'Utente come titolare del trattamento (cliente Adobe Analytics) dispone dell'opzione per limitare i dati preliminari ad Adobe Analytics e impedire che venga inoltrato ad AAM. Una nuova variabile di contesto dell'implementazione consente di contrassegnare le richieste dove non è stato ricevuto il consenso. La variabile, quando impostata, impedisce che queste richieste vengano inviate all'AAM fino al ricevimento del consenso.

When this new context variable, `cm.ssf=1`, exists on a hit, this hit gets flagged and does not get server-side-forwarded to AAM. Viceversa, se la stringa non viene visualizzata in un hit, l'hit viene inoltrato ad AAM.

L'inoltro lato server è bidirezionale, ovvero quando viene applicato a un hit e l'hit viene inoltrato a AAM, Audience Analytics riceve le informazioni del segmento per quell'hit da AAM e lo invia nuovamente ad Analytics. Di conseguenza, tutti gli hit che non sono trasmessi su server da Analytics ad AAM non verranno arricchiti con l'elenco degli ID del segmento da AAM. Pertanto, si verificherà un sottoinsieme di traffico/hit che non riceveranno informazioni sull'ID del segmento da AAM.

## Implementation Details {#section_FFA8B66085BF469FAB5365C944FE38F7}

A seconda del metodo di implementazione, attenetevi alla procedura seguente.

| Metodo di implementazione | Passaggi |
|--- |--- |
| Adobe Experience Platform Launch | Assuming you have the Adobe Analytics extension installed, add the following context data variable definition to the custom code editor within the Action configuration of a Rule: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Set the `contextdata` variable to *0* for customers who consented to targeted marketing. |
| DTM | Add the context data variable definition to the Custom Page Code editor: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Impostare la variabile di dati su 0 per i clienti che hanno acconsentito al marketing mirato. |
| AppMeasurement | Add the context data variable definition to the AppMeasurement.js file:  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Impostare la variabile di dati su 0 per i clienti che hanno acconsentito al marketing mirato. |

## Reporting (Optional) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Potete utilizzare Adobe Analytics per segnalare la quantità di traffico sul quale il traffico è basato sul consenso e come risultato del server rispetto a quanto del traffico non è in vigore e non è stato inoltrato ad AAM.

Per configurare questo tipo di rapporto, mappate la nuova variabile di contesto su una variabile di traffico personalizzata (prop) tramite le regole di elaborazione. A tal fine

1. Implementa la variabile «cm. ssf» (come mostrato sopra).
1. [Abilitare il prop.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Utilizza le regole di elaborazione per mappare la variabile di contesto sulla proprietà.

   1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** , then select a report suite.
   1. Click  **[!UICONTROL Edit Report Suite]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Processing Rules]** .
   1. Fai clic su **[!UICONTROL Add Rule.]**
   1. Under **[!UICONTROL Always Execute]**, overwrite the value of the prop you had enabled with the context variable “cm.ssf(Context Data)”.
   1. Fai clic su **[!UICONTROL Save]**.

