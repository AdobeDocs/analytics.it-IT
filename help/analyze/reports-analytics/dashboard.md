---
description: Un dashboard è una raccolta di miniature di rapporti denominati reportlet. Un dashboard è particolarmente utile quando contiene minirapporti correlati che ti forniscono panorami completi su alcuni aspetti del sito, ad esempio metodi di ricerca, profili visitatore e così via.
subtopic: Dashboards
title: Dashboard e minirapporti
uuid: 7a7b3bc9-0a3c-49b0-9168-e2878ae67b97
role: User, Admin
exl-id: 399765a3-0f90-46b9-b62e-9f41d98eaa9a
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '1692'
ht-degree: 2%

---

# Dashboard e minirapporti

Un dashboard è una raccolta di miniature di rapporti denominati reportlet. Un dashboard è particolarmente utile quando contiene minirapporti correlati che ti forniscono panorami completi su alcuni aspetti del sito, ad esempio metodi di ricerca, profili visitatore e così via.

## Dashboard e minirapporti {#concept_8CD3ACA2830A4994A68A31D8773B57E0}

Un dashboard è una raccolta di rapporti miniature denominata *`reportlets`*. Un dashboard è particolarmente utile quando contiene minirapporti correlati che ti forniscono panorami completi su alcuni aspetti del sito, ad esempio metodi di ricerca, profili visitatore e così via.

Puoi aggiungere la maggior parte dei rapporti di marketing a una dashboard, compresi i rapporti graficamente intensi come [!UICONTROL Fallout Report], [!UICONTROL Conversion Funnel Report] e [!UICONTROL Pathfinder Report].

Puoi anche impostare una dashboard come pagina di destinazione, condividere dashboard con altri utenti e pianificarle per la consegna. Se non impostate una dashboard (o un segnalibro) come pagina di destinazione, viene visualizzato il dashboard [!UICONTROL My Recommended Reports]. **[!UICONTROL My Recommended Reports]** mostra il  **[!UICONTROL Key Metrics]** rapporto e i cinque rapporti visualizzati più frequentemente. È dinamico e si basa sui report attuali che vengono maggiormente visualizzati.

Tieni presente che alcuni rapporti visualizzati di frequente non possono essere dashboard e non verranno visualizzati. Questi includono:

* Rapporti sul rilevamento delle anomalie
* Rapporti di analisi dei contributi
* Rapporti di fallout
* Rapporti sul percorso
* Rapporti in tempo reale
* Altre dashboard

>[!NOTE]
>
>Il dashboard **[!UICONTROL Site Overview]** non è più elencato in Reports &amp; Analytics. Tuttavia, ci sono ancora un paio di circostanze in cui vedrai alcuni o tutti i suoi minirapporti.

* Se hai, ad esempio, solo tre rapporti visualizzati di frequente, Reports &amp; Analytics prenderà due rapporti dalla dashboard Panoramica sito per completare il dashboard **[!UICONTROL My Recommended Reports]**.
* Anche le nuove suite di rapporti di marchio inizialmente includeranno i minirapporti Panoramica sito, fino a quando non saranno sostituiti dai rapporti visualizzati di frequente. Tuttavia, il dashboard verrà ora chiamato **[!UICONTROL My Recommended Reports]**.

Oltre alle dashboard create, per ogni utente sono incluse le seguenti dashboard preconfigurate:

**[!UICONTROL Components]>  [!UICONTROL All components] >  [!UICONTROL Dashboards] >  [!UICONTROL Shared Dashboards] >[!UICONTROL Local Sites]**

Questo dashboard personalizzabile consente di rilasciare minirapporti nel modello fornito.

**[!UICONTROL Components]>  [!UICONTROL All components] >  [!UICONTROL Dashboards] >  [!UICONTROL Shared Dashboards] >[!UICONTROL Site Operations Dashboard]**

Questa dashboard offre una panoramica delle metriche chiave correlate alle operazioni sul sito web. I rapporti su questo dashboard includono:

* Esci da pagine
* Pagine più popolari
* Sezioni più popolari del sito
* Report KPI/Gage
* Rapporto testo
* Report di riepilogo della società

Utilizza [!UICONTROL Dashboard Manager] per modificare e gestire le dashboard e abilitarle ad DirectAccess.

Consulta [Gestione delle dashboard](/help/analyze/reports-analytics/dashboard-manage.md).

## Creare un dashboard {#task_54EFBED59BDC4418A919E6EF84AB9CFF}

