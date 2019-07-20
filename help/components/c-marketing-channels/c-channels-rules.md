---
description: Prima che i canali e i dati del canale possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Potete anche creare importi costi e budget per i canali associati e specificare per quanto tempo si desidera durare il periodo di coinvolgimento dei visitatori. Esegui le attività di configurazione dei rapporti in Strumenti di amministrazione.
seo-description: Prima che i canali e i dati del canale possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Potete anche creare importi costi e budget per i canali associati e specificare per quanto tempo si desidera durare il periodo di coinvolgimento dei visitatori. Esegui le attività di configurazione dei rapporti in Strumenti di amministrazione.
seo-title: Informazioni sui canali e sulle regole
solution: Analytics
subtopic: Canali di marketing
title: Informazioni sui canali e sulle regole
topic: Reports & Analytics
uuid: 7 d 574790-4 d 0 d -419 d -8 fb 5-c 16 ec 5 a 4 a 387
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Informazioni sui canali e sulle regole

Prima che i canali e i dati del canale possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Potete anche creare importi costi e budget per i canali associati e specificare per quanto tempo si desidera durare il periodo di coinvolgimento dei visitatori. Esegui le attività di configurazione dei rapporti in Strumenti di amministrazione.

Pensa a un canale come contenitore per le visite. Le regole assegnano le visite al contenitore appropriato.

![](assets/buckets_2.png)

Adobe provides several predefined channels during an [automatic setup](../../components/c-marketing-channels/c-channel-autosetup.md#topic_E9ABE9E9E71B4E40A4E7EA9AD2C0372B) that you can edit to suit your needs.

>[!NOTE]
>
>Adobe consiglia di configurare il rapporto in una suite di rapporti da utilizzare come modello a scopo di test. Puoi utilizzare il modello per applicare set di regole e canali a una o più suite di rapporti di produzione.
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](../../components/c-marketing-channels/t-template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC).

Esaminate i seguenti argomenti:

* [Prerequisiti](../../components/c-marketing-channels/c-channels-rules.md#section_9913D2932E3140C099B7978CA95378B2)
* [Note importanti sull'elaborazione](../../components/c-marketing-channels/c-channels-rules.md#section_DE372EEF02314F2395750CF2892DAAE1)

## Prerequisiti {#section_9913D2932E3140C099B7978CA95378B2}

Se necessario, contatta l'Assistenza clienti per fornirti i seguenti prerequisiti:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   See [General Account Settings](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) in Analytics help for more information.

* Set up user group access to the **[!UICONTROL Marketing Channel Report]**.

   See [Configure User Group Access](../../components/c-marketing-channels/t-user-groups.md#task_B156E7527FE94055A43A697338FE8C8C).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Important processing notes {#section_DE372EEF02314F2395750CF2892DAAE1}

* Il sistema elabora le regole nell'ordine specificato e, quando una regola viene soddisfatta, il sistema interrompe l'elaborazione delle regole rimanenti.
* Le regole possono accedere alle variabili impostate da VISTA, ma non possono accedere ai dati eliminati da VISTA.
* I canali memorizzano solo le metriche di conversione. Le metriche di traffico non sono disponibili.
* Due canali di marketing non ricevono mai crediti per lo stesso evento (ad esempio acquisti o clic). In questo modo, i canali di marketing differiscono da evar (due evar potrebbero ricevere credito per lo stesso evento).
* Il rapporto può elaborare fino a 25 canali alla volta.

