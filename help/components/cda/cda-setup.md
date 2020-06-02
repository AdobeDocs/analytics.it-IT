---
title: Configurazione di Analytics tra dispositivi
description: Scopri come configurare Analytics cross-Device dopo aver soddisfatto i prerequisiti.
translation-type: tm+mt
source-git-commit: d847fb9dc1427727a0162be993ddc4a73c52f192
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 1%

---


# Configurazione di Analytics tra dispositivi

Una volta soddisfatti tutti i prerequisiti, attenetevi alla seguente procedura per abilitare l&#39;analisi tra dispositivi. Per seguire questa procedura, devi appartenere a un gruppo Amministratore profilo di prodotto o avere privilegi di amministratore in Adobe Analytics.

>[!IMPORTANT] Tutti i prerequisiti devono essere soddisfatti prima di seguire questi passaggi. Se tutti i prerequisiti non sono soddisfatti, la funzione non è disponibile o non funziona. Consultate Analisi [](cda-home.md) multi-dispositivo per prerequisiti e limitazioni.

## Scegliete la suite di rapporti per più dispositivi che verrà abilitata per CDA

Quando l’organizzazione dispone del provisioning per l’utilizzo di CDA, potete scegliere quale suite di rapporti utilizzare. Questa scelta può essere comunicata tramite il tuo Adobe Account Manager. Adobe quindi abilita la suite di rapporti selezionata per l&#39;elaborazione CDA.

## Creare una suite di rapporti virtuali per dispositivi diversi per visualizzare la visualizzazione su più dispositivi

Gli amministratori con accesso per creare suite di rapporti virtuali possono creare suite di rapporti virtuali CDA come segue:

