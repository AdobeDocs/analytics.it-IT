---
description: Utilizza Dashboard Manager per copiare, condividere, archiviare e pianificare i dashboard per la consegna.
subtopic: Dashboards
title: Dashboard Manager
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
feature: Reports & Analytics Basics
role: User, Admin
exl-id: abd5acf5-f743-4c94-81fb-fc6cc69e8f26
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 4%

---

# Dashboard Manager

{{ra-eol}}

Utilizza Dashboard Manager per copiare, condividere, archiviare e pianificare i dashboard per la consegna.

>[!IMPORTANT]
>
>Si consiglia di utilizzare Dashboard Manager con un massimo di 300 dashboard per ogni singolo utente. Inoltre, il manager carica tutte le dashboard condivise di seguito, quindi sii prudente a condividere le dashboard.

Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Dashboards]**.

| Elemento | Descrizione |
|--- |--- |
| Condiviso | Indica se il dashboard è condiviso. |
| Pianificato | Consente di pianificare la consegna del dashboard. |
| Visualizza archivio | Questa funzionalità non è più disponibile. |
| Invia agli utenti | Consente di condividere un dashboard. |
| Gestire i   | Consente di modificare, copiare ed eliminare un dashboard. |

## Gestire le dashboard condivise

Per gestire le dashboard condivise:

1. Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Dashboards]**.
1. Sotto [!UICONTROL Shared Dashboards], individua il dashboard condiviso (o il dashboard legacy) che desideri gestire e scegli una o più delle seguenti opzioni:

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
  <td class="choption"><strong>Lettore dashboard</strong></td> 
  <td class="chdesc stentry"> <p>I server SiteCatalyst 14 non risponderanno più alle richieste di dati del lettore del dashboard. È possibile accedere a tutte le dashboard attualmente visualizzate in Dashboard Player nell’interfaccia standard di Reports &amp; Analytics o ricrearle come dashboard in tempo reale. Le dashboard in tempo reale sono progettate appositamente per la visualizzazione continua e includono una modalità a schermo intero per consentire la visualizzazione su televisori o altri dispositivi a grande schermo. </p> <p>Azione utente richiesta: è necessario interrompere l’utilizzo di Dashboard Player. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Copy Me</strong></td> 
  <td class="chdesc stentry"> Aggiunge una copia nell’elenco delle dashboard con lo stesso nome dell’originale. Tuttavia, non puoi visualizzare eventuali aggiornamenti o modifiche apportate dal proprietario del dashboard. Quando si copia una dashboard legacy viene aperta una dashboard vuota in cui è possibile aggiungere contenuto legacy. <p>Importante: se gli utenti condivisi del dashboard non possono visualizzare le modifiche apportate nel dashboard, controlla nel Dashboard Manager per verificare se gli utenti hanno scelto <span class="uicontrol"> Copia </span> opzione. In caso contrario, non potranno visualizzare gli aggiornamenti o le modifiche che hai apportato. Per visualizzare tutte le modifiche/aggiornamenti, gli utenti condivisi devono selezionare <span class="uicontrol"> Menu On </span> in Dashboard Manager. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Menu On</strong></td> 
  <td class="chdesc stentry"> Consente di visualizzare le modifiche o gli aggiornamenti effettuati dal proprietario del dashboard. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Annullamento condivisione</strong></td> 
  <td class="chdesc stentry"> Rimuove la dashboard dall’elenco delle dashboard condivise. </td> 
 </tr> 
</table>

## Migrare un dashboard legacy

I dashboard legacy esistenti continueranno a essere eseguiti ed è ancora possibile modificarli, scaricarli e pianificarli; tuttavia, non è più possibile creare nuovi dashboard legacy. Si consiglia vivamente di aggiornare le dashboard legacy esistenti al formato dashboard più recente.

>[!NOTE]
>
>In futuro, puoi utilizzare [Progetti Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it) e la loro capacità di essere scaricati e pianificati.

Quando copi la dashboard legacy, il sistema la apre per la modifica, dove puoi aggiungere contenuto legacy o nuovo contenuto. Quando copi un dashboard legacy, l’originale viene mantenuto nell’elenco dei dashboard legacy.

>[!NOTE]
>
>L’aggiunta di contenuto legacy a una dashboard crea una dashboard basata sulle funzionalità della dashboard più recente. Tuttavia, il reportlet legacy potrebbe contenere dati basati sulla piattaforma dati precedente.

**Per migrare una dashboard legacy versione 14.x**

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. In [!UICONTROL Manage] colonna, sotto [!UICONTROL Legacy Dashboards], fai clic su **[!UICONTROL Copy to New Dashboard]**.

   Il dashboard copiato viene aperto nell’editor di layout del dashboard.

   Consulta [Modifica dei dati del dashboard e del reportlet](/help/analyze/reports-analytics/dashboard.md).

## Condividere un dashboard

Gli amministratori di Analytics possono condividere (o inviare) un dashboard a più utenti. Quando invii le dashboard agli utenti, queste diventano disponibili nel [!UICONTROL Shared Dashboards] menu.

Per condividere un dashboard con più utenti:

1. In [!UICONTROL Dashboard Manager], individua il dashboard, quindi abilita **[!UICONTROL Shared]**.
1. Fai clic su **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. Il giorno [!UICONTROL Push Dashboard] , selezionare gli utenti target o fare clic su **[!UICONTROL Check All]**.
1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

Se gli utenti condivisi del dashboard non possono visualizzare le modifiche apportate nel dashboard, controlla nel Dashboard Manager per verificare se gli utenti hanno scelto **[!UICONTROL Copy Me]** opzione. In caso contrario, non potranno visualizzare gli aggiornamenti o le modifiche che hai apportato. Per visualizzare tutte le modifiche/aggiornamenti, gli utenti condivisi devono selezionare **[!UICONTROL On Menu]** in Dashboard Manager.

## Pianificare una dashboard per la consegna

In [!UICONTROL Dashboard Manager], puoi vedere se è pianificata la consegna di un dashboard e modificarne la pianificazione. Le opzioni di consegna del dashboard sono identiche a quelle del report.

1. Apri una dashboard.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Send]**.

   Consulta [Pianificazione e distribuzione](/help/analyze/reports-analytics/scheduling.md) per ulteriori informazioni.
