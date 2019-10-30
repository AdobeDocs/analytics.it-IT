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
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Informazioni sui canali e sulle regole

Prima che i canali e i dati dei canali possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Potete anche creare importi di costo e budget per i canali associati e specificare per quanto tempo il periodo di coinvolgimento del visitatore deve durare. Esegui le attività di configurazione dei rapporti in Strumenti di amministrazione.

Considerate un canale come un contenitore per le visite. Le regole assegnano visite al contenitore appropriato.

![](assets/buckets_2.png)

Adobe fornisce diversi canali predefiniti durante una configurazione [](../../components/c-marketing-channels/c-channel-autosetup.md#topic_E9ABE9E9E71B4E40A4E7EA9AD2C0372B) automatica che potete modificare in base alle vostre esigenze.

> [!NOTE] Adobe consiglia di impostare il rapporto in una suite di rapporti da utilizzare come modello a scopo di test. Potete utilizzare il modello per applicare canali e set di regole a livello globale a una o più suite di rapporti di produzione.
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](../../components/c-marketing-channels/t-template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC).

Esaminate i seguenti argomenti:

* [Prerequisiti](../../components/c-marketing-channels/c-channels-rules.md#section_9913D2932E3140C099B7978CA95378B2)
* [Note importanti sull'elaborazione](../../components/c-marketing-channels/c-channels-rules.md#section_DE372EEF02314F2395750CF2892DAAE1)

## Prerequisiti {#section_9913D2932E3140C099B7978CA95378B2}

Se necessario, contattate l'Assistenza clienti per assistenza su questi prerequisiti:

* Nella console di amministrazione (Impostazioni account generali), abilita l’opzione **[!UICONTROL Conversion Level]** (e-commerce) per la suite di rapporti.

   Consulta Impostazioni [account](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) generali nell'Aiuto di Analytics per ulteriori informazioni.

* Configurate l’accesso al gruppo di utenti **[!UICONTROL Marketing Channel Report]**.

   See [Configure User Group Access](../../components/c-marketing-channels/t-user-groups.md#task_B156E7527FE94055A43A697338FE8C8C).

* Verifica che il tuo account manager sia abilitato **[!UICONTROL Channel Reports]** per la suite di rapporti.

## Note importanti sull'elaborazione {#section_DE372EEF02314F2395750CF2892DAAE1}

* Il sistema elabora le regole nell'ordine specificato e quando viene soddisfatta una regola, il sistema interrompe l'elaborazione delle regole rimanenti.
* Le regole possono accedere alle variabili che VISTA ha impostato, ma non ai dati che VISTA ha eliminato.
* I canali memorizzano solo le metriche di conversione. Le metriche del traffico non sono disponibili.
* Due canali di marketing non ricevono mai crediti per lo stesso evento (ad esempio acquisti o clic). In questo modo, i canali di marketing sono diversi dalle eVar (due eVar potrebbero ricevere credito per lo stesso evento).
* Il rapporto può elaborare fino a 25 canali alla volta.

