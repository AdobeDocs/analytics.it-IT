---
description: Gestione dashboard consente di copiare, condividere, archiviare e pianificare le dashboard per la distribuzione.
subtopic: Dashboards
title: Dashboard Manager
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: 6efb60ae2f565e67426c78bf830ada655e29b3af
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 4%

---


# Dashboard Manager

Gestione dashboard consente di copiare, condividere, archiviare e pianificare le dashboard per la distribuzione.

>[!IMPORTANT]
>
>Quando si utilizza Gestione dashboard, è consigliabile non disporre di più di 300 dashboard per ogni singolo utente. Inoltre, si prega di notare che il manager carica tutte le dashboard condivise qui sotto, quindi siate consapevoli con la condivisione di dashboard.

Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| Elemento | Descrizione |
|--- |--- |
| Shared | Indica se il dashboard è condiviso. |
| Pianificato | Consente di pianificare la consegna del dashboard. |
| Visualizza archivio | Questa funzionalità non è più disponibile. |
| Invia agli utenti | Consente di condividere una dashboard. |
| Gestire i   | Consente di modificare, copiare ed eliminare una dashboard. |

## Gestione di dashboard condivisi

Passaggi che descrivono l’utilizzo delle opzioni di gestione del dashboard condiviso.

1. Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.
1. In [!UICONTROL Shared Dashboards]questa sezione, individuate il dashboard condiviso (o il dashboard legacy) da gestire e scegliete una o più delle seguenti opzioni:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> Opzione </th> 
  <th class="chdeschd"> Descrizione </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Visualizza archivio</strong></td> 
  <td class="chdesc stentry"> Questa funzionalità non è più disponibile. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Dashboard Player</strong></td> 
  <td class="chdesc stentry"> <p>I server SiteCatalyst 14 non rispondono più alle richieste di dati di Dashboard Player. Tutte le dashboard attualmente visualizzate in Dashboard Player sono accessibili nell'interfaccia standard di Reporting e analisi o ricreato come dashboard in tempo reale. Le dashboard in tempo reale sono progettate specificatamente per la visualizzazione continua e includono una modalità a schermo intero per consentire la visualizzazione su TV o altri dispositivi di grandi dimensioni. </p> <p>Azione utente richiesta: È necessario interrompere l'utilizzo di Dashboard Player. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Copy Me</strong></td> 
  <td class="chdesc stentry"> Aggiunge una copia all’elenco delle dashboard utilizzando lo stesso nome dell’originale. Tuttavia, non è possibile visualizzare gli aggiornamenti o le modifiche apportate dal proprietario del dashboard. Copiando una dashboard legacy si apre una dashboard vuota, in cui è possibile aggiungere contenuto legacy. <p>Importante:  Se gli utenti condivisi del dashboard non sono in grado di visualizzare le modifiche apportate nel dashboard, controllate che Dashboard Manager verifichi se gli utenti hanno scelto l'opzione <span class="uicontrol"> Copia utente </span> . Se lo hanno fatto, non possono vedere gli aggiornamenti o le modifiche apportate dall'utente. Per visualizzare tutte le modifiche/gli aggiornamenti, gli utenti condivisi devono selezionare l'opzione <span class="uicontrol"> Menu attivato </span> in Gestione dashboard. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Menu attivato</strong></td> 
  <td class="chdesc stentry"> Consente di visualizzare le modifiche e gli aggiornamenti apportati dal proprietario del dashboard. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Unshare</strong></td> 
  <td class="chdesc stentry"> Rimuove il dashboard dall'elenco delle dashboard condivise. </td> 
 </tr> 
</table>

## Migrazione di un dashboard legacy

Le dashboard esistenti continueranno a essere eseguite e potrai comunque modificarle, scaricarle e pianificarle; tuttavia, non è più possibile creare nuove dashboard legacy. Si consiglia vivamente di aggiornare le dashboard esistenti al formato dashboard più recente.

>[!NOTE]
>
>In futuro, prendete in considerazione la possibilità di utilizzare [progetti](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html) Analysis Workspace e la possibilità di scaricarli e pianificarli.

Quando copiate il dashboard legacy, il sistema apre il dashboard legacy per la modifica, in cui potete aggiungere contenuto legacy o nuovo contenuto. Quando copiate una dashboard precedente, l’originale viene mantenuto nell’elenco delle dashboard precedenti.

>[!NOTE]
>
>L’aggiunta di contenuti legacy a una dashboard crea una dashboard basata sulle funzionalità più recenti della dashboard. Tuttavia, il minirapporto legacy potrebbe contenere dati basati sulla piattaforma dati precedente.

**Per migrare una versione 14.x del dashboard legacy**

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Nella [!UICONTROL Manage] colonna, sotto [!UICONTROL Legacy Dashboards], fare clic **[!UICONTROL Copy to New Dashboard]**.

   Il dashboard copiato si apre nell&#39;editor di layout del dashboard.

   Consultate [Modifica dei dati](/help/analyze/reports-analytics/dashboard.md)del dashboard e del minirapporto.

## Condivisione di un dashboard

Procedura che descrive come un amministratore può condividere (o inviare) una dashboard a più utenti. Quando si inviano dashboard agli utenti, queste diventano disponibili nel [!UICONTROL Shared Dashboards] menu dell&#39;utente.

1. Individuate il [!UICONTROL Dashboard Manager]dashboard, quindi abilitate **[!UICONTROL Shared]**.
1. Fai clic su **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. Nella [!UICONTROL Push Dashboard] pagina, selezionate gli utenti di destinazione o fate clic su **[!UICONTROL Check All]**.
1. Fai clic su **[!UICONTROL Save]**.

Se gli utenti condivisi del dashboard non riescono a vedere le modifiche apportate nel dashboard, controllate che il manager del dashboard verifichi se gli utenti hanno scelto l&#39; **[!UICONTROL Copy Me]** opzione. Se lo hanno fatto, non possono vedere gli aggiornamenti o le modifiche apportate dall&#39;utente. Per visualizzare tutte le modifiche/gli aggiornamenti, gli utenti condivisi devono selezionare l&#39; **[!UICONTROL On Menu]** opzione in Dashboard Manager.

## Pianificazione di un dashboard per la consegna

In [!UICONTROL Dashboard Manager], potete verificare se una dashboard è pianificata per la consegna e modificare la pianificazione. Le opzioni di consegna del dashboard sono identiche alle opzioni di consegna del rapporto.

1. Aprite una dashboard.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Send]**.

   Per ulteriori informazioni, consulta [Pianificazione e distribuzione](/help/analyze/reports-analytics/scheduling.md) .

## Archiviare un dashboard

>[!NOTE]
>
>Questa funzionalità non sarà più disponibile a gennaio 2020.

Procedura che descrive come archiviare qualsiasi dashboard inviata come file PDF. Il sistema memorizza il file archiviato per due anni, o fino a quando non si raggiunge un limite massimo di 4 GB di rapporti archiviati, a seconda di quale sia il primo.

1. Aprite una dashboard.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Nel [!UICONTROL Email Report] gruppo, abilita **[!UICONTROL Archive]**.
1. Specificate le opzioni di consegna, quindi fate clic su **[!UICONTROL Send]**.

   Potete visualizzare le dashboard archiviate in Dashboard Manager. In alternativa, aprite un dashboard e fate clic su **[!UICONTROL More]** > **[!UICONTROL View Archive]**.
