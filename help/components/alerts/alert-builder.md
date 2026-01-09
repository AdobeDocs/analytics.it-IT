---
description: Scopri come creare avvisi in Analysis Workspace.
title: Creare avvisi
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 39%

---

# Creare avvisi {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularità temporale"
>abstract="La granularità temporale si riferisce alla frequenza con cui viene controllato l’avviso."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>L&#39;utilizzo degli avvisi con rilevamento delle anomalie (noti anche come _avvisi intelligenti_) è disponibile solo per le organizzazioni con un pacchetto Adobe Analytics Prime o Ultimate.

Gli avvisi in Adobe Analytics ti consentono di ricevere notifiche in base alle percentuali modificate o a punti dati specifici. A seconda del pacchetto Adobe Analytics, puoi anche utilizzare gli avvisi da attivare in base alle soglie delle anomalie. Gli avvisi sull’utilizzo delle chiamate al server sono un tipo diverso di avvisi, disponibili solo per gli amministratori di Analytics. Questi avvisi ti segnalano il rischio o il verificarsi di un superamento nei dati relativi al consumo e all’impegno delle chiamate al server. Per ulteriori informazioni, vedere [Avvisi sull&#39;utilizzo delle chiamate server](/help/admin/tools/server-call-usage/scu-alerts.md).

Per informazioni più dettagliate sugli avvisi, vedere [Panoramica avvisi](alerts-overview.md).

Per creare un avviso:

1. Per creare un avviso, utilizza uno dei modi seguenti:

   * Apri un progetto in Analysis Workspace, quindi seleziona **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.
   * Apri un progetto in Analysis Workspace, quindi utilizza la seguente scelta rapida: ***cmd + maiusc + a*** (macOS) o ***ctrl + maiusc + a*** (Windows).
   * Apri un progetto in Analysis Workspace, seleziona uno o più elementi in una tabella a forma libera, quindi fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Create alert from selection]**. Questa azione precompila immediatamente il generatore di avvisi [Generatore di avvisi](alert-builder.md) per creare un avviso con le metriche e i filtri corretti.
   * Creare un avviso [da Gestione avvisi](/help/components/alerts/alert-manager.md#create-alerts).

   Viene visualizzato il generatore di avvisi. Questa interfaccia è familiare a quella per la creazione di segmenti o metriche calcolate in Analytics.



## Generatore di avvisi

L’interfaccia del Generatore di avvisi è simile a quella utilizzata per creare segmenti o metriche calcolate in Customer Journey Analytics:

![Interfaccia generatore di avvisi](assets/alert-builder.png)

Specifica i seguenti dettagli nel generatore di avvisi per un avviso:

| Elemento | Descrizione |
|---------|----------|
| **[!UICONTROL Title]** | Specificare un nome per l&#39;avviso. Il nome dell’avviso può contenere il nome del rapporto o la soglia delle metriche. |
| **[!UICONTROL Description (optional)]** | Inserisci una descrizione per l’avviso. |
| **[!UICONTROL Time granularity]** | Specifica quanto spesso desideri che la metrica sia controllata: ogni giorno, settimana o mese.<p> |
| **[!UICONTROL Recipients]** | Specifica dove può essere inviato l’avviso. Un avviso può essere inviato a un utente Analytics, a un gruppo Analytics, a un indirizzo e-mail non elaborato o a un numero di telefono.<p><b>Importante</b>: il numero di telefono deve essere preceduto da un `+` e da un [codice paese](https://countrycode.org/).</p><p>Un esempio dell’e-mail che un utente riceve:</p><p>![E-mail avviso](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Expiration date]** | Imposta la data e l’ora di scadenza dell’avviso. |
| **[!UICONTROL Delay]** | Il tempo necessario prima che i dati siano completi e disponibili per essere inseriti in Customer Journey Analytics varia a seconda dell’organizzazione, in genere da 3 a 9 ore dopo l’ora dell’evento dati. Affinché gli avvisi siano precisi, i dati evento per un determinato intervallo di eventi devono essere completi, il che significa che Adobe non riceve più i dati evento per l’intervallo di eventi specificato.<p>Per tenere conto di questo ritardo nel tempo di acquisizione, gli avvisi hanno un ritardo predefinito di 9 ore prima di essere inviati.</p><p>Puoi impostare il ritardo predefinito di 9 ore su qualsiasi valore compreso tra 0 e 24 ore. Tuttavia, la riduzione del ritardo al di sotto di 9 ore può significare che stai eseguendo un rapporto con dati incompleti, il che si traduce in informazioni di avviso imprecise.</p><p>Quando configuri la riduzione del ritardo, tieni presente quanto segue:</p><ul><li>**Comprendere la disponibilità dei dati rispetto alla completezza dei dati**: tutti i dati batch vengono acquisiti in un set di dati Experience Platform solo dopo un periodo di 3-9 ore. Affinché gli avvisi siano precisi, l’acquisizione dei dati deve essere completa, con tutti i dati batch disponibili nel set di dati.</li><li>**Determina il tempo necessario per il completamento e la disponibilità dei dati nel set di dati**: i tempi di acquisizione dei dati variano a seconda dell’organizzazione. Verifica che il ritardo scelto per la consegna degli avvisi sia lo stesso o meno frequente del tempo necessario per rendere disponibili i dati batch nel set di dati di Platform<!--add link? -->.</li><p>**Suggerimento:** il modo più accurato per conoscere il tempo necessario per il completamento e l’acquisizione di tutti i dati batch nel set di dati di Platform consiste nel consultare i data engineer della tua organizzazione.</p><p>In alternativa, puoi avere un’idea generale di quanto tempo ci vuole affinché la consegna batch nell’organizzazione sia disponibile nel set di dati di Experience Platform. Creazione della seguente tabella a forma libera in Analysis Workspace:</p><ol><li>In una tabella a forma libera in Analysis Workspace, aggiungi una metrica [!UICONTROL **Eventi**] e una dimensione [!UICONTROL **Giorno**].</li><li>Suddividi la dimensione [!UICONTROL **Giorno**] utilizzando una dimensione [!UICONTROL **Ore**].<p>Le ore senza dati vengono visualizzate come 0.</p></li></ol><li>**Conto degli errori nei calcoli**: se riduci il ritardo predefinito, configura il ritardo per almeno un&#39;ora in più rispetto al tempo necessario all&#39;organizzazione per completare l&#39;acquisizione dei dati. Ad esempio, in caso di ritardo di 3 ore prima del completamento dell’acquisizione dei dati, imposta il ritardo su 4 ore.</li> |
| **[!UICONTROL Send an alert when]** | [!UICONTROL **Uno di questi trigger di metriche**]: <ol><li>Trascina le metriche (comprese le metriche calcolate) per creare i trigger per l’avviso.<p>Se non tutte le metriche, dimensioni o segmenti nell&#39;avviso sono compatibili con la suite di rapporti attualmente selezionata, viene visualizzato un messaggio di *componenti non compatibili*.</p><p>Determina la soglia (per un’anomalia) che la metrica deve superare o il valore (in caso di sopra, sotto, è uguale o modifica della percentuale) da utilizzare prima di impostare un avviso.</li><li>Seleziona una delle seguenti condizioni:<ul><li>esiste un’anomalia</li><li>anomalia è superiore al previsto</li><li>anomalia inferiore al previsto</li><li>è superiore o uguale a</li><li>è inferiore o uguale a</li><li>modifiche di</li></ul></li><li>Selezionate un valore di soglia o immettete un valore.</li></ol>[!UICONTROL **Con tutti questi filtri**]: trascina segmenti o dimensioni per aggiungere filtri all&#39;avviso. Ad esempio, l&#39;aggiunta di un segmento *Solo dispositivi mobili* implica che la regola viene attivata solo per i dispositivi mobili. Puoi aggiungere altri filtri utilizzando un’istruzione AND. Per aggiungere una regola AND o OR, fai clic sull’icona a forma di ingranaggio.</p><p>Consulta [Avvisi: casi d’uso](alerts-use-cases.md) per esempi di casi d’uso.</p> |
| **[!UICONTROL Preview]** | L’anteprima interattiva degli avvisi mostra la frequenza con cui, approssimativamente, un avviso viene attivato in base all’esperienza passata.<p>Ad esempio, se imposti la granularità temporale su giornaliera, l’anteprima può indicare che l’avviso sarebbe stato attivato per una determinata metrica x volte negli ultimi 30 o 31 giorni.</p><p>Se vengono attivati troppi avvisi, è possibile regolare la soglia in [Gestisci avvisi](alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |
