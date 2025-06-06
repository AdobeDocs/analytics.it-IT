---
description: Domande frequenti su Advertising Analytics.
title: Domande frequenti per l’analisi della pubblicità
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '1294'
ht-degree: 1%

---

# Domande frequenti

## Accesso/Diritti {#access}

+++ Per accedere a questa funzionalità, devo essere un cliente di Adobe Advertising Cloud o Adobe Advertising Cloud (AMO)?

No, questa funzionalità è disponibile per i clienti non Advertising Cloud e AMO.

I clienti AMO possono sfruttare l’integrazione Analytics-AMO esistente; non potranno utilizzare Ad Analytics.

+++

+++ Quali SKU di Adobe Analytics ti autorizzano a utilizzare Advertising Analytics?

Advertising Analytics è disponibile per Adobe Analytics

* [Seleziona](https://www.adobe.com/it/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/it/data-analytics-cloud/analytics/prime.html)

* [Ultimate](https://www.adobe.com/it/data-analytics-cloud/analytics/ultimate.html)

+++

+++ Devo pagare un supplemento per utilizzare Advertising Analytics?

No, al di fuori di un provisioning SKU appropriato, Advertising Analytics non comporta costi aggiuntivi.

+++

+++ Advertising Analytics conta rispetto all’utilizzo delle chiamate al server?

No, Advertising Analytics utilizza un tipo di origine dati speciale che non comporta costi di chiamata al server.

+++

+++ Se utilizzo già Advertising Cloud/AMO, posso continuare a utilizzare la funzionalità Advertising Analytics?

Tutti gli account compatibili dei motori di ricerca passeranno ad Advertising Analytics e verranno visualizzati in sola lettura. Tutte le modifiche o gli aggiornamenti devono essere gestiti in Advertising Cloud/AMO.

+++

+++ Possiedo lo SKU corretto, ma non posso accedere ad Advertising Analytics. Perché?

Advertising Analytics è disponibile solo per gli amministratori di Adobe Analytics; tuttavia, gli amministratori possono concedere l’accesso agli utenti non amministratori. Contatta l’amministratore per i diritti di accesso.

+++

## Utilizzo di Advertising Analytics {#using}

+++ Quali account del motore di ricerca sono inclusi in Advertising Analytics?

Gli account dei motori di ricerca includono Google Ads e Microsoft Advertising.

+++

+++ Dove posso trovare l’accesso ad Advertising Analytics?

Dopo aver effettuato l&#39;accesso ad Adobe Analytics, passa a [!UICONTROL Admin]. Quindi seleziona [!UICONTROL Advertising Analytics] per aggiungere gli account del motore di ricerca.

+++

+++ Come vengono raccolti e trasmessi i dati in Analytics?

Advertising Analytics utilizza una serie di API personalizzate per trasmettere ad Analytics i dati dai motori di ricerca tramite Adobe Advertising Cloud.

+++

+++ Quali dati di ricerca ottengo con questa integrazione?

Otterrai

* Impression
* Clic
* Costi
* punteggio di qualità
* Posizione media direttamente dai motori di ricerca, nonché
* Istanze AMO ID (fai clic su Istanze).

+++

+++ Posso raggruppare i dati di Advertising Analytics per altri dati di Analytics (metriche/dimensioni)?

No, i dati di ricerca non elaborati verranno inseriti come set di dati indipendente. Tuttavia, esiste una versione Istanze dei dati di clic che può essere suddivisa per altri dati di Analytics.

+++ Qual è la definizione dei vari indicatori di stato per i miei account (In sospeso, Attivo, In pausa, ecc.)? Ciascuno di questi indicatori di stato identifica la fase del ciclo di vita di ciascun account del motore di ricerca.

* [!UICONTROL Pending]
* [!UICONTROL Paused] significa che l&#39;account è stato precedentemente configurato ma è stato messo in uno stato inattivo.
* [!UICONTROL Active] significa che l&#39;account è stato configurato completamente e sta estraendo i dati di ricerca.

+++

+++ Sto tentando di mappare i miei account Advertising Analytics su una suite di rapporti specifica, ma non è disponibile nella finestra modale Suite di rapporti. Perché?

Prima di poter assegnare una suite di rapporti a un account Advertising Analytics, è necessario eseguire il provisioning della suite di rapporti desiderata per il reporting di Advertising Analytics [&#128279;](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
Questa operazione viene eseguita tramite una pagina Amministratore separata accessibile da: Amministratore > Suite di rapporti > `[select report suite]` > Modifica impostazioni > Configurazione Advertising Analytics.

+++

+++ È possibile assegnare una suite di rapporti virtuale a un account Advertising Analytics?

Le suite di rapporti virtuali non raccolgono dati, pertanto non puoi mappare direttamente un account Advertising Analytics a una suite di rapporti virtuale. Tuttavia, puoi mappare l’account Advertising Analytics alla suite di rapporti principale della suite di rapporti virtuale in cui desideri visualizzare i dati. Le metriche del motore di ricerca (clic/costo/impression) potrebbero non essere visualizzate nella suite di rapporti virtuali, a meno che non includi una condizione &quot;o&quot; nella logica del segmento in base all’AMO ID (o alla relativa classificazione). Esempio: l’aggiunta di &quot;tutti gli hit in cui esiste un AMO ID&quot; includerebbe le metriche del motore di ricerca nel segmento.

+++

+++ Le metriche di Advertising Analytics sono segnalabili nel report *Marketing Channels*?

No, non sono inclusi nel rapporto Canali di marketing.

+++

+++ Quando vengono estratti i dati di ricerca in Analytics?

I dati di ricerca vengono estratti dai motori di ricerca intorno alle 6 del mattino (06:00) nel fuso orario del centro dati di Analytics. ovvero quando i dati AMO vengono raccolti e inseriti nella suite di rapporti; Viene quindi convertito nel fuso orario della suite di rapporti come parte dell’inserimento dei dati in Analytics.

+++

+++ Cosa è possibile acquisire *prima del clic*? Portiamo impressioni, costi, posizione media, ecc.? anche senza clic?

L’AMO ID acquisirà le metriche del motore di ricerca: impression, costo, clic, posizione media e punteggio di qualità medio. Se non ci sono clic ma sono presenti impression, i dati di impression/posizione/punteggio di qualità verranno comunque inviati ad Analytics. In genere, se non ci sono clic, allora non c&#39;è anche alcun costo.

+++

+++ A che livello vengono acquisiti questi dati? *Visitatore? Hit?*

Le metriche del motore di ricerca vengono acquisite a livello di hit e collegate all’AMO ID (e alle relative classificazioni). Si tratta di dati a livello di riepilogo e non collegati a visite/visitatori. Di conseguenza, le metriche del motore di ricerca possono essere utilizzate solo in segmenti con ambito a livello di hit e basati sull’AMO ID (o sulle relative classificazioni).

L’AMO ID viene anche acquisito nella pagina di destinazione dell’hit per quella pagina (che lo collega alla visita/visitatore) e persiste a valle per ottenere credito per altre metriche di Analytics (fino alla scadenza o alla sovrascrittura da parte di un nuovo AMO ID). È completamente incorporato nel set di dati come qualsiasi altro eVar.

+++

+++ Acquisiamo solo google.com o *versioni nazionali* (come google.co.uk, google.it, google.fr o google.de)?

La classificazione della piattaforma di annunci acquisisce questi valori: &quot;Google Adwords&quot; e &quot;Bing Ads&quot;. Una best practice comune consiste nell’includere il codice del paese come parte della denominazione delle campagne. Puoi quindi filtrare verso il basso o segmentare (ad esempio, se tutte le campagne iniziano con country code_, la creazione di un segmento in cui Campagne (AMO ID) inizia con &quot;UK_&quot; ti fornirebbe solo i dati per il Regno Unito).

+++

+++ La metrica &quot;AMO Cost&quot; è il costo pagato per ogni parola chiave/annuncio riportato dal motore di ricerca. È il costo netto o il costo lordo?

Il &quot;costo AMO&quot; è solo il costo pagato ai motori di ricerca. Non sono incluse le tariffe per agenzie o piattaforme di ottimizzazione/gestione delle ricerche.

+++

+++ È previsto l&#39;inclusione di altri canali pubblicitari, ad esempio *Visualizzazione* o *Social*?

No, al momento non abbiamo piani per questi altri canali nella roadmap.

+++


## Tracciamento automatico e manuale {#section_7437C4698A6D482EB7ED94A948390119}

+++ Durante la configurazione del mio account Advertising, viene indicato che il *tracciamento automatico* può causare conseguenze indesiderate. Che tipo di conseguenze possono verificarsi?

La modalità automatica tenta di aggiungere i parametri URL alla fine dei modelli di tracciamento o degli URL di destinazione nel formato corretto. Tuttavia, è tua responsabilità verificare che i parametri URL aggiunti persistano correttamente nella pagina di destinazione finale. La modalità automatica può inserire parole chiave nell’URL di destinazione e il server web potrebbe non supportare parole chiave con caratteri speciali.

+++

+++ Se inizialmente si imposta il rilevamento manuale o automatico, è possibile passare successivamente all&#39;altra modalità di rilevamento? Quali sono le implicazioni?

Sì, è possibile cambiare le modalità di tracciamento, ma è necessario rimuovere la vecchia logica di tracciamento prima di effettuare il passaggio. Ciò può comportare tempi di inattività del tracciamento nel giorno in cui viene effettuato il passaggio (specialmente se si passa da manuale a automatico). Pertanto, si consiglia di non cambiare se non in caso di assoluta necessità.

* Passaggio da manuale ad automatico: rimuovi le aggiunte manuali ai modelli di tracciamento, quindi cambia l’opzione nell’interfaccia utente di Advertising Analytics da manuale ad automatico e salva l’impostazione. Potrebbero essere necessarie diverse ore affinché il sistema possa compilare i codici di tracciamento automatico.

* Passaggio da automatico a manuale: aggiorna il passaggio da manuale a automatico nell’interfaccia utente di configurazione di Advertising Analytics, quindi distribuisci i codici di tracciamento manuali il più rapidamente possibile. Durante la distribuzione dei codici di tracciamento manuali, rimuovili se nei modelli di tracciamento dei motori di ricerca trovi i codici di tracciamento automatici.

+++
