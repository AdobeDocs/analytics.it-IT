---
title: Introduzione ai canali di marketing
description: Scopri il flusso di lavoro Canali di marketing, la configurazione automatica e come applicare le impostazioni della suite di rapporti di modelli a più suite di rapporti.
feature: Marketing Channels
exl-id: 35938bf9-89ab-434f-9dc2-7a65251412ef
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 7%

---

# Introduzione ai canali di marketing

>[!NOTE]
>
>Per massimizzare l’efficacia dei canali di marketing per Attribution IQ e Customer Journey Analytics, abbiamo pubblicato alcune [best practice](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Gli amministratori di Analytics possono gestire i canali di marketing per le loro organizzazioni come descritto in [Gestire i canali di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).

I canali di marketing vengono comunemente utilizzati per fornire approfondimenti su come i visitatori arrivano sul sito. Puoi personalizzare le regole di elaborazione dei canali di marketing in base a quali canali desideri monitorare e a come desideri tenerne traccia.

I canali di marketing ruotano attorno alle metriche Primo contatto e Ultimo contatto, che sono componenti delle metriche di conversione standard.

## Flusso di lavoro dei canali di marketing

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step1_icon.png) Definisci ogni canale in base ai requisiti aziendali.

La definizione dei canali utilizzati è uno dei componenti più importanti dei canali di marketing. La definizione dei canali può richiedere la collaborazione tra più persone all’interno dell’organizzazione. Di seguito sono riportate alcune domande da considerare:

* Stai utilizzando una ricerca a pagamento?
* Stai utilizzando campagne e-mail? Stai utilizzando più campagne e-mail che desideri monitorare separatamente?
* Hai affiliati che indirizzano il traffico al tuo sito? Ci sono affiliati che desideri monitorare individualmente?
* Esistono campagne esterne che sarebbero vantaggiose per il tracciamento separato?
* Vuoi aggregare tutti i siti di social networking o ce ne sono di che desideri monitorare singolarmente?
* Vuoi tenere traccia di altri canali che potrebbero influenzare la conversione?

Un elenco dei canali consigliati è disponibile in [Domande frequenti ed esempi](/help/components/c-marketing-channels/c-faq.md). Creare un elenco di canali da utilizzare, in modo da semplificarne l&#39;attivazione e la definizione durante la creazione.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step2_icon.png) Aggiungere canali di marketing su [!UICONTROL Marketing Channel Manager] pagina.

Dopo aver definito i canali da tracciare, puoi abilitarli in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

Consulta [Canali e regole](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md) per informazioni importanti sui prerequisiti e sui concetti.

Consulta [Aggiungere canali di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md) per la procedura.

>[!NOTE]
>
>Se i canali di marketing non sono stati configurati in precedenza, il [impostazione automatica](/help/components/c-marketing-channels/c-getting-started-mchannel.md) visualizzazioni. Questa configurazione fornisce diversi canali preconfigurati che puoi personalizzare. L’Adobe consiglia di utilizzare queste regole come modello. Tuttavia, se si dispone già di definizioni di canale solido, è possibile saltare la configurazione automatica.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step3_icon.png) Configurare o perfezionare le regole di ogni canale sulla [!UICONTROL Marketing Channel Processing Rules] pagina.

Dopo aver creato i canali su [!UICONTROL Marketing Channel Manager] , puoi configurare le regole in modo che i canali possano recuperare e generare rapporti sui dati.

Consulta [Regole di elaborazione per il canale di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

Se i canali sono stati creati nella configurazione automatica, le regole in tali canali vengono definite. Puoi modificarli in base alle tue esigenze.

## Impostazione automatica per i canali di marketing {#run-auto-setup}

Il rapporto Canale di marketing include una pagina di configurazione una tantum per iniziare. Fornisce diversi canali di marketing che puoi utilizzare per il tracciamento. Puoi saltare questa configurazione se hai familiarità con la creazione di canali e regole. Tuttavia, l’Adobe consiglia di consentire la creazione guidata dei canali. La configurazione automatica consente di vedere come vengono create le regole o di modificarle per i propri scopi. Puoi disattivare o eliminare i canali predefiniti in qualsiasi momento.

Come eseguire la configurazione automatica di Marketing Channels.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Il giorno [!UICONTROL Report Suite Manager], seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![Risultato del passaggio](assets/wizard.png)

   >[!NOTE]
   >
   >Il [!UICONTROL Marketing Channels: Auto Setup] viene visualizzata automaticamente quando accedi alle applicazioni di configurazione del canale in Strumenti di amministrazione. (vedere [Marketing Channel Manager](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).) Questa pagina non viene visualizzata se la suite di rapporti contiene uno o più canali di marketing. Non puoi accedere nuovamente a questa pagina a meno che non selezioni un’altra suite di rapporti che non contiene canali di marketing.

1. Assicurati che i canali da creare siano selezionati.

   Se selezionata, **[!UICONTROL Email]**, **[!UICONTROL Display]**, e **[!UICONTROL Affiliate]** sono campi obbligatori.

1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

## Applicazione delle impostazioni suite di rapporti per più suite di rapporti

Come utilizzare una suite di rapporti principale come modello per testare la configurazione del canale di marketing. Per risparmiare tempo, puoi applicare questo modello a una o più suite di rapporti di produzione in un aggiornamento di massa. Questa attività viene eseguita separatamente per i canali e i set di regole.

>[!NOTE]
>
>Applicare i canali da un modello prima di applicare i set di regole. Quando esegui questa procedura, i canali devono essere gli stessi in tutte le suite di rapporti.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Il giorno **[!UICONTROL Report Suite Manager]** , seleziona la suite di rapporti di modelli e una o più suite di rapporti di target.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. Il giorno **[!UICONTROL Select Master Report Suites]** , seleziona una suite di rapporti di modelli.
1. Fai clic su **[!UICONTROL Save All]** (Usa modello di attribuzione non predefinito).
1. Applicare regole da un modello a più suite di rapporti:
   1. Torna a [!UICONTROL Report Suite Manager] pagina.
   1. Seleziona la suite di rapporti di modelli e una o più suite di rapporti di destinazione.
   1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. Fai clic su **[!UICONTROL Save]**. Se il pulsante Salva è disabilitato in questo passaggio, abilitalo espandendo una delle regole.
