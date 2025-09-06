---
title: Introduzione ai canali di marketing
description: Scopri il flusso di lavoro Canali di marketing, la configurazione automatica e come applicare un modello di impostazioni a più suite di rapporti.
feature: Marketing Channels
exl-id: 35938bf9-89ab-434f-9dc2-7a65251412ef
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 97%

---

# Introduzione ai canali di marketing

>[!NOTE]
>
>Per massimizzare l’efficacia dei canali di marketing per la funzione Attribuzione e Customer Journey Analytics, abbiamo pubblicato alcune [best practice revisionate](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Gli amministratori di Analytics possono gestire i canali di marketing per le loro organizzazioni come descritto in [Gestire i canali di marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

I canali di marketing vengono comunemente utilizzati per fornire insight su come i visitatori arrivano sul sito. Puoi personalizzare le regole di elaborazione dei canali di marketing in base a quali desideri monitorare e a come desideri tenerne traccia.

I canali di marketing ruotano attorno alle metriche di primo contatto e ultimo contatto, che sono componenti delle metriche di conversione standard.

## Flusso di lavoro dei canali di marketing

![](assets/step1_icon.png) Definisci ogni canale in base ai tuoi requisiti di business.

La definizione dei canali utilizzati è uno dei componenti più importanti dei canali di marketing. Per definire i canali può esere necessario collaborare con più persone all’interno dell’organizzazione. Di seguito sono riportate alcune domande da considerare:

* Utilizzi la ricerca a pagamento?
* Utilizzi campagne e-mail? Utilizzi più campagne e-mail da tracciare separatamente?
* Hai dei partner che indirizzano il traffico verso il tuo sito? Alcuni partner devono essere tracciati separatamente?
* Esistono campagne esterne che sarebbe utile tracciare separatamente?
* Vuoi aggregare tutti i siti di social networking o ce ne sono alcuni di cui vuoi tenere traccia separatamente?
* Vuoi tenere traccia di altri canali che potrebbero influenzare la conversione?

Un elenco dei canali consigliati è disponibile nella sezione [Domande frequenti ed esempi](/help/components/c-marketing-channels/c-faq.md). Crea un elenco di canali che vuoi utilizzare, in modo che, al momento di crearli, sarà più facile abilitarli e definirli.

![](assets/step2_icon.png) Aggiungi i canali di marketing dalla pagina [!UICONTROL Marketing Channel Manager].

Dopo aver definito i canali da tracciare, puoi abilitarli da **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

Consulta [Canali e regole](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md) per informazioni importanti sui prerequisiti e sui concetti.

Consulta [Aggiungere canali di marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md) per la procedura da seguire.

>[!NOTE]
>
>Se i canali di marketing non sono stati configurati in precedenza, viene visualizzata la [configurazione automatica](/help/components/c-marketing-channels/c-getting-started-mchannel.md). Questa configurazione fornisce diversi canali preconfigurati che puoi personalizzare. Adobe consiglia di utilizzare queste regole come modello. Tuttavia, se hai già delle definizioni di canale solide, puoi saltare la configurazione automatica.

![](assets/step3_icon.png) Configura o perfeziona le regole di ogni canale dalla pagina [!UICONTROL Marketing Channel Processing Rules].

Dopo aver creato i canali dalla pagina [!UICONTROL Marketing Channel Manager], puoi configurare le regole in modo che i canali possano recuperare dati e generare rapporti.

Consulta [Regole di elaborazione per il canale di marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md).

Se i canali sono stati creati nella configurazione automatica, le regole in tali canali sono già definite. Puoi modificarle in base alle tue esigenze.

## Configurazione automatica per i canali di marketing {#run-auto-setup}

Il rapporto sui canali di marketing include una pagina di configurazione una tantum per iniziare. Fornisce diversi canali di marketing che puoi utilizzare per il tracciamento. Se hai familiarità con la creazione di canali e regole, puoi saltare questa configurazione. Tuttavia, Adobe consiglia di consentire la creazione guidata dei canali. Seguendo la configurazione automatica puoi capire come vengono create le regole o come modificarle per i tuoi scopi. Puoi disabilitare o eliminare i canali predefiniti in qualsiasi momento.

Come eseguire la configurazione automatica dei canali di marketing.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. In [!UICONTROL Report Suite Manager], seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![Risultato del passaggio](assets/wizard.png)

   >[!NOTE]
   >
   >La pagina [!UICONTROL Marketing Channels: Auto Setup] viene visualizzata in automatico quando accedi alle applicazioni di configurazione dei canali in Strumenti di amministrazione. (Vedi [Marketing Channel Manager](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).) Questa pagina non viene visualizzata se la suite di rapporti contiene uno o più canali di marketing. Non puoi accedere nuovamente a questa pagina a meno che non selezioni un’altra suite di rapporti che non contiene canali di marketing.

1. Assicurati che i canali che desideri creare siano selezionati.

   Se selezionati, **[!UICONTROL Email]**, **[!UICONTROL Display]**, e **[!UICONTROL Affiliate]** sono campi obbligatori.

1. Fai clic su **[!UICONTROL Save]**.

## Applicazione delle impostazioni della suite di rapporti di modelli a più suite di rapporti

Come utilizzare una suite di rapporti principale come modello per testare la configurazione del canale di marketing. Per risparmiare tempo, puoi applicare questo modello a una o più suite di rapporti di produzione in un aggiornamento di massa. Questa attività viene eseguita separatamente per i canali e i set di regole.

>[!NOTE]
>
>Applicazione di i canali da un modello prima di applicare i set di regole. Quando esegui questa procedura, i canali devono essere gli stessi in tutte le suite di rapporti.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Nella pagina **[!UICONTROL Report Suite Manager]**, seleziona la suite di rapporti di modelli e una o più suite di rapporti di destinazione.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. Nella pagina **[!UICONTROL Select Master Report Suites]**, seleziona una suite di rapporti di modelli.
1. Fai clic su **[!UICONTROL Save All]**.
1. Applicazione delle regole da un modello a più suite di rapporti:
   1. Torna alla pagina [!UICONTROL Report Suite Manager].
   1. Seleziona la suite di rapporti di modelli e una o più suite di rapporti di destinazione.
   1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. Fai clic su **[!UICONTROL Save]**. Se il pulsante Salva è disabilitato in questo passaggio, abilitalo espandendo una delle regole.
