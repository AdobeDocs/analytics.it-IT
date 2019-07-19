---
description: I rapporti sulle origini traffico ti offrono informazioni approfondite sul modo in cui i visitatori interagiscono con il tuo sito web.
seo-description: I rapporti sulle origini traffico ti offrono informazioni approfondite sul modo in cui i visitatori interagiscono con il tuo sito web.
seo-title: Rapporti fonti traffico
solution: Analytics
title: Rapporti fonti traffico
topic: Analisi ad hoc
uuid: 246 afbdc -9 f 7 b -4956-a 44 a-b 7 aad 948 f 392
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rapporti fonti traffico

I rapporti sulle origini traffico ti offrono informazioni approfondite sul modo in cui i visitatori interagiscono con il tuo sito web.

## Rapporti fonti traffico {#concept_0F1772141E1345C5BCF63BE7C544C0CB}

I rapporti sulle origini traffico ti offrono informazioni approfondite sul modo in cui i visitatori interagiscono con il tuo sito web.

I rapporti sulle origini traffico consentono di:

* Analizzare aspetti critici del comportamento dei visitatori.
* Monitorare e comprendere i pattern di traffico.
* Determinare il contenuto del sito più diffuso.
* Segmentare i visitatori in base a criteri misurabili.

**Persistenza comune**

In [!UICONTROL Traffic Sources], all report values persist and receive credit until they are overwritten or until the visit ends, whichever comes first. In precedenza venivano mantenute solo le parole chiave e i domini di riferimento. Ad esempio, se un visitatore esegue una ricerca Google per "DVD" che li porta al sito per un acquisto di $ 100, il rapporto assegna un credito di $ 100 alla parola chiave "DVD" e al motore di ricerca Google. This functionality is unalterable, regardless of [!DNL Admin Console] settings.

## Search Keywords {#concept_071FDCBD0A3B4242BA00744786D1C59C}

Visualizza una suddivisione delle parole chiave per le ricerche All, Paid e Natural.

<!-- 

c_reports_search_keyword.xml

 -->

** [!UICONTROL Search Keywords - All] **: Displays a breakdown of each search keyword that has been used to find your site. Per ordinare questo elenco in base alle visualizzazioni di pagina o alle parole chiave di ricerca, fai clic sul titolo della colonna sopra l'elenco. Fate clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il sito.

** [!UICONTROL Search Keywords - Paid] **: Displays a breakdown of each paid search keyword that is used to find your site. Per ordinare questo elenco in base alle visualizzazioni di pagina o alle parole chiave di ricerca, fai clic sul titolo della colonna sopra l'elenco. Fate clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il sito.

** [!UICONTROL Search Keywords - Natural] **: Displays a breakdown of each natural search keyword that is used to find your site. Per ordinare questo elenco in base alle visualizzazioni di pagina o alle parole chiave di ricerca, fai clic sul titolo della colonna sopra l'elenco. Fate clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il sito.

## Search Engines {#concept_351CDE4F5FC44371B6B657064E125134}

Visualizza i motori di ricerca utilizzati dai visitatori per le ricerche All, Paid e Natural.

<!-- 

c_reports_search_engines.xml

 -->

** [!UICONTROL Search Engines - All] **: Displays which search engines that people are using to find your web page. Il grafico mostra la suddivisione percentuale dei motori di ricerca utilizzati per trovare il sito.

** [!UICONTROL Search Engines - Paid] **: Displays which paid-keyword search engines that people are using to find your web page. Il grafico mostra la suddivisione percentuale dei motori di ricerca utilizzati per trovare il sito.

** [!UICONTROL Search Engines - Natural] **: Displays which natural-keyword search engines people are using to find your web page. Il grafico mostra la suddivisione percentuale dei motori di ricerca utilizzati per trovare il sito.

## Domini di riferimento {#concept_804614DF21C14C9FB542451B30F92788}

<!-- 

c_reports_ref_domains.xml

 -->

Mostra i domini che hanno indirizzato i clienti che hanno maggiormente influenzato le metriche di successo del sito. I referenti rientrano in due categorie principali: Domini e URL. I domini fanno riferimento al nome di dominio e appaiono come dominio di base senza le stringhe o le sottodirectory di query allegate. Gli URL includono il nome del dominio di base, nonché qualsiasi stringa o sottodirectory di query.

## Original Referring Domains {#concept_EB18251DF70343169B46BB59543A579A}

<!-- 

c_reports_original_ref_domains.xml

 -->

