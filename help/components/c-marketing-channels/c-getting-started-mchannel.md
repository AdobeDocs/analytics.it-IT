---
title: Introduzione ai canali di marketing
description: Scopri il flusso di lavoro Marketing Channels (Canali di marketing), la configurazione automatica e come applicare le impostazioni della suite di rapporti a più suite di rapporti.
translation-type: tm+mt
source-git-commit: 7202a49dda7c3ef4f4b535476d3cf637b9e9f7f6
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 3%

---


# Introduzione ai canali di marketing

>[!NOTE]
>
>Per massimizzare l&#39;efficacia dei canali di marketing per Attribution IQ e Customer Journey Analytics, abbiamo pubblicato alcune [best practice riviste](/help/components/c-marketing-channels/mchannel-best-practices.md).

I canali di marketing vengono comunemente utilizzati per fornire approfondimenti su come i visitatori arrivano sul tuo sito. Puoi personalizzare le regole di elaborazione del canale di marketing in base ai canali che desideri monitorare e a come desideri tenerli traccia.

I canali di marketing ruotano intorno alle metriche First e Last Touch, che sono componenti delle metriche di conversione standard.

## Flusso di lavoro dei canali di marketing

![](assets/step1_icon.png) Definisci ogni canale in base ai requisiti aziendali.

La definizione dei canali utilizzati è uno dei componenti più importanti di Marketing Channels. La definizione dei canali può richiedere la collaborazione tra più individui nell’organizzazione. Ecco alcune domande da considerare:

* Stai utilizzando una ricerca a pagamento?
* Utilizzi campagne e-mail? Utilizzi più campagne e-mail che desideri monitorare separatamente?
* Hai affiliati che indirizzano il traffico al tuo sito? Ci sono affiliati che desideri monitorare individualmente?
* Ci sono campagne esterne che sarebbero vantaggiose nel tracciamento separato?
* Vuoi aggregare tutti i siti di social networking o ce ne sono di che vuoi tenere traccia individualmente?
* Esistono altri canali che potrebbero influenzare la conversione di cui desideri tenere traccia?

Un elenco dei canali consigliati si trova in [Domande frequenti ed esempi](/help/components/c-marketing-channels/c-faq.md). Crea un elenco di canali da utilizzare, in modo da facilitarne l’attivazione e la definizione quando crei canali.

![](assets/step2_icon.png) Aggiungi canali di marketing sulla  [!UICONTROL Marketing Channel Manager] pagina.

Dopo aver definito i canali da tracciare, attivali in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

Consulta [Canali e regole](/help/components/c-marketing-channels/c-channels.md) per informazioni importanti sui prerequisiti e sui concetti.

Per la procedura, consulta [Aggiungi canali di marketing](/help/components/c-marketing-channels/c-channels.md) .

>[!NOTE]
>
>Se Marketing Channels non è stato configurato in precedenza, viene visualizzato il messaggio [setup automatico](/help/components/c-marketing-channels/c-getting-started-mchannel.md) . Questa configurazione fornisce diversi canali preconfigurati che è possibile personalizzare. Adobe consiglia di utilizzare queste regole come modello. Tuttavia, se disponi già di definizioni di canali solidi, puoi saltare la configurazione automatica.

![](assets/step3_icon.png) Configura o perfeziona le regole di ogni canale sulla  [!UICONTROL Marketing Channel Processing Rules] pagina.

Dopo aver creato i canali nella pagina [!UICONTROL Marketing Channel Manager], configuri le regole in modo che i canali possano recuperare e segnalare i dati.

Consulta [Regole di elaborazione del canale di marketing](/help/components/c-marketing-channels/c-rules.md).

Se i canali sono stati creati nella configurazione automatica, le regole in tali canali sono definite. Puoi modificarli in base alle tue esigenze.

## Configurazione automatica per canali di marketing {#run-auto-setup}

Il rapporto sul canale di marketing viene fornito con una pagina di configurazione unica per aiutarti a iniziare. Fornisce diversi canali di marketing che puoi utilizzare per il tracciamento. Puoi saltare questa configurazione se ti senti a tuo agio nel creare canali e regole. Tuttavia, Adobe consiglia di consentire alla procedura guidata di creare i canali desiderati. La configurazione automatica ti consente di vedere come vengono create le regole o di modificarle per scopi personalizzati. Puoi disattivare o eliminare i canali predefiniti in qualsiasi momento.

Come eseguire la configurazione automatica di Marketing Channels .

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. In [!UICONTROL Report Suite Manager], seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![Risultato del passaggio](assets/wizard.png)

   >[!NOTE]
   >
   >La pagina [!UICONTROL Marketing Channels: Auto Setup] viene visualizzata automaticamente quando accedi alle applicazioni di configurazione del canale in Strumenti di amministrazione. (Consulta [Marketing Channel Manager](/help/components/c-marketing-channels/c-channels.md).) Questa pagina non viene visualizzata se la suite di rapporti contiene uno o più canali di marketing. Non puoi accedere nuovamente a questa pagina a meno che non selezioni un’altra suite di rapporti che non contiene canali di marketing.

1. Assicurati che i canali da creare siano selezionati.

   Quando è selezionata questa opzione, i campi **[!UICONTROL Email]**, **[!UICONTROL Display]** e **[!UICONTROL Affiliate]** sono obbligatori.

1. Fai clic su **[!UICONTROL Save]**.

## Applicazione delle impostazioni suite di rapporti per più suite di rapporti

Utilizzare una suite di rapporti principale come modello per testare la configurazione del canale di marketing. Per risparmiare tempo, puoi applicare questo modello a una o più suite di rapporti di produzione in un aggiornamento di massa. Esegui questa attività separatamente per i canali e i set di regole.

>[!NOTE]
>
>Applica i canali da un modello prima di applicare i set di regole. Quando si esegue questa procedura, i canali devono essere gli stessi in tutte le suite di rapporti.

1. Assicurati che il rapporto Canale di marketing sia abilitato per le suite di rapporti selezionate. Il tuo Account Manager esegue questo passaggio.
1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Nella pagina **[!UICONTROL Report Suite Manager]** , seleziona la suite di rapporti del modello e una o più suite di rapporti di destinazione.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. Nella pagina **[!UICONTROL Select Master Report Suites]** , seleziona una suite di rapporti modello.
1. Fai clic su **[!UICONTROL Save All]**.
1. Applicare regole da un modello a più suite di rapporti:
   1. Torna alla pagina [!UICONTROL Report Suite Manager] .
   1. Seleziona la suite di rapporti modello e una o più suite di rapporti target.
   1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. Fai clic su **[!UICONTROL Save]**. Se in questo passaggio il pulsante Salva è disabilitato, abilitalo espandendo una delle regole.