Passaggi che descrivono come creare un dashboard.

<!-- 

t_dashboard_add.xml

 -->

Prima di aggiungere un rapporto (come minirapporti) a una dashboard, definisci il layout del dashboard.

1. Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Fai clic su **[!UICONTROL Add Dashboard]**.
1. Digitate un nome per il dashboard.
1. Fai clic su **[!UICONTROL 3 x 2]** o **[!UICONTROL 2 x 2]** per specificare il numero di minirapporti desiderati nella pagina del dashboard.
1. Configura il layout della pagina del dashboard:

   * **[!UICONTROL Add Page]**: Aggiunge una pagina vuota al dashboard in cui è possibile trascinare il contenuto per creare minirapporti.
   * **[!UICONTROL Paper]**: Consente di specificare un formato carta, ad esempio orizzontale, verticale e A4.
   * **[!UICONTROL Find Content]**: Consente di cercare il contenuto nei  [!UICONTROL Add Content] menu  [!UICONTROL Dashboard Contents] e .

1. Aggiungi il contenuto disponibile al dashboard trascinando gli elementi nell’area di lavoro del reportlet.

   Consulta [Creazione di un minirapporti](/help/analyze/reports-analytics/dashboard.md#task_EC3AFBBAA51C45CEBAF632F841C305B3) e [Modifica delle impostazioni del dashboard](/help/analyze/reports-analytics/dashboard.md#task_90D7FAC1CC3E4DB786B4C87CC33B5459).
1. Fai clic su **[!UICONTROL Save.]**

   Il salvataggio di un dashboard lo rende disponibile nel menu **[!UICONTROL Dashboard]**. Il nuovo dashboard è disponibile anche in [!UICONTROL Dashboard Manager] ( **[!UICONTROL Favorites]** > **[!UICONTROL Dashboards]** > **[!UICONTROL Manager]**), dove puoi modificare, organizzare, condividere, pianificare, archiviare dashboard e altro ancora. (Consulta [Gestione delle dashboard](/help/analyze/reports-analytics/dashboard-manage.md).)

1. (Facoltativo) Per impostare il dashboard come pagina di destinazione, fai clic su **[!UICONTROL More Options]** > **[!UICONTROL Set as Landing Page]**.

## Creare un reportlet {#task_EC3AFBBAA51C45CEBAF632F841C305B3}

Passaggi che descrivono come creare un reportlet. Una volta creato un reportlet, questo può essere visualizzato in un dashboard.

<!-- 

t_dashboard_add_report.xml

 -->

1. Esegui un report.
1. Fai clic su **[!UICONTROL Dashboard.]**
1. Nella pagina [!UICONTROL Add Reportlet] denomina il rapporto, quindi seleziona un dashboard da **[!UICONTROL Place in Dashboard]**.
1. (Facoltativo) Configura l’intervallo di date.

   * **[!UICONTROL Rolling]**: Modifica la data quando passa il tempo, in base all’intervallo di tempo (giornaliero, mensile e così via). Ad esempio, se oggi è il 17 gennaio, puoi impostare le date per il 15-16 gennaio. Quindi se selezioni **[!UICONTROL Rolling]**, il 27 gennaio il minirapporti visualizza i dati per il 25 - 26 gennaio.
   * **[!UICONTROL Fixed]**: Impedisce che la data prosegua con il passare del tempo.

1. (Facoltativo) Ignora la lista di distribuzione di pubblicazione.

   **[!UICONTROL Publishing List Override]**: Se abiliti questa opzione, la suite di rapporti a cui si fa riferimento in questo reportlet viene sempre utilizzata quando distribuita in un elenco di pubblicazione. Se disattivi questa opzione, la suite di rapporti identificata nell’elenco di pubblicazione sostituisce la suite di rapporti in questo reportlet.

1. Fai clic su **[!UICONTROL Create New]**.

   Il minirapporti viene aggiunto al menu **[!UICONTROL Dashboard Contents]** nell’editor del dashboard.

## Aggiungere contenuto a un dashboard {#task_90D7FAC1CC3E4DB786B4C87CC33B5459}

Passaggi che descrivono come aggiungere contenuti da altre dashboard e dashboard condivise. Puoi anche aggiungere contenuto da origini personalizzate ed esterne, come testo e immagini.

<!-- 

t_dashboard_content.xml

 -->

1. Apri un dashboard, quindi fai clic su **[!UICONTROL Layout]**.
1. Fai clic su **[!UICONTROL Add Content]**, quindi trascina gli elementi nel dashboard.

   Il menu [!UICONTROL Add Content] visualizza il contenuto del reportlet da altre dashboard, dashboard legacy e dashboard condivise.

   >[!NOTE]
   >
   >Il limite attuale al numero di pagine in un dashboard è 30.

   **Report personalizzati**

   *Contenuto dati:*

   * Riepilogo società: Visualizza le visualizzazioni di pagina per più suite di rapporti e metriche selezionate.
   * Misura della metrica: Visualizza un indicatore che indica dove si trovano le cifre delle metriche in relazione alle soglie specificate.

      Puoi selezionare una metrica, un tipo di grafico, un intervallo di colori e valori di soglia. Se il conteggio della metrica aumenta al di sopra della soglia Maggiore di, il contatore lo indica nel minirapporti, utilizzando il colore sopra il campo Maggiore di. Se il conteggio della metrica è al di sotto della soglia Minore di , il contatore lo indica nel minirapporti, utilizzando il colore sopra il campo Minore di . I valori specificati in questi campi sono il valore contabile della metrica, ad esempio il numero di visualizzazioni di pagina, gli importi in dollari, le visualizzazioni del carrello e così via. (Non utilizzare caratteri speciali).
   * Riepilogo suite di rapporti: Visualizza una metrica selezionata e i relativi valori totali o alti e bassi per una suite di rapporti.
   * Riepilogo utilizzo: Mostra i dati relativi all’accesso all’interfaccia da parte delle persone dell’organizzazione. Questo reportlet può mostrare i dati in base all’accesso del nome utente, all’accesso ai rapporti o alla suite di rapporti.
Puoi creare i seguenti reportlet di contenuto utente fornendo gli URL. Se un&#39;immagine o un altro URL di risorse non inizia con https://, gli utenti di Internet Explorer potrebbero visualizzare un avviso relativo ai contenuti misti. È possibile disattivare l’avviso per i contenuti misti nelle impostazioni di protezione del browser.

   *Contenuto utente:*

   * Relazione esterna: Consente di aggiungere un rapporto esterno nei formati .xml e .csv .
   * HTML: Consente di aggiungere un reportlet HTML personalizzato. L’URL deve utilizzare HTTP o HTTPS. In caso contrario, viene visualizzato un errore `Specified URL could not be retrieved`. Nel contenuto del documento, tutti i tag con attributi che utilizzano i dati: e javascript: i protocolli vengono rimossi. Vengono rimossi script, frame, applet, gestori eventi, flash e altri oggetti incorporati. Se le risorse vengono specificate utilizzando non HTTPS, agli utenti di IE viene visualizzato un avviso relativo ai contenuti misti.
   * Immagine: Consente di creare un dashboard da un URL immagine. Se l’URL utilizza il protocollo HTTP, Internet Explorer genera un avviso relativo a contenuti misti. L’utilizzo di un URL con HTTPS rimuove l’avviso. Tutti gli altri protocolli emettono un errore `Specified URL could not be retrieved`.
   * RSS: Consente di aggiungere un feed Web RSS. Deve essere HTTP o HTTPS. In caso contrario, viene visualizzato un errore `Specified URL could not be retrieved`.
   * Testo: Consente di utilizzare il codice XHTML per creare dati personalizzati. Utilizza HTTP o HTTPS per un URL. Le immagini utilizzate nel contenuto del reportlet di testo con protocollo HTTP fanno sì che gli utenti IE ricevano un avviso relativo ai contenuti misti. Le immagini incluse utilizzando altri protocolli non vengono visualizzate nel reportlet.

   **Dashboard personali**

   Elenca le dashboard aggiornate da cui è possibile spostare il contenuto nel nuovo dashboard.

   **Dashboard legacy**

   Elenca le dashboard condivise da cui è possibile spostare il contenuto nel nuovo dashboard.

   **Dashboard condivisi**

   Elenca le dashboard legacy dalle quali è possibile spostare il contenuto nel nuovo dashboard. Le dashboard legacy sono utili se desideri mantenere la formattazione del dashboard rispetto alle versioni precedenti.

   **Contenuto del dashboard**

   Visualizza gli elementi già aggiunti al dashboard.

1. Fai clic su **[!UICONTROL Save.]**

## Modificare i dati del dashboard e del reportlet {#task_B460CCD70D9F40FCAC6BBC1C044CC460}

È possibile modificare le impostazioni dei dati a livello di dashboard o di minirapporti. Ad esempio, puoi modificare la suite di rapporti, bloccarla, modificare le date, applicare segmenti e così via. È inoltre possibile personalizzare un dashboard inserendo l’istruzione sulla riservatezza della propria azienda e includendo dati HTML, XML, API Web e CSV nei minirapporti personalizzati.

<!-- 

t_dashboard_edit.xml

 -->

**Per modificare i dati del dashboard e del reportlet**

1. Fai clic su **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Dashboards]** > *nome del dashboard* per aprire un dashboard.
1. Fai clic su **[!UICONTROL Layout]**.

