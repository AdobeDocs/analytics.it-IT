---
title: Definizione dei canali
description: Prima che i canali e i dati dei canali possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Potete anche creare importi di costo e budget per i canali associati e specificare per quanto tempo il periodo di coinvolgimento del visitatore deve durare. Esegui le attività di configurazione dei rapporti in Strumenti di amministrazione.
translation-type: tm+mt
source-git-commit: e080c38e536f710490291aaca252cba36456b0f9

---


# Definizione dei canali

Prima che i canali e i dati dei canali possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Potete anche creare importi di costo e budget per i canali associati e specificare per quanto tempo il periodo di coinvolgimento del visitatore deve durare. Esegui le attività di configurazione dei rapporti in Strumenti di amministrazione.

Considerate un canale come un contenitore per le visite. Le regole assegnano visite al contenitore appropriato.

![](assets/buckets_2.png)

Adobe fornisce diversi canali predefiniti durante una configurazione [](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md) automatica che potete modificare in base alle vostre esigenze.

>[!NOTE]
>
>Adobe consiglia di impostare il rapporto in una suite di rapporti da utilizzare come modello a scopo di test. Potete utilizzare il modello per applicare canali e set di regole a livello globale a una o più suite di rapporti di produzione.
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](/help/components/c-marketing-channels/getting-started/t-template.md).

## Prerequisiti {#prereqs}

Se necessario, contattate l&#39;Assistenza clienti per assistenza su questi prerequisiti:

* Nella console di amministrazione (Impostazioni account generali), abilita l’opzione **[!UICONTROL Conversion Level]** (e-commerce) per la suite di rapporti.

   Consulta Impostazioni [account](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/general-acct-settings-admin.html) generali nell&#39;Aiuto di Analytics per ulteriori informazioni.

* Configurate l&#39;accesso alle dimensioni del canale di marketing.

   Consultate Autorizzazioni per i canali [di marketing](/help/components/c-marketing-channels/mc-access/c-channel-report-access.md).

* Verifica che il tuo account manager sia abilitato **[!UICONTROL Channel Reports]** per la suite di rapporti.

## Note importanti sull&#39;elaborazione {#important-proc-rules}

* Il sistema elabora le regole nell&#39;ordine specificato e quando viene soddisfatta una regola, il sistema interrompe l&#39;elaborazione delle regole rimanenti.
* Le regole possono accedere alle variabili che VISTA ha impostato, ma non ai dati che VISTA ha eliminato.
* I canali memorizzano solo le metriche di conversione. Le metriche del traffico non sono disponibili.
* Due canali di marketing non ricevono mai crediti per lo stesso evento (ad esempio acquisti o clic). In questo modo, i canali di marketing sono diversi dalle eVar (due eVar potrebbero ricevere credito per lo stesso evento).
* Il rapporto può elaborare fino a 25 canali alla volta.

