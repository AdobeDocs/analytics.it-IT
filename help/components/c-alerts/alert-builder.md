---
description: Utilizzare gli avvisi in Analysis Workspace.
title: Panoramica di Alert Builder
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 966bd9a05e6c344a62ce3f0b12df8a99ff3d7ece
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 24%

---

# Creare avvisi {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularità temporale"
>abstract="La granularità temporale si riferisce sia alla frequenza con cui verrà controllato l’avviso sia a cosa verrà incluso"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>L&#39;utilizzo degli avvisi con rilevamento delle anomalie (noti anche come _avvisi intelligenti_) è disponibile solo per le organizzazioni con un pacchetto Adobe Analytics Prime o Ultimate.

Gli avvisi in Adobe Analytics ti consentono di ricevere notifiche in base alle percentuali modificate o a punti dati specifici. A seconda del pacchetto Adobe Analytics, puoi anche utilizzare gli avvisi da attivare in base alle soglie delle anomalie. Gli avvisi sull’utilizzo delle chiamate al server sono un tipo diverso di avvisi, disponibili solo per gli amministratori di Analytics. Questi avvisi ti segnalano il rischio o il verificarsi di un superamento nei dati relativi al consumo e all’impegno delle chiamate al server. Per ulteriori informazioni, vedere [Avvisi sull&#39;utilizzo delle chiamate server](/help/admin/admin/c-server-call-usage/scu-alerts.md).

Per informazioni di panoramica più dettagliate sugli avvisi, vedere [Panoramica avvisi](/help/components/c-alerts/intellligent-alerts.md).

Per creare un avviso:

1. Inizia a creare un avviso accedendo al generatore di avvisi. Puoi accedere al generatore di avvisi in uno dei seguenti modi:

   * Apri un progetto in Analysis Workspace, quindi seleziona **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.
   * Apri un progetto in Analysis Workspace, quindi utilizza il seguente collegamento: ***Ctrl/Comando + Maiusc + A***.
   * Apri un progetto in Analysis Workspace, seleziona uno o più elementi in una tabella a forma libera, quindi fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Create alert from selection]**. Questa azione precompila immediatamente il generatore di avvisi per creare un avviso con le metriche e i filtri corretti.
   * Creare un avviso [da Gestione avvisi](/help/components/c-alerts/alert-manager.md#create-alerts).

   Viene visualizzato il generatore di avvisi. Questa interfaccia è familiare per la creazione di segmenti o metriche calcolate in Analytics:

   ![](assets/alert-builder.png)

1. Specificare le opzioni seguenti per configurare l&#39;avviso:

   | Opzione | Descrizione |
   |---------|----------|
   | [!UICONTROL **Titolo**] | Inserisci un nome per l’avviso. Il nome può contenere il nome del rapporto o la soglia di metrica. |
   | [!UICONTROL **Descrizione (facoltativo)**] | Specificare una descrizione per l&#39;avviso. |
   | [!UICONTROL **Granularità temporale**] | Seleziona la frequenza con cui vuoi che la metrica venga controllata: Oraria, Giornaliera, Settimanale o Mensile.<p><b>Nota:</b> per le suite di rapporti con un calendario personalizzato, la granularità mensile nel generatore di avvisi non è supportata.<!--true?--></p> |
   | [!UICONTROL **Recipients (Destinatari)**] | Specifica a chi deve essere inviato l’avviso. Può essere inviato a un utente o un gruppo di Analytics, a un indirizzo e-mail o a un numero telefonico.<p><b>Importante:</b> il numero di telefono deve essere preceduto da `+` e da un [codice paese](https://countrycode.org/).</p><p>Il messaggio di posta elettronica che un utente riceverebbe dopo l’attivazione di un avviso è simile al seguente:</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Data di scadenza**] | Impostare la data e l&#39;ora di scadenza dell&#39;avviso. |
   | [!UICONTROL **Invia un avviso quando**] | [!UICONTROL **Uno di questi trigger di metriche**]: trascinare le metriche (comprese le metriche calcolate) qui per creare trigger per l&#39;avviso.<p>Se non tutte le metriche, le dimensioni o i segmenti nell&#39;avviso sono compatibili con la visualizzazione dati attualmente selezionata, viene visualizzato il messaggio **&quot;components incompatibili&quot;**.</p><p>Determina la soglia che dovrà essere superata affinché venga attivato l’avviso. Puoi impostare questo valore su una soglia e quindi su una delle seguenti condizioni:</p><ul><li>anomaly exists (l’anomalia esiste)</li><li>anomaly is above expected (l’anomalia supera il valore previsto)</li><li>anomaly is below expected (l’anomalia è inferiore al valore previsto)</li><li>is above or equals (è superiore o uguale a)</li><li>is below or equals (è inferiore o uguale a)</li><li>changes by (cambia di)</li><li>Puoi impostare una soglia di 90%, 95%, 99%, 99,75% o 99,9%.</li></ul><p>[!UICONTROL **Con tutti questi filtri**]: trascina segmenti o dimensioni per aggiungere filtri. Ad esempio, l’aggiunta di un segmento &quot;Solo dispositivi mobili&quot; significherebbe che la regola si attiva solo per i dispositivi mobili. Puoi aggiungere altri filtri utilizzando un’istruzione AND. Per aggiungere una regola AND o OR, fai clic sull’icona a forma di ingranaggio.</p><p>Vedi [Avvisi - casi d&#39;uso](/help/components/c-alerts/alerts-use-cases.md) per esempio.</p> |
   | [!UICONTROL **Anteprima**] | L’anteprima interattiva degli avvisi mostra la frequenza approssimativa di un avviso sulla base dell’esperienza passata.<p>Ad esempio, se imposti la granularità temporale su giornaliera, l’anteprima può indicare che l’avviso sarebbe stato attivato per una determinata metrica x volte negli ultimi 30 o 31 giorni. La finestra di approssimazione dell&#39;anteprima viene impostata in base all&#39;impostazione della frequenza di avviso. Per le frequenze degli avvisi giornaliere, la finestra di anteprima si avvicina ai 30 giorni precedenti. Per le frequenze degli avvisi settimanali, la finestra di anteprima si avvicina alle ultime 12 settimane. Per le frequenze degli avvisi mensili, la finestra di anteprima si avvicina ai 12 mesi precedenti.</p><p>Se vengono attivati troppi avvisi, è possibile regolare la soglia in [Gestione avvisi](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Seleziona [!UICONTROL **Salva**].
