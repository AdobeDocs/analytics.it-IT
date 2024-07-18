---
description: Scopri come utilizzare il Reporting Activity Manager per diagnosticare e risolvere i problemi di capacità durante i periodi in cui si verificano picchi di reporting.
title: Annullare le richieste di reporting in Reporting Activity Manager
feature: Admin Tools
exl-id: 37a2fa8f-7804-4220-a508-ec66996b3801
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '1420'
ht-degree: 5%

---

# Annullare le richieste di reporting in Reporting Activity Manager

[!UICONTROL Reporting Activity Manager] consente agli amministratori di diagnosticare e annullare rapidamente le richieste di reporting per risolvere i problemi di capacità di reporting durante i periodi in cui si verificano picchi di reporting.

Quando annulli le richieste di reporting, considera quanto segue:

* Puoi annullare richieste specifiche, annullare tutte le richieste provenienti da un utente specifico o annullare tutte le richieste relative a un progetto specifico.

  Quando annulli una richiesta, l&#39;azione viene registrata nei [registri](/help/admin/admin/logs.md). La colonna [!UICONTROL **Tipo evento**] viene visualizzata come [!UICONTROL **Azione amministratore**] e una descrizione dell&#39;annullamento è disponibile nella colonna [!UICONTROL **Evento**].

* Quando annulli le richieste, puoi anche scegliere di limitare le richieste successive per un determinato periodo di tempo.

  Quando si limita una richiesta successiva, l&#39;azione viene registrata nei [registri](/help/admin/admin/logs.md). La colonna [!UICONTROL **Tipo evento**] viene visualizzata come [!UICONTROL **Azione amministratore**] e una descrizione della restrizione è disponibile nella colonna [!UICONTROL **Evento**].

* Non puoi annullare una richiesta se la colonna [!UICONTROL **Utente**] di una richiesta indica che è [!UICONTROL **Non riconosciuto**]. In questo caso, significa che l’utente si trova in una società di accesso per la quale non disponi di autorizzazioni amministrative.