| Su | Esegui questa operazione |
|--- |--- |
| Modificare la suite di rapporti di un dashboard | Fai clic sul menu nell’intestazione dell’Experience Cloud, quindi seleziona una suite di rapporti. |
| Modificare la suite di rapporti di un reportlet | Nel minirapporti, fai clic sul nome della suite di rapporti, quindi seleziona una suite di rapporti dal menu [!UICONTROL Report Suite] . |
| Applicazione di un segmento a un dashboard | Nell’intestazione dell’Experience Cloud, fai clic su [!UICONTROL Show Segments], quindi seleziona un segmento. |
| Applicare un segmento a un reportlet | Nel dashboard, fai clic su Layout per modificare un dashboard.   Nel minirapporti, fai clic sul nome della suite di rapporti, quindi seleziona un valore dal campo Segmento e fai clic su Aggiorna. |
| Bloccare una suite di rapporti (impedisce la modifica della suite di rapporti in un reportlet) | Nel minirapporti, fai clic sul nome della suite di rapporti, quindi abilita [!UICONTROL Lock Report Suite]. Fai clic su Aggiorna. |
| Modificare una data di reporting | Per un dashboard, fare clic sul calendario. (Tutti i minirapporti nel dashboard riflettono la modifica.)<br>Per un reportlet, fai clic sul collegamento della data, quindi configura il calendario. |
| Assegnare un nome a un dashboard | Apri un dashboard, quindi fai clic su [!UICONTROL More] > [!UICONTROL Rename]. |
| Visualizzare un archivio dashboard | Fai clic su  [!UICONTROL More] >  [!UICONTROL View Archive]. |
| Imposta il dashboard come pagina di destinazione | In un dashboard, fai clic su [!UICONTROL More] > [!UICONTROL Set As Landing Page]. |
| Scaricare un dashboard | In un dashboard, fai clic su [!UICONTROL More] > Scarica. |
| Stampa di un dashboard | In un dashboard, fai clic su [!UICONTROL More] > Stampa. |
| Salvare un dashboard | In un dashboard, fai clic su Salva con nome, quindi specifica un nome. |

