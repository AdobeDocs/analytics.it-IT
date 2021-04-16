---
description: 'Una volta attivata, l’integrazione DFA dei Data Connectors fornisce le metriche seguenti per i rapporti di Adobe Analytics '
keywords: DFA
title: Funzionalità di integrazione
feature: Data Connectors
uuid: 4ad8e6e8-3449-498a-8596-37c0ac1657cd
exl-id: a0eb2196-5f6a-4dbb-98b0-c96c30601bc5
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 1%

---

# Funzionalità di integrazione{#integration-features}

Una volta attivata, l’integrazione DFA dei Data Connectors fornisce le metriche seguenti per i rapporti di Adobe Analytics:

* View-through
* Clic DFA
* Impression
* (facoltativo) Dati dei costi DFA
* (facoltativo) Errori di query DFA, timeout

>[!NOTE]
>
>Questa integrazione non fornisce supporto per i tracciatori di clic (in precedenza comandi di clic). I tracciatori di clic vengono utilizzati per registrare il numero di clic su collegamenti di testo, collegamenti in messaggi di posta elettronica o su altri elementi codificati in un sito Web.

L’integrazione DFA dei Data Connectors costruisce automaticamente i codici di tracciamento DFA dai dati restituiti da DFA. Questi codici di tracciamento sono costruiti per identificare in modo univoco un annuncio insieme ai relativi Collocamenti e Creativi. Di seguito viene descritta la struttura del codice di tracciamento, a seconda della versione dell’integrazione. La versione 1.5 si presenta così:

![](assets/DFA_id_struct1_5.png)

La versione 2.0 si presenta così:

![](assets/DFA_id_struct2.png)

Questi ID fungono da chiave condivisa tra Genesis e DFA per associare le classificazioni e le metriche corrette.

| ID sito | Il sito di terze parti in cui è stato ospitato l’annuncio. La classificazione Nome sito fornisce un nome descrittivo di questo ID sito. |
|---|---|
| ID annuncio | Un ID per il messaggio commerciale consegnato a un utente. La classificazione Nome annuncio contiene il nome dell’annuncio come definito dall’organizzazione nel sistema DFA. Ad esempio: `Hybrid Coup Textlink - Build`. |
| ID posizionamento | Una rappresentazione nell&#39;account DFA di un sito Web, di una parte di un sito Web o di un gruppo di siti Web in cui è stato acquistato spazio pubblicitario. |
| ID creativo | Immagine, file SWF di Flash o altra risorsa che deve essere mostrata al visitatore. La classificazione Nome creativo contiene il nome fornito al creativo nell’interfaccia DFA. |

Le altre due classificazioni, Strumento di consegna (DoubleClick for Advertiser) e Canale (Banner Ad) hanno gli stessi valori per qualsiasi campagna DFA e aiutano a distinguere i dati importati DFA.

## Deduplicazione SearchCenter {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

L’integrazione DFA è ora nota per Adobe SearchCenter. Attivando la deduplicazione SearchCenter tramite la procedura guidata Data Connectors, i visitatori basati sulla ricerca non estrarranno i dati dal server di Mobile DFA e *`s.campaign`* non verranno compilati da DFA, consentendo quindi a SearchCenter di compilarli. Inoltre, DFA e SearchCenter ora popolano i valori di deduplicazione nelle variabili per ogni prodotto.

L’elenco seguente illustra la logica abilitata quando la deduplicazione di SearchCenter è abilitata:

Se **[!UICONTROL DFA]** > **[!UICONTROL SearchCenter deduplication]** è selezionato nella procedura guidata:

* Nel caso di un click-through DFA, l’integrazione popolerà la stringa &quot;Click-through DFA&quot; nell’eVar SCM configurato.
* Nel caso di un view-through DFA, l’integrazione popolerà la stringa &quot;DFA Viewthrough&quot; nell’eVar SCM.

Se **[!UICONTROL SearchCenter]** > **[!UICONTROL DFA deduplication]** è selezionato nella procedura guidata:

* Nel caso di un view-through DFA, l’integrazione popolerà la stringa &quot;DFA Viewthrough&quot; nell’eVar SCM.

>[!NOTE]
>
>Se SearchCenter > Deduplicazione DFA è abilitato e il parametro della stringa di query SearchCenter è impostato, la visita non verrà considerata per l’elaborazione DFA. Ciò significa che il parametro della stringa di query SearchCenter deve essere diverso dal parametro click-through DFA e che nessun annuncio Display deve impostare il parametro della stringa di query SearchCenter.