Per ulteriori informazioni su Reporting Activity Manager, inclusi i vantaggi chiave e i requisiti delle autorizzazioni, vedere [Panoramica di Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Annullare richieste specifiche

Puoi annullare singole richieste che consumano una grande quantità di capacità di reporting.

1. In Adobe Analytics, vai a **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Seleziona la suite di rapporti in cui desideri annullare le richieste di reporting. <!--double-check this step-->

   Per ulteriori informazioni sui dati disponibili in questa pagina, vedere [Visualizzare l&#39;attività di reporting in Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Seleziona la scheda [!UICONTROL **Richieste**], quindi seleziona una o più richieste.

   <!-- add screenshot -->

1. Seleziona [!UICONTROL **Annulla richieste**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Annulla _x_ richieste report**].

1. Il campo Messaggio di annullamento mostra il messaggio visualizzato agli utenti quando le loro richieste vengono annullate. Viene fornito un messaggio predefinito. Puoi aggiornare il messaggio predefinito per fornire ulteriori dettagli.

1. (Facoltativo) Per limitare le richieste future per un determinato periodo di tempo:

   1. Abilita l&#39;opzione per [!UICONTROL **Limitare le richieste successive**]

      ![Limita le richieste successive](assets/restrict-subsequent-requests.png)

   1. Scegli tra le seguenti opzioni:

      | Opzione | Funzione |
      |---------|----------|
      | [!UICONTROL **Utente e progetto**] | Agli utenti associati alle richieste selezionate verrà temporaneamente impedito di eseguire richieste di reporting per i progetti associati. |
      | [!UICONTROL **Utente**] | Agli utenti associati alle richieste selezionate verrà temporaneamente impedito di effettuare richieste di reporting. |
      | [!UICONTROL **Progetto**] | I progetti associati alle richieste selezionate saranno temporaneamente esclusi da tutte le richieste di reporting. |
      | [!UICONTROL **Limitato per**] | Scegli per quanto tempo le richieste verranno limitate. È possibile scegliere tra 1 minuto (impostazione predefinita), 5 minuti, 10 minuti, 15 minuti o 30 minuti. <!-- double-check this --><p>Non è possibile rimuovere una restrizione subito dopo averla impostata.</p> |

      {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Continua con annullamento**].

   In Analysis Workspace viene visualizzata una notifica per informare gli utenti che la richiesta è stata annullata. Per ulteriori informazioni su come verrà visualizzato in Analysis Workspace, vedi [Esperienza con l&#39;accesso degli utenti a un report annullato](#experience-when-users-access-a-cancelled-report).

## Annulla richieste per utente

Puoi annullare tutte le richieste associate a uno o più utenti.

1. In Adobe Analytics, vai a **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Seleziona la suite di rapporti in cui desideri annullare le richieste di reporting. <!--double-check this step-->

   Per ulteriori informazioni sui dati disponibili in questa pagina, vedere [Visualizzare l&#39;attività di reporting in Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Seleziona la scheda [!UICONTROL **Utenti**], quindi seleziona uno o più utenti.

   <!-- add screenshot -->

1. Seleziona [!UICONTROL **Annulla richieste**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Annulla _x_ richieste di report da x utenti**].

1. Il campo Messaggio di annullamento mostra il messaggio visualizzato agli utenti quando le loro richieste vengono annullate. Viene fornito un messaggio predefinito. Puoi aggiornare il messaggio predefinito per fornire ulteriori dettagli.

1. (Facoltativo) Per limitare le richieste future per un determinato periodo di tempo:

   1. Abilita l&#39;opzione per [!UICONTROL **Limitare le richieste successive**].

      ![Limita le richieste successive per utente](assets/restrict-subsequent-requests-user.png)

   1. Scegli tra le seguenti opzioni:

      | Opzione | Funzione |
      |---------|----------|
      | [!UICONTROL **Utente e progetto**] | Agli utenti selezionati verrà temporaneamente impedito di effettuare richieste di reporting per i progetti associati. |
      | [!UICONTROL **Utente**] | Agli utenti selezionati verrà temporaneamente impedito di effettuare richieste di reporting. |
      | [!UICONTROL **Progetto**] | I progetti associati agli utenti selezionati saranno esclusi da tutte le richieste di reporting effettuate da qualsiasi utente. |
      | [!UICONTROL **Limitato per**] | Scegli per quanto tempo le richieste verranno limitate. È possibile scegliere tra 1 minuto (impostazione predefinita), 5 minuti, 10 minuti, 15 minuti o 30 minuti. <!--double-check this--> <p>Non è possibile rimuovere una restrizione subito dopo averla impostata.</p> |

      {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Continua con annullamento**].

   In Analysis Workspace viene visualizzata una notifica per informare gli utenti che la richiesta è stata annullata. Per ulteriori informazioni su come verrà visualizzato in Analysis Workspace, vedi [Esperienza con l&#39;accesso degli utenti a un report annullato](#experience-when-users-access-a-cancelled-report).

## Annulla richieste per progetto

Puoi annullare tutte le richieste associate a uno o più progetti.

1. In Adobe Analytics, vai a **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Seleziona la suite di rapporti in cui desideri annullare le richieste di reporting. <!--double-check this step-->

   Per ulteriori informazioni sui dati disponibili in questa pagina, vedere [Visualizzare l&#39;attività di reporting in Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Seleziona la scheda [!UICONTROL **Progetti**], quindi seleziona uno o più progetti.

   <!-- add screenshot -->

1. Seleziona [!UICONTROL **Annulla richieste**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Annulla _x_ richieste di report da x progetti**].

1. Il campo Messaggio di annullamento mostra il messaggio visualizzato agli utenti quando le loro richieste vengono annullate. Viene fornito un messaggio predefinito. Puoi aggiornare il messaggio predefinito per fornire ulteriori dettagli.

1. (Facoltativo) Per limitare le richieste future per un determinato periodo di tempo:

   1. Abilita l&#39;opzione per [!UICONTROL **Limitare le richieste successive**].

      ![Limita le richieste successive per progetto](assets/restrict-subsequent-requests-project.png)

   1. Scegli tra le seguenti opzioni:

      | Opzione | Funzione |
      |---------|----------|
      | [!UICONTROL **Utente e progetto**] | I progetti selezionati saranno temporaneamente esclusi da qualsiasi richiesta di reporting effettuata dagli utenti associati. |
      | [!UICONTROL **Utente**] | Agli utenti associati ai progetti selezionati sarà impedito di effettuare richieste di reporting. |
      | [!UICONTROL **Progetto**] | I progetti selezionati saranno temporaneamente esclusi da qualsiasi richiesta di reporting effettuata da qualsiasi utente. |
      | [!UICONTROL **Limitato per**] | Scegli per quanto tempo le richieste verranno limitate. È possibile scegliere tra 1 minuto (impostazione predefinita), 5 minuti, 10 minuti, 15 minuti o 30 minuti. <!--double-check this--> <p>Non è possibile rimuovere una restrizione subito dopo averla impostata.</p> |

      {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Continua con annullamento**].

   In Analysis Workspace viene visualizzata una notifica per informare gli utenti che la richiesta è stata annullata. Per ulteriori informazioni su come verrà visualizzato in Analysis Workspace, vedi [Esperienza con l&#39;accesso degli utenti a un report annullato](#experience-when-users-access-a-cancelled-report).

## Annulla richieste per applicazione

Puoi annullare tutte le richieste associate a una o più applicazioni. Quando si annullano richieste associate a un&#39;applicazione, è possibile scegliere di limitare ulteriormente le richieste associate a tale applicazione per un determinato periodo di tempo.

Le applicazioni includono:

* Interfaccia utente di Analysis Workspace
* Progetti pianificati in Workspace
* Report Builder
* Interfaccia utente di Builder: segmento, metriche calcolate, annotazioni, pubblico, ecc.
* Chiamate API da 1.4 o 2.0 API
* Avvisi intelligenti
* Condividi con qualsiasi collegamento
* Qualsiasi altra applicazione che esegue query sul motore di reporting di Analytics

Per annullare le richieste per applicazione:

1. In Adobe Analytics, vai a **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Seleziona la connessione in cui desideri annullare le richieste di reporting. <!--double-check this step-->

   Per ulteriori informazioni sui dati disponibili in questa pagina, vedere [Visualizzare l&#39;attività di reporting in Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Selezionare la scheda [!UICONTROL **Applicazioni**], quindi selezionare una o più applicazioni.

   <!-- add screenshot -->

1. Seleziona [!UICONTROL **Annulla richieste**].

   Viene visualizzata la finestra di dialogo [!UICONTROL **Annulla _x_ richieste di report da x progetti**].

1. Il campo Messaggio di annullamento mostra il messaggio visualizzato agli utenti quando le loro richieste vengono annullate. Viene fornito un messaggio predefinito. Puoi aggiornare il messaggio predefinito per fornire ulteriori dettagli.

1. (Facoltativo) Per limitare le richieste future per un determinato periodo di tempo:

   1. Abilita l&#39;opzione per [!UICONTROL **Limitare le richieste successive**]

      ![Limita le richieste successive per applicazione](assets/restrict-subsequent-requests-application.png)

   1. Scegli tra le seguenti opzioni:

      | Opzione | Funzione |
      |---------|----------|
      | [!UICONTROL **Utente e progetto**] | Le applicazioni selezionate saranno temporaneamente escluse da qualsiasi richiesta di reporting effettuata dagli utenti e dai progetti associati.<p>Si tratta dell’opzione meno restrittiva.</p> |
      | [!UICONTROL **Utente**] | Agli utenti associati alle applicazioni selezionate verrà impedito di effettuare richieste di reporting. |
      | [!UICONTROL **Progetto**] | Ai progetti associati alle applicazioni selezionate non sarà consentito inviare richieste di creazione di rapporti da parte di qualsiasi utente. |
      | [!UICONTROL **Limitato per**] | Scegli per quanto tempo le richieste verranno limitate. È possibile scegliere tra 1 minuto (impostazione predefinita), 5 minuti, 10 minuti, 15 minuti o 30 minuti. <!--double-check this--> <p>Non è possibile rimuovere una restrizione subito dopo averla impostata.</p> |

      {style="table-layout:auto"}

1. Seleziona [!UICONTROL **Continua con annullamento**].

   Nell’applicazione viene visualizzata una notifica (ad esempio in Analysis Workspace) che informa gli utenti che la richiesta è stata annullata. Per ulteriori informazioni su come verrà visualizzato in Analysis Workspace, vedi [Esperienza con l&#39;accesso degli utenti a un report annullato](#experience-when-users-access-a-cancelled-report).

## Esperienza di accesso degli utenti a un rapporto annullato

In Analysis Workspace, quando gli utenti tentano di accedere a un rapporto o a una visualizzazione interessati da una cancellazione, visualizzano i seguenti messaggi:

### Messaggio sul progetto

Quando gli utenti tentano di accedere a un progetto interessato da un annullamento, viene visualizzato un messaggio per informare che il rapporto è temporaneamente limitato:

![Messaggio di annullamento progetto](assets/workspace-canceled-report.png)

### Messaggio sulla visualizzazione

Quando gli utenti tentano di accedere a una visualizzazione interessata da un annullamento, viene visualizzato un messaggio per informarli che l’elaborazione dei dati per il rapporto è temporaneamente limitata:

![Messaggio di annullamento visualizzazione](assets/workspace-cancelled-visualization.png)