## Assegna un marchio a un dashboard {#task_603BDE7700B945699AF5514C2DEB81F7}

Passaggi che descrivono come caricare un’immagine da visualizzare in un dashboard.

<!-- 

t_dashboard_branding.xml

 -->

1. **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Company settings]**.
1. Nella pagina [!UICONTROL Company Settings], fai clic su **[!UICONTROL Co-Brand the Adobe Experience Cloud]**.
1. Fai clic su **[!UICONTROL Enable Co-Branding]**.
1. Sfoglia per caricare l&#39;immagine, quindi fai clic su **[!UICONTROL Save.]**

   Per ottenere i migliori risultati quando visualizzi l&#39;immagine in un browser, carica un&#39;immagine 100px per 30px. Per ottenere risultati migliori nell’output PDF, carica un’immagine da 417 px per 125 px (300 dpi). Le immagini di dimensioni eccessive vengono ridotte e vengono mantenute le proporzioni.

## Utilizzare i segmenti con le dashboard {#concept_ED030C3713D54D03971FB7B209285750}

Le dashboard, come la maggior parte dei report in Adobe Analytics, possono utilizzare i segmenti per recuperare i dati desiderati.

<!-- 

segments_dashboards.xml

 -->

I segmenti possono essere applicati su due livelli: su un intero dashboard o su un report specifico.

* **Livello** del minirapporto: Fai clic su  **[!UICONTROL Layout]**, quindi sulla suite di rapporti del minirapporto che desideri segmentare. Viene visualizzata una finestra modale che consente di aggiungere o modificare i segmenti utilizzati dal rapporto.
* **Livello** dashboard: Fai clic sull’icona Segmento nella navigazione a sinistra, controlla i segmenti che desideri utilizzare e fai clic su Applica. I segmenti selezionati sovrascrivono e sostituiscono tutti i segmenti a livello di minirapporto.
