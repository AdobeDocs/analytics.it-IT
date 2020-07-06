---
description: I rapporti sulle origini del traffico forniscono informazioni approfondite sul modo in cui i visitatori interagiscono con il sito Web.
title: Rapporti fonti traffico
topic: Ad hoc analysis
uuid: 246afbdc-9f7b-4956-a44a-b7aad948f392
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 1%

---


# Rapporti fonti traffico

I rapporti sulle origini del traffico forniscono informazioni approfondite sul modo in cui i visitatori interagiscono con il sito Web.

## Rapporti fonti traffico {#concept_0F1772141E1345C5BCF63BE7C544C0CB}

I rapporti sulle origini del traffico forniscono informazioni approfondite sul modo in cui i visitatori interagiscono con il sito Web.

I rapporti sulle origini di traffico consentono di:

* Analizzare gli aspetti critici del comportamento dei visitatori.
* Monitorare e comprendere i pattern di traffico.
* Consente di determinare il contenuto del sito più popolare.
* Segmenta i visitatori in base a qualsiasi criterio misurabile.

**Persistenza comune**

In [!UICONTROL Traffic Sources]questo caso, tutti i valori del rapporto persistono e ricevono credito fino a quando non vengono sovrascritti o fino alla fine della visita, a seconda di quale sia il primo. Precedentemente, erano persistenti solo le parole chiave e i domini di riferimento. Ad esempio, se un visitatore esegue una ricerca Google per &quot;DVD&quot;, che li porta sul sito per un acquisto da $ 100, il rapporto assegna un credito da $ 100 alla parola chiave &quot;DVD&quot; e anche al motore di ricerca Google. Questa funzionalità è inalterabile, indipendentemente dalle [!DNL Admin Console] impostazioni.

## Parole chiave di ricerca {#concept_071FDCBD0A3B4242BA00744786D1C59C}

Visualizza un’analisi approfondita delle parole chiave per le ricerche Tutte, Pagate e Naturali.

<!-- 

c_reports_search_keyword.xml

 -->

**[!UICONTROL Search Keywords - All]**: Visualizza una suddivisione di ogni parola chiave di ricerca utilizzata per trovare il sito. Potete ordinare l’elenco per visualizzazioni di pagina o per parole chiave di ricerca facendo clic sul titolo della colonna sopra l’elenco. Fai clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il tuo sito.

**[!UICONTROL Search Keywords - Paid]**: Visualizza una suddivisione di ogni parola chiave di ricerca a pagamento utilizzata per trovare il sito. Potete ordinare l’elenco per visualizzazioni di pagina o per parole chiave di ricerca facendo clic sul titolo della colonna sopra l’elenco. Fai clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il tuo sito.

**[!UICONTROL Search Keywords - Natural]**: Visualizza una suddivisione di ogni parola chiave di ricerca naturale utilizzata per trovare il sito. Potete ordinare l’elenco per visualizzazioni di pagina o per parole chiave di ricerca facendo clic sul titolo della colonna sopra l’elenco. Fai clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il tuo sito.

## Motori di ricerca {#concept_351CDE4F5FC44371B6B657064E125134}

Visualizza i motori di ricerca utilizzati dai visitatori per le ricerche All (Tutto), Paid (Pagato) e Natural (Naturale).

<!-- 

c_reports_search_engines.xml

 -->

**[!UICONTROL Search Engines - All]**: Visualizza i motori di ricerca utilizzati dagli utenti per trovare la pagina Web. Il grafico mostra la suddivisione percentuale dei motori di ricerca utilizzati per trovare il sito.

**[!UICONTROL Search Engines - Paid]**: Visualizza i motori di ricerca con parole chiave a pagamento utilizzati dagli utenti per trovare la pagina Web. Il grafico mostra la suddivisione percentuale dei motori di ricerca utilizzati per trovare il sito.

**[!UICONTROL Search Engines - Natural]**: Consente di visualizzare i motori di ricerca con parole chiave naturali che gli utenti usano per trovare la pagina Web. Il grafico mostra la suddivisione percentuale dei motori di ricerca utilizzati per trovare il sito.

## Domini di riferimento {#concept_804614DF21C14C9FB542451B30F92788}

<!-- 

c_reports_ref_domains.xml

 -->

Mostra i domini che fanno riferimento ai clienti che hanno più inciso sulle metriche di successo del sito. I riferimenti sono suddivisi in due categorie principali: Domini e URL. I domini fanno riferimento al nome del dominio e vengono visualizzati come dominio di base senza la stringa di query o le sottodirectory associate. Gli URL includono il nome del dominio di base, nonché eventuali stringhe di query o sottodirectory.

## Domini di riferimento originali {#concept_EB18251DF70343169B46BB59543A579A}

<!-- 

c_reports_original_ref_domains.xml

 -->

