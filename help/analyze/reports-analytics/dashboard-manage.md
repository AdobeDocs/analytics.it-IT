---
description: Dashboard Manager consente di copiare, condividere, archiviare e pianificare la distribuzione dei dashboard.
subtopic: Dashboards
title: Dashboard Manager
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
feature: Nozioni di base su Reports & Analytics
role: Business Practitioner, Administrator
exl-id: abd5acf5-f743-4c94-81fb-fc6cc69e8f26
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 2%

---

# Dashboard Manager

Dashboard Manager consente di copiare, condividere, archiviare e pianificare la distribuzione dei dashboard.

>[!IMPORTANT]
>
>Quando si utilizza Dashboard Manager, è consigliabile non disporre di più di 300 dashboard per ogni singolo utente. Inoltre, ricorda che il responsabile carica tutte le dashboard condivise di seguito, quindi fai attenzione a condividere le dashboard.

Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Dashboards]**.

| Elemento | Descrizione |
|--- |--- |
| Condiviso | Indica se il dashboard è condiviso. |
| Pianificato | Consente di pianificare la consegna del dashboard. |
| Visualizza archivio | Questa funzionalità non è più disponibile. |
| Invia agli utenti | Consente di condividere un dashboard. |
| Gestire i   | Consente di modificare, copiare ed eliminare un dashboard. |

## Gestire le dashboard condivise

Passaggi che descrivono come utilizzare le opzioni di gestione del dashboard condiviso.

1. Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Dashboards]**.
1. In [!UICONTROL Shared Dashboards], individua il dashboard condiviso (o il dashboard legacy) che desideri gestire e scegli una o più delle seguenti opzioni:

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
  <td class="chdesc stentry"> <p>I server di SiteCatalyst 14 non risponderanno più alle richieste di dati di Dashboard Player. Tutte le dashboard attualmente visualizzate in Dashboard Player sono accessibili nell'interfaccia standard di Reports &amp; Analytics o ricreato come dashboard in tempo reale. Le dashboard in tempo reale sono progettate appositamente per la visualizzazione continua e includono una modalità a schermo intero che consente la visualizzazione su televisori o altri dispositivi a schermo grande. </p> <p>Azione utente richiesta: È necessario interrompere l'utilizzo di Dashboard Player. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Copy Me</strong></td> 
  <td class="chdesc stentry"> Aggiunge una copia nell’elenco delle dashboard con lo stesso nome dell’originale. Tuttavia, non è possibile visualizzare gli aggiornamenti o le modifiche apportate dal proprietario del dashboard. Copiare un dashboard legacy consente di aprire un dashboard vuoto in cui è possibile aggiungere contenuto legacy. <p>Importante:  Se gli utenti condivisi del dashboard non possono vedere le modifiche apportate nel dashboard, controlla il tuo Dashboard Manager per vedere se gli utenti hanno scelto l'opzione <span class="uicontrol"> Copy Me </span> (Copia utente). Se lo hanno fatto, non possono vedere gli aggiornamenti o le modifiche apportate da te. Per visualizzare tutte le modifiche/gli aggiornamenti, gli utenti condivisi devono selezionare l'opzione <span class="uicontrol"> Nel menu </span> in Dashboard Manager. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Menu attivato</strong></td> 
  <td class="chdesc stentry"> Consente di visualizzare le modifiche o gli aggiornamenti apportati dal proprietario del dashboard. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Unshare</strong></td> 
  <td class="chdesc stentry"> Rimuove il dashboard dall’elenco delle dashboard condivise. </td> 
 </tr> 
</table>

## Migrazione di un dashboard legacy

Le dashboard esistenti continueranno a essere eseguite e potrai comunque modificarle, scaricarle e pianificarle; tuttavia, non è più possibile creare nuove dashboard legacy. Ti consigliamo vivamente di aggiornare le dashboard legacy esistenti al formato dashboard più recente.

>[!NOTE]
>
>In futuro, considera l&#39;utilizzo di [progetti Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) e la possibilità di scaricarli e pianificarli.

Quando copi il dashboard legacy, il sistema apre il dashboard legacy per la modifica, in cui puoi aggiungere contenuto legacy o nuovo contenuto. Quando copi un dashboard legacy, l’originale viene mantenuto nell’elenco delle dashboard legacy.

>[!NOTE]
>
>L’aggiunta di contenuto legacy a un dashboard crea un dashboard basato sulle funzionalità più recenti del dashboard. Tuttavia, il reportlet legacy potrebbe contenere dati basati sulla piattaforma dati precedente.

**Per eseguire la migrazione di un dashboard legacy versione 14.x**

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Nella colonna [!UICONTROL Manage], sotto [!UICONTROL Legacy Dashboards] fare clic su **[!UICONTROL Copy to New Dashboard]**.

   Il dashboard copiato si apre nell’editor di layout del dashboard.

   Consulta [Modifica dei dati del dashboard e del reportlet](/help/analyze/reports-analytics/dashboard.md).

## Condivisione di un dashboard

Procedura che descrive come un amministratore può condividere (o inviare in push) un dashboard a più utenti. Quando invii le dashboard agli utenti, diventano disponibili nel menu [!UICONTROL Shared Dashboards] dell’utente.

1. In [!UICONTROL Dashboard Manager], individua il dashboard, quindi abilita **[!UICONTROL Shared]**.
1. Fai clic su **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. Nella pagina [!UICONTROL Push Dashboard] , seleziona gli utenti target o fai clic su **[!UICONTROL Check All]**.
1. Fai clic su **[!UICONTROL Save]**.

Se gli utenti condivisi del dashboard non possono vedere le modifiche apportate nel dashboard, controlla il tuo Dashboard Manager per vedere se gli utenti hanno scelto l&#39;opzione **[!UICONTROL Copy Me]**. Se lo hanno fatto, non possono vedere gli aggiornamenti o le modifiche apportate da te. Per visualizzare tutte le modifiche/gli aggiornamenti, gli utenti condivisi devono selezionare l&#39;opzione **[!UICONTROL On Menu]** in Dashboard Manager.

## Pianificare un dashboard per la consegna

In [!UICONTROL Dashboard Manager] puoi vedere se è prevista la consegna di un dashboard e modificare la pianificazione. Le opzioni di consegna del dashboard sono identiche alle opzioni di consegna del report.

1. Apri un dashboard.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Send]**.

   Per ulteriori informazioni, consulta [Pianificazione e distribuzione](/help/analyze/reports-analytics/scheduling.md) .

## Archiviare un dashboard

>[!NOTE]
>
>Questa funzionalità non sarà più disponibile a gennaio 2020.

Passaggi che descrivono come archiviare qualsiasi dashboard inviato come file PDF. Il sistema memorizza il file archiviato per due anni, o fino a quando non si raggiunge un limite massimo di 4 GB di rapporti archiviati, a seconda di quale dei due eventi si verifica prima.

1. Apri un dashboard.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Nel gruppo [!UICONTROL Email Report] , abilita **[!UICONTROL Archive]**.
1. Specifica le opzioni di consegna, quindi fai clic su **[!UICONTROL Send]**.

   Potete visualizzare le dashboard archiviate in Dashboard Manager. In alternativa, apri una dashboard e fai clic su **[!UICONTROL More]** > **[!UICONTROL View Archive]**.
