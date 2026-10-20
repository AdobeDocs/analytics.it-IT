---
title: Metriche del ciclo di vita mobile
description: Metriche basate su dati raccolti tramite Mobile SDK.
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
TQID: 'https://experienceleague.adobe.com/Y1IigGbQygTsS9UD3WEp9z8rLTqkeDuhZZ83AJQMa3o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 6%
---
# Metriche del ciclo di vita mobile

>[!BEGINSHADEBOX]

*Questa pagina fa riferimento ai dati tracciati comunemente tramite Adobe Experience Platform Mobile SDK. Per le dimensioni tracciate con Mobile SDK, consulta [Dimensioni del ciclo di vita mobile](../dimensions/lifecycle-dimensions.md). Per informazioni sul dispositivo mobile tramite l&#39;agente utente, vedere [Dimensioni di ricerca mobile](../dimensions/mobile-dimensions.md).*

>[!ENDSHADEBOX]

| Nome metrica del ciclo di vita | Descrizione | Variabile dati contestuali |
| --- | --- | --- |
| **[!UICONTROL First Launches]** | Il numero di volte in cui l’app è stata eseguita per la prima volta dopo l’installazione o la reinstallazione. | `a.InstallEvent` |
| **[!UICONTROL Upgrades]** | Il numero di volte in cui l’app è stata eseguita per la prima volta dopo un aggiornamento o dopo la modifica del numero di versione. | `a.UpgradeEvent` |
| **[!UICONTROL Launches]** | Il numero di volte in cui l’app è stata eseguita, comprese le esecuzioni dopo arresti anomali e installazioni. Un avvio viene conteggiato anche quando l’app riprende dal background dopo il superamento del timeout della sessione del ciclo di vita. | `a.LaunchEvent` |
| **[!UICONTROL Crashes]** | Il numero di volte in cui l’app si è bloccata prima della chiusura. L&#39;arresto anomalo viene segnalato al successivo avvio dell&#39;app. | `a.CrashEvent` |
| **[!UICONTROL Total Session Length]** | Il numero totale di secondi in cui le sessioni dell&#39;app sono durate, in base a quanto tempo l&#39;app è stata aperta e in primo piano. Ogni lancio riporta la durata della sessione precedente; questa metrica è la somma di tali valori. | `a.PrevSessionLength` |
| **[!UICONTROL Action Time Total]** | Il numero totale di secondi (tempo di clock) tra l&#39;inizio e la fine di un&#39;azione temporizzata, nelle sessioni. Viene compilata dai metodi `trackTimedAction` nel SDK Mobile Services legacy (4.x). | `a.action.time.total` |
| **[!UICONTROL Action Time In App]** | Il numero di secondi trascorsi nell’app dall’inizio alla fine di un’azione temporizzata, nell’arco di più sessioni. Viene compilata dai metodi `trackTimedAction` nel SDK Mobile Services legacy (4.x). | `a.action.time.inapp` |
| **[!UICONTROL Lifetime Value (event)]** | Il valore del ciclo di vita di un utente, ad esempio acquisti, visualizzazioni di annunci, video completati o condivisioni social nel corso del ciclo di vita. Viene compilata dal metodo `trackLifetimeValueIncrease` nel SDK Mobile Services legacy (4.x). | `a.ltv.amount` |

>[!NOTE]
>
>Le metriche [!UICONTROL Action Time Total], [!UICONTROL Action Time In App] e [!UICONTROL Lifetime Value (event)] sono compilate da metodi nel SDK Mobile Services legacy (4.x), che non è più supportato. Il SDK Adobe Experience Platform Mobile non popola automaticamente queste metriche. Consulta [Migrazione da libreria mobile Adobe (v4) ad Experience Platform Analytics](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/) per alternative alle azioni temporizzate e al tracciamento del valore del ciclo di vita.