Visualizza i referenti originali che hanno prodotto i clienti sul sito. I clienti possono visitare il sito più volte e disporre di un referente diverso per ogni visita. Questo rapporto mostra come sono stati rimandati la prima volta che sono arrivati sul sito. Questo può essere utile per verificare se hanno continuato a utilizzare lo stesso referente e per visualizzare i pattern in base al modo in cui i clienti vengono indirizzati al sito. Puoi visualizzare il numero di visitatori generati da un referente originale o scoprire il fatturato generato da ciascun referente originale. I rapporti del referente possono essere compilati ogni volta che un visitatore accede al sito, anche se il visitatore accede più volte al sito durante una sessione (prima della scadenza della visita).

## Riferimenti {#concept_40CF9C2D10B94E82819BC65A232F05C3}

Visualizza il dominio o l’URL da cui i visitatori sono arrivati prima del loro arrivo sul sito, i metodi utilizzati dai visitatori per trovare il sito Web e il numero di visite al sito provenienti da queste posizioni di riferimento.

<!-- 

c_reports_referrers.xml

 -->

Ad esempio, se un visitatore fa clic su un collegamento dal sito A e arriva sul sito, il sito A è il referente se non è definito come parte del dominio. Durante l’implementazione dei marketing reports and analytics, il consulente di implementazione può aiutarti a definire i domini e gli URL che fanno parte del tuo sito Web. (Questa modifica può essere eseguita dopo l’implementazione).

I domini o gli URL che non fanno parte di tali domini definiti e gli URL sono considerati referenti. Ad esempio, la pagina Web A e la pagina Web B vengono aggiunte al filtro URL interno, ma non la pagina Web C. In questo caso, la pagina Web C è considerata un referente.

Per ulteriori informazioni, consulta Filtri [URL](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/internal-url-filter-admin.html) interni nella [!DNL Admin Console] guida.

>[!NOTE]
>
>Marketing reports and analytics registra un dominio di riferimento come e-mail quando i visitatori fanno clic su un collegamento a un messaggio e-mail contenente il protocollo [!DNL imap://] o [!DNL mail://] e arrivano sul sito. Ad esempio, qualsiasi cosa proveniente da [!DNL https://mail.yahoo.com] viene conteggiata come referente e-mail perché il protocollo è [!DNL https://]. Le e-mail di Outlook vengono riportate nella riga Typed/Bookmarked, mentre qualsiasi referente con un protocollo HTTP in cui il dominio è un motore di ricerca noto viene riportato nella riga Motore di ricerca.

## Tipo di riferimento {#concept_689E42D8F96C450DA41C7167C7388198}

Tracciando e registrando i siti di riferimento dei visitatori per ogni visita, puoi determinare in che modo i visitatori hanno scoperto il sito per ogni visita.

<!-- 

c_reports_ref_types.xml

 -->

L&#39;elenco seguente definisce i vari tipi di referenti:

* *Quando i visitatori fanno clic su un collegamento situato in una pagina di un altro sito Web (non definito come parte del sito) e arrivano al sito Web, vengono registrati altri riferimenti* al sito Web.
* *I referenti del motore* di ricerca vengono registrati quando i visitatori accedono al sito tramite un motore di ricerca.
* *Vengono registrati i riferimenti digitati/con segnalibro*

   * Se un visitatore accede al sito tramite un collegamento non del browser (ad esempio, in un messaggio e-mail).
   * Se un visitatore digita l&#39;URL del sito direttamente nel browser.
   * Se un visitatore fa clic su un collegamento HTML sul suo disco rigido personale.
   * Se un visitatore accede al sito selezionando i segnalibri del browser.

**Definizioni**

Durante l&#39;esecuzione di questo rapporto potrebbero essere visualizzati i seguenti elementi di riga:

**All&#39;interno del sito**: Si tratta di URL dotati di tag per i filtri URL interni. Questi elementi non vengono conteggiati come istanze di riferimento, ma possono essere visualizzati durante la generazione di rapporti su altre metriche.

**Nessun Java Script**: Non era presente un codice JavaScript, pertanto il tipo non era identificabile (sconosciuto). Ciò significa che non sono state fornite informazioni sul referente da un client in un browser, che non segnala il supporto di Javascript. Questi non vengono contati come &quot;istanze di referente&quot;, ma possono essere visualizzati quando si riferiscono ad altre metriche.

**USENET (newsgroup)**: Ciò significa che l&#39;URL di un referente è iniziato con `news://`. Come tale, il collegamento del referente è stato pubblicato su un newsgroup Usenet anziché su una pagina Web.

>[!NOTE]
>
>La logica Tipo referente corrisponde ad altri rapporti origini traffico (ad esempio [!UICONTROL Referrers] e [!UICONTROL Referring Domains]). In questo modo si riducono o si eliminano le occorrenze degli elementi di riga all&#39;interno del sito e non è presente alcun elemento JavaScript nel [!UICONTROL Referrer Type] rapporto.

