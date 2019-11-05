---
description: Prima che i canali e i dati dei canali possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Potete anche creare importi di costo e budget per i canali associati e specificare per quanto tempo il periodo di coinvolgimento del visitatore deve durare. Esegui le attività di configurazione dei rapporti in Strumenti di amministrazione.
seo-description: Prima che i canali e i dati dei canali possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Potete anche creare importi di costo e budget per i canali associati e specificare per quanto tempo il periodo di coinvolgimento del visitatore deve durare. Esegui le attività di configurazione dei rapporti in Strumenti di amministrazione.
seo-title: Informazioni sui canali e sulle regole
solution: Analytics
subtopic: Canali di marketing
title: Informazioni sui canali e sulle regole
topic: Reports and Analytics
uuid: 7d574790-4d0d-419d-8fb5-c16ec5a4a387
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Informazioni sui canali e sulle regole

Prima che i canali e i dati dei canali possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Potete anche creare importi di costo e budget per i canali associati e specificare per quanto tempo il periodo di coinvolgimento del visitatore deve durare. Esegui le attività di configurazione dei rapporti in Strumenti di amministrazione.

Considerate un canale come un contenitore per le visite. Le regole assegnano visite al contenitore appropriato.

![](assets/buckets_2.png)

Adobe fornisce diversi canali predefiniti durante una configurazione [](/help/components/c-marketing-channels/c-channel-autosetup.md) automatica che potete modificare in base alle vostre esigenze.

>[!NOTE]
>
> Adobe consiglia di impostare il rapporto in una suite di rapporti da utilizzare come modello a scopo di test. Potete utilizzare il modello per applicare canali e set di regole a livello globale a una o più suite di rapporti di produzione.
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](/help/components/c-marketing-channels/t-template.md).

Esaminate i seguenti argomenti:

* [Prerequisiti](/help/components/c-marketing-channels/c-channels-rules.md#prereqs)
* [Note importanti sull'elaborazione](/help/components/c-marketing-channels/c-channels-rules.md#important-proc-rules)

## Prerequisiti {#prereqs}

Se necessario, contattate l'Assistenza clienti per assistenza su questi prerequisiti:

* Nella console di amministrazione (Impostazioni account generali), abilita l’opzione **[!UICONTROL Conversion Level]** (e-commerce) per la suite di rapporti.

   Consulta Impostazioni [account](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) generali nell'Aiuto di Analytics per ulteriori informazioni.

* Configurate l’accesso al gruppo di utenti **[!UICONTROL Marketing Channel Report]**.

   See [Configure User Group Access](/help/components/c-marketing-channels/t-user-groups.md).

* Verifica che il tuo account manager sia abilitato **[!UICONTROL Channel Reports]** per la suite di rapporti.

## Note importanti sull'elaborazione {#important-proc-rules}

* Il sistema elabora le regole nell'ordine specificato e quando viene soddisfatta una regola, il sistema interrompe l'elaborazione delle regole rimanenti.
* Le regole possono accedere alle variabili che VISTA ha impostato, ma non ai dati che VISTA ha eliminato.
* I canali memorizzano solo le metriche di conversione. Le metriche del traffico non sono disponibili.
* Due canali di marketing non ricevono mai crediti per lo stesso evento (ad esempio acquisti o clic). In questo modo, i canali di marketing sono diversi dalle eVar (due eVar potrebbero ricevere credito per lo stesso evento).
* Il rapporto può elaborare fino a 25 canali alla volta.