Visualizza i referenti originali che hanno prodotto i clienti sul sito. I clienti possono visitare il sito più volte e avere un referente diverso per ogni visita. Questo rapporto mostra come sono stati citati al suo primo sito Web. In questo modo potete vedere se hanno continuato a utilizzare lo stesso referente e visualizzare pattern in cui i clienti vengono indirizzati al sito. Potete visualizzare il numero di visitatori generati da un referente originale o verificare il numero di entrate che ogni referente originale è responsabile per la produzione. I rapporti di referrer possono essere popolati ogni volta che un visitatore accede al sito, anche se il visitatore accede più volte al sito durante una sessione (prima della scadenza della visita).

## Referrers {#concept_40CF9C2D10B94E82819BC65A232F05C3}

Visualizza il dominio o l'URL in cui i visitatori provengono prima che arrivino sul sito, i metodi utilizzati dai visitatori per trovare il tuo sito Web e il numero di visite al tuo sito derivanti da queste posizioni di provenienza.

<!-- 

c_reports_referrers.xml

 -->

Ad esempio, se un visitatore fa clic su un collegamento dal Sito A e accede al sito, il Sito A è il referente se non viene definito come parte del dominio. Durante l'implementazione di rapporti di marketing e analisi, il consulente di implementazione può aiutarti a definire i domini e gli URL che fanno parte del tuo sito Web. (Questa modifica può essere effettuata dopo l'implementazione.)

I domini o gli URL che non fanno parte di tali domini e URL definiti sono considerati referenti. Ad esempio, la pagina Web A e la pagina Web B vengono aggiunte al filtro URL interno, mentre la pagina Web C non lo è. In questo caso, la pagina Web C è considerata un referente.

See [Internal URL Filters](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=internal_URL_filter_admin) in the [!DNL Admin Console] help for more information.

>[!NOTE]
>
>Marketing reports and analytics records a referring domain as an email when visitors click an emailed message link containing the protocol [!DNL imap://] or [!DNL mail://] and arrive at your site. For example, anything coming from [!DNL https://mail.yahoo.com] is not counted as an email referrer because the protocol is [!DNL https://]. Le e-mail di Outlook sono riportate nella riga Typed/Bookmarked, mentre qualsiasi referente con un protocollo HTTP in cui il dominio è un motore di ricerca noto è riportato nella riga Motore di ricerca.

## Referrer Type {#concept_689E42D8F96C450DA41C7167C7388198}

Tracciando e registrando i siti di provenienza dei visitatori per ogni visita, potete determinare in che modo i visitatori hanno scoperto il sito per ogni visita.

<!-- 

c_reports_ref_types.xml

 -->

L'elenco seguente definisce i vari tipi di referenti:

* *Altri riferimenti* al sito Web vengono registrati quando i visitatori fanno clic su un collegamento situato in una pagina su un altro sito Web (non definito come parte del sito) e arrivano sul sito Web.
* *I referenti del motore* di ricerca vengono registrati quando i visitatori utilizzano un motore di ricerca per accedere al sito.
* *I referenti Typed/Segnalibri* vengono registrati

   * Se un visitatore accede al sito tramite un collegamento non browser (ad esempio, in un messaggio e-mail).
   * Se un visitatore digita l'URL del sito direttamente nel browser.
   * Se un visitatore fa clic su un collegamento HTML sul suo disco rigido personale.
   * Se un visitatore accede al sito selezionando segnalibri del browser.

**Definizioni**

Durante l'esecuzione di questo rapporto potrebbero essere visualizzati i seguenti elementi della riga:

**All'interno del sito**: Questi elementi sono URL con tag dai filtri URL interni. Questi elementi non vengono considerati istanze di riferimento, ma possono essere visti durante il reporting su altre metriche.

** Nessuno script Java**: Javascript non era in modo che il tipo non fosse identificabile (sconosciuto). Ciò significa che non sono presenti informazioni di riferimento fornite da un client in un browser, che non sono in grado di supportare Javascript. Queste non vengono considerate come «istanze di referente», ma possono essere visualizzate durante la segnalazione di altre metriche.

**USENET (newsgroup)**: Ciò significa [!DNL news://]che l'URL di un referente è iniziato. Di conseguenza, il collegamento referrer veniva pubblicato su un newsgroup Usenet piuttosto che su una pagina Web.

>[!NOTE]
>
>Referrer Type logic matches other traffic sources reports (such as [!UICONTROL Referrers] and [!UICONTROL Referring Domains]). This should reduce or eliminate the occurrences of the Inside Your Site and No JavaScript line items in the [!UICONTROL Referrer Type] report.