1. Andate a [experience.adobe.com](https://experiencecloud.adobe.com) ed effettuate l&#39;accesso utilizzando le credenziali AdobeID.
2. Fate clic sull&#39;icona a 9 griglie nella parte superiore, quindi fate clic su Analytics.
3. Passa il cursore del mouse sui componenti in alto, quindi fai clic su Suite di rapporti virtuale.
4. Fai clic su Aggiungi.
5. Immettete un nome per la suite di rapporti virtuali e accertatevi che sia selezionata la suite di rapporti abilitata per CDA.
6. (Facoltativo) Applicare un segmento alla suite di rapporti virtuali. Ad esempio, puoi applicare un segmento che limita la suite di rapporti virtuali alle date successive all&#39;attivazione di CDA e all&#39;inizio della cucitura. Questo segmento consente agli utenti di visualizzare solo gli intervalli di date cuciti all&#39;interno della VRS.
7. Fate clic sulla casella di controllo &quot;Abilita elaborazione tempo rapporto&quot; per abilitare diverse opzioni, tra cui Analisi multi-dispositivo.
8. Fate clic sulla casella di controllo &quot;Stitch User Visits Between Devices&quot; (Stitch Visite utente tra dispositivi).
9. Fate clic su Continue (Continua), completate la configurazione della suite di rapporti virtuali, quindi fate clic su Save (Salva).

![Casella di controllo CDA](assets/cda-checkbox.png)

## Aggiunte e modifiche alle suite di rapporti virtuali su più dispositivi

Quando Analytics cross-device è abilitato su una suite di rapporti virtuale, prendi nota delle seguenti modifiche:

* Accanto al nome della suite di rapporti virtuale viene visualizzata una nuova icona cross-device. Questa icona è esclusiva per le suite di rapporti virtuali su più dispositivi.
* È disponibile una nuova dimensione con l&#39;etichetta &quot;Stato identificato&quot;. Questa dimensione determina se l’Experience Cloud ID su tale hit è noto dal grafico del dispositivo in quel momento.
* Sono disponibili nuove metriche con etichetta &#39;Persone&#39; e &#39;Dispositivi univoci&#39;.
* La metrica &quot;Visitatori unici&quot; non è disponibile, in quanto viene sostituita con &quot;Persone&quot; e &quot;Dispositivi unici&quot;.
* Durante la creazione di segmenti, il contenitore del segmento &quot;Visitatore&quot; viene sostituito con un contenitore &quot;Persona&quot;.

## Modello di area di lavoro CDA

Adobe offre un modello per visualizzare i dati essenziali sulle prestazioni cross-device.

1. Andate a [experience.adobe.com](https://experiencecloud.adobe.com) ed effettuate l&#39;accesso utilizzando le credenziali AdobeID.
1. Fate clic sull&#39;icona a 9 griglie nella parte superiore, quindi fate clic su Analytics.
1. Fate clic [!UICONTROL Workspace] in alto, quindi fate clic su [!UICONTROL Create New Project].
1. Individuare il &quot;IQ del viaggio: Modello Analisi cross-device&quot;, quindi fai clic su [!UICONTROL Create].
1. Se richiesto, modificate la suite di rapporti in una che supporti CDA.

Viene creato un progetto di Analysis Workspace contenente diversi pannelli. Nella parte superiore, viene visualizzato un sommario e un’introduzione che consentono di visualizzare il contesto del rapporto e di passare ai singoli rapporti. Fate clic su un collegamento all’interno del sommario o espandete la struttura di navigazione di un pannello per visualizzarli.

<!-->The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md<-->

* **Nota speciale per i membri del Co-op Graph**: Mostra quale parte della suite di rapporti contiene i visitatori nelle aree in cui è supportato il grafico della cooperativa e nelle aree in cui non è supportato.
* **Identificazione degli utenti**: Mostra la frequenza con cui i visitatori del sito vengono identificati utilizzando metodi basati su Analisi cross-device.
* **Misurazione della dimensione** del pubblico: Mostra un confronto tra &quot;Dispositivi univoci&quot; e &quot;Persone&quot;. La proporzione di questi due numeri è nota come &#39;compressione tra dispositivi&#39;, una metrica calcolata visibile in questo pannello. Questa metrica di compressione dipende da un&#39;ampia gamma di fattori:
   * Usando il grafico Co-op o il grafico Privato: In generale, le organizzazioni che utilizzano la cooperativa dispositivi tendono a visualizzare tassi di compressione migliori rispetto alle organizzazioni che utilizzano il grafico privato.
   * Velocità di accesso: Più utenti accedono al sito, più Adobe è in grado di identificare e unire i visitatori tra i dispositivi. Anche i siti con un basso tasso di accesso hanno bassi tassi di compressione.
   * Copertura Experience Cloud ID: È possibile unire solo i visitatori con un ECID. Una percentuale inferiore di visitatori del sito che utilizza un ECID è correlata a tassi di compressione più bassi.
   * Utilizzo di più dispositivi: Se i visitatori del sito non utilizzano più dispositivi, è possibile visualizzare percentuali di compressione più basse.
   * Granularità del reporting: La compressione per giorno è generalmente inferiore alla compressione per mese o anno. Le possibilità di un singolo di utilizzare più dispositivi diventano più ridotte entro un singolo giorno rispetto a un intero mese. Segmentazione, filtraggio o utilizzo di dimensioni di suddivisione può anche mostrare una minore frequenza di compressione.
* **Segmenti** basati sulle persone: Contiene un elenco a discesa dei segmenti che consente di visualizzare dati specifici per il dispositivo. Questo pannello incoraggia la sperimentazione con i segmenti per vedere in che modo i report possono essere influenzati dall&#39;inclusione o esclusione di tipi di dispositivi.
* **Analisi del percorso** cross-device: Fornisce rapporti di flusso e di abbandono in base al tipo di dispositivo.
* **Attribuzione** tra dispositivi: Combinate le funzioni di IQ viaggio e IQ attribuzione.
* **Altri suggerimenti e trucchi**: Argomenti utili intorno a CDA che ti permettono di ottenere di più dall&#39;utilizzo.
