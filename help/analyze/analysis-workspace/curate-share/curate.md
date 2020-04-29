---
description: Utilizzando i componenti curati è possibile limitare i componenti disponibili prima di condividere un progetto. Puoi condividere all’interno dell’azienda un progetto e i relativi componenti con gli addetti al marketing e altri dipendenti non addetti alle analisi. Aggiungi commenti e tag ai progetti.
keywords: Analysis Workspace
title: Panoramica di cura/condivisione
topic: Reports and analytics
uuid: 267e9678-95a1-4195-8ba4-e8a53c28ea0d
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Panoramica di cura/condivisione

Utilizzando i componenti curati è possibile limitare i componenti disponibili prima di condividere un progetto. Puoi condividere all’interno dell’azienda un progetto e i relativi componenti con gli addetti al marketing e altri dipendenti non addetti alle analisi. Aggiungi commenti e tag ai progetti.

**Video introduttivo**

>[!VIDEO](https://www.youtube.com/watch?v=LJJRskdmlOg&amp;index=79&amp;t=0s&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)

**[!UICONTROL Workspace]** (Workspace) > **[!UICONTROL Share]** (Condividi) > **[!UICONTROL Curate Project Data]** (Cura dati progetto)

## Cura dati progetto

1. Specifica le autorizzazioni per creare e curare progetti.

   Prima di creare o curare un progetto di Analysis Workspace, gli amministratori devono aggiungere gli utenti a un [gruppo](https://docs.adobe.com/content/help/it-IT/analytics/admin/user-product-management/user-groups/groups.html) su cui sia abilitata l’autorizzazione **[!UICONTROL Analysis Workspace Access]** (Accesso ad Analytics Workspace), oppure un gruppo di utenti. (**[!UICONTROL All Report Access]** (Accesso a tutti i rapporti). **[!UICONTROL Admin]** (Amministratore) > **[!UICONTROL User Management]** (Gestione utenti) > **[!UICONTROL Groups]** (Gruppi)).

1. [Crea e salva](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) un progetto, quindi fai clic su **[!UICONTROL Share]** (Condividi) > **[!UICONTROL Curate Project Data]** (Cura dati progetto).
1. Trascina i componenti che vuoi condividere dalla sovrapposizione di componenti trascinabili a sinistra fino al campo **[!UICONTROL Curated Components]** (Componenti curati).

   ![](assets/curated-components.png)

   >[!IMPORTANT]
   >
   >La cura dei componenti non è necessaria per la condivisione di un progetto. Puoi condividere un progetto con tutti i componenti predefiniti disponibili o con i componenti selezionati. Per conservare tutti i componenti predefiniti di un progetto, una procedura consigliata è quella di crearne una copia personale usando l’opzione **[!UICONTROL Save As]** (Salva con nome) prima di curarne i componenti. In un progetto con componenti curati, gli altri componenti non sono più disponibili.

1. Fai clic su **[!UICONTROL Done]** (Fine).

Il progetto risultante si comporta come un progetto tipico di Analysis Workspace, ma sarà possibile scegliere solo i componenti specificati.

## Condivisione di un progetto curato

La condivisione rende il progetto disponibile ad altri utenti di Analysis Workspace all’interno dell’azienda. Ogni cura effettuata viene riflessa nel progetto utilizzato da altri.

1. Dopo aver curato i componenti di un rapporto, fai clic su **[!UICONTROL Share]** (Condividi) > **[!UICONTROL Share Project]** (Condividi progetto).

   ![](assets/share_component.png)

1. Aggiungi i destinatari.
1. (Facoltativo) Puoi condividere componenti di progetto incorporati (segmenti, metriche calcolate e intervalli di date) con tutti i destinatari. Una volta condivisi, tali componenti sono disponibili nel menu a discesa dei componenti nell’interfaccia Workspace del destinatario.

   >[!IMPORTANT]
   >
   >Questa impostazione non è persistente; è una singola azione da eseguire al momento della condivisione.

1. Hai inoltre la possibilità di impostare questa pagina come pagina di destinazione per i destinatari.

   >[!IMPORTANT]
   >
   >Questa impostazione non è persistente; è una singola azione da eseguire al momento della condivisione.

1. Fai clic su **[!UICONTROL Share]** (Condividi).

<!-- 

<p> <b>Annotate and tag a project</b> </p> 
<p>An alternative way to collaborate on a project is to use the Information panel. This panel will be re-introduced in an upcoming release. </p> 
<p> </p> 
<ul id="ul_EFD045FD9F3B4BF8A70637B00EE0BC9C"> 
 <li id="li_EC6C5EAF9C234E76BDA7FF0226B82083">Tag reports for sharing. </li> 
 <li id="li_CF6A438C55F847F8890F8CB674CAA4F7">Specify the recipient (filter by permission group or user name), the storage folder. In-product notifications let users know that they have a shared report waiting. </li> 
 <li id="li_C8E088DA43024277908705CB0F3A142A">Write messages or report descriptions for recipients. </li> 
 <li id="li_342EB4758C344B859757E23691068FA3"> Select the dimensions, metrics, and segments to recommend to a non-analyst colleague, who can view the report you are curating and sharing. Curating the component gives the recipient access to those components, based on their permission settings. </li> 
 <li id="li_6487500F9315481599B7F3897998879F"> Add suggested items to a previously configured report. These new items exist as recommended selectable options. </li> 
</ul>

 -->

