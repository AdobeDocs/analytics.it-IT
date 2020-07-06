---
description: 'Una volta attivata, l''integrazione DFA dei Connettori dati fornisce le metriche seguenti per i report Adobe  Analytics '
keywords: DFA
title: Funzionalità di integrazione
topic: Data connectors
uuid: 4ad8e6e8-3449-498a-8596-37c0ac1657cd
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---


# Funzionalità di integrazione{#integration-features}

Una volta attivata, l&#39;integrazione DFA dei Connettori dati fornisce le metriche seguenti per i report Adobe  Analytics:

* Visualizzazione
* Clic DFA
* Impressioni
* (facoltativo) Dati sui costi DFA
* (facoltativo) Errori query DFA, timeout

>[!NOTE]
>
>Questa integrazione non supporta i tracciatori di clic (precedentemente clic sui comandi). I tracciatori di clic vengono utilizzati per registrare il numero di clic su collegamenti di testo, collegamenti in messaggi e-mail o su altri elementi che sono codificati in un sito Web.

L’integrazione DFA dei Connettori dati crea automaticamente i codici di monitoraggio DFA a partire dai dati restituiti dal DFA. Questi codici di tracciamento sono creati per identificare in modo univoco un annuncio insieme ai relativi Collocamenti e Creative. Di seguito viene illustrata la struttura del codice di tracciamento, a seconda della versione dell&#39;integrazione. La versione 1.5 è simile alla seguente:

![](assets/DFA_id_struct1_5.png)

La versione 2.0 è simile alla seguente:

![](assets/DFA_id_struct2.png)

Questi ID fungono da chiave condivisa tra Genesis e DFA per associare le classificazioni e le metriche corrette.

| ID sito | Il sito di terze parti in cui è stato ospitato l&#39;annuncio. La classificazione Nome sito fornisce un nome descrittivo di questo ID sito. |
|---|---|
| ID annuncio | Un ID per il messaggio commerciale inviato a un utente. La classificazione Ad Name (Nome annuncio) contiene il nome dell&#39;annuncio, come definito dall&#39;organizzazione nel sistema DFA. Ad esempio: `Hybrid Coup Textlink - Build`. |
| ID posizionamento | Una rappresentazione nel proprio account DFA di un sito Web, di una parte di un sito Web o di un gruppo di siti Web in cui è stato acquistato spazio per gli annunci. |
| Creative ID | Immagine, SWF Flash o altra risorsa che verrà mostrata al visitatore. La classificazione Nome creativo contiene il nome fornito a questo creativo nell’interfaccia DFAE. |

Le altre due classificazioni, Strumento di consegna (DoubleClick for Advertiser) e Canale (Banner Ad) hanno gli stessi valori per qualsiasi campagna DFA e aiutano a distinguere i dati DFA importati.

## De-Duplicazione SearchCenter {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

L’integrazione DFA ora è in grado di riconoscere Adobe SearchCenter. Attivando la deduplicazione SearchCenter tramite la procedura guidata Connettori dati, i visitatori guidati dalla ricerca non causeranno il pulling dei dati dal server di Floodlight del DFA e non *`s.campaign`* verranno compilati dal DFA, consentendo quindi a SearchCenter di compilarli. Inoltre, DFA e SearchCenter ora popolano i valori di deduplicazione nelle variabili per ogni prodotto.

Nell&#39;elenco seguente è illustrata la logica abilitata quando la deduplicazione SearchCenter è abilitata:

Se **[!UICONTROL DFA]** > **[!UICONTROL SearchCenter deduplication]** è selezionato nella procedura guidata:

* Nel caso di un click-through DFA, l&#39;integrazione popolerà la stringa &quot;Clickthrough DFA&quot; nella eVar SCM configurata.
* Nel caso di una visualizzazione &quot;through&quot; DFAE, l’integrazione inserisce nella eVar SCM la stringa &quot;DFA Viewthrough&quot;.

Se **[!UICONTROL SearchCenter]** > **[!UICONTROL DFA deduplication]** è selezionato nella procedura guidata:

* Nel caso di una visualizzazione &quot;through&quot; DFAE, l’integrazione inserisce nella eVar SCM la stringa &quot;DFA Viewthrough&quot;.

>[!NOTE]
>
>Se è abilitata la deduplicazione SearchCenter > DFA e viene impostato il parametro della stringa di query SearchCenter, la visita non verrà considerata per l&#39;elaborazione DFA. Ciò significa che il parametro della stringa di query SearchCenter deve essere diverso dal parametro click-through del DFA e che nessun annuncio display deve impostare il parametro della stringa di query SearchCenter.

