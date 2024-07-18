---
description: Puoi ricevere degli avvisi quando i componenti del progetto raggiungono determinate soglie.
title: Generatore di avvisi (Analysis Workspace)
feature: Alerts
role: User, Admin
exl-id: aae28c90-bfdf-49ff-bd38-c9ef63880bf4
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 39%

---

# Creare avvisi

>[!NOTE]
>
>Gli Avvisi intelligenti sono disponibili solo per i clienti di Adobe Analytics Prime e Adobe Analytics Ultimate.

Gli avvisi intelligenti (o semplicemente &quot;avvisi&quot;) in Adobe Analytics ti consentono di ricevere notifiche immediate quando si verificano eventi anomali nei tuoi dati. Gli avvisi sull’utilizzo delle chiamate al server sono un tipo diverso di avvisi, disponibili solo per gli amministratori di Analytics. Questi avvisi ti segnalano il rischio o il verificarsi di un superamento nei dati relativi al consumo e all’impegno delle chiamate al server. Per ulteriori informazioni, vedere [Avvisi sull&#39;utilizzo delle chiamate server](/help/admin/admin/c-server-call-usage/scu-alerts.md).)

Per informazioni di panoramica più dettagliate sugli avvisi intelligenti, consulta [Panoramica degli avvisi intelligenti](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md).

Per creare un avviso intelligente:

1. Inizia a creare un avviso accedendo al generatore di avvisi. Puoi accedere al generatore di avvisi in uno dei seguenti modi:

   * Apri un progetto in Analysis Workspace, quindi seleziona **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.
   * Apri un progetto in Analysis Workspace, quindi utilizza la seguente scelta rapida:

     `ctrl (or cmd) + shift + a`
   * Apri un progetto in Analysis Workspace, seleziona uno o più elementi in una tabella a forma libera, quindi fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Create alert from selection]**.

     Questo precompila immediatamente il generatore di avvisi per creare un avviso con le metriche e i filtri corretti.
   * Creare un avviso [da Gestione avvisi](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md#create-alerts).

   Viene visualizzato il generatore di avvisi. Questa interfaccia è familiare a coloro che hanno creato segmenti o metriche calcolate in Analytics:

   ![](assets/alert-builder.png)

1. Specificare le opzioni seguenti per configurare l&#39;avviso:

   | Opzione | Descrizione |
   |---------|----------|
   | [!UICONTROL **Titolo**] | Inserisci un nome per l’avviso. Il nome può contenere il nome del rapporto o la soglia di metrica. |
   | [!UICONTROL **Descrizione (facoltativo)**] | Specificare una descrizione per l&#39;avviso. |
   | [!UICONTROL **Granularità temporale**] | Seleziona la frequenza con cui vuoi che la metrica venga controllata: Giornaliero, Settimanale o Mensile.<p><b>Nota:</b>Nelle visualizzazioni dati con un calendario personalizzato non è supportata la granularità mensile nel generatore di avvisi.<!--true?--></p> |
   | [!UICONTROL **Recipients (Destinatari)**] | Specifica a chi deve essere inviato l’avviso. Può essere inviato a un utente o un gruppo di Analytics, a un indirizzo e-mail o a un numero telefonico.<p><b>Importante:</b>Il numero di telefono deve essere preceduto dal segno &quot;+&quot; e dal [codice paese](https://countrycode.org/).</p><p>Il messaggio e-mail che un utente riceve dopo l’attivazione di un avviso è simile al seguente:</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Data di scadenza**] | Impostare la data e l&#39;ora di scadenza dell&#39;avviso. |
   | [!UICONTROL **Invia un avviso quando**] | [!UICONTROL **Uno di questi trigger di metriche**]: trascinare le metriche (comprese le metriche calcolate) qui per creare trigger per l&#39;avviso.<p>Se non tutte le metriche, le dimensioni o i segmenti nell&#39;avviso sono compatibili con la visualizzazione dati attualmente selezionata, viene visualizzato il messaggio **&quot;components incompatibili&quot;**.</p><p>Determina la soglia che dovrà essere superata affinché venga attivato l’avviso. Puoi impostare questo valore su una soglia e quindi su una delle seguenti condizioni:</p><ul><li>anomaly exists (l’anomalia esiste)</li><li>anomaly is above expected (l’anomalia supera il valore previsto)</li><li>anomaly is below expected (l’anomalia è inferiore al valore previsto)</li><li>is above or equals (è superiore o uguale a)</li><li>is below or equals (è inferiore o uguale a)</li><li>changes by (cambia di)</li><li>Puoi impostare una soglia di 90%, 95%, 99%, 99,75% o 99,9%.</li></ul><p>[!UICONTROL **Con tutti questi filtri**]: trascina segmenti o dimensioni per aggiungere filtri. Ad esempio, l’aggiunta di un segmento &quot;Solo dispositivi mobili&quot; significherebbe che la regola si attiva solo per i dispositivi mobili. Puoi aggiungere altri filtri utilizzando un’istruzione AND. Per aggiungere una regola AND o OR, fai clic sull’icona a forma di ingranaggio.</p><p>Consulta [Avvisi intelligenti: casi d&#39;uso](/help/analyze/analysis-workspace/c-intelligent-alerts/alerts-use-cases.md), ad esempio casi d&#39;uso.</p> |
   | [!UICONTROL **Anteprima**] | L’anteprima interattiva degli avvisi mostra la frequenza approssimativa di un avviso sulla base dell’esperienza passata.<p>Ad esempio, se imposti la granularità su Ogni giorno, l’anteprima indicherà che l’avviso è stato attivato x volte per una specifica metrica negli ultimi 30 o 31 giorni.</p><p>Se sono stati attivati troppi avvisi, puoi regolare la soglia in [Alert Manager](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md) (Gestione avvisi).</p><p>![](assets/alert_preview.png)</p> |

1. Seleziona [!UICONTROL **Salva**].
