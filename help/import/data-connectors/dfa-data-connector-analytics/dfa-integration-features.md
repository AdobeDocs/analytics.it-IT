---
description: 'Una volta attivata, l''integrazione DFA dei connettori dati fornisce le metriche seguenti per i rapporti di Adobe Analytics '
keywords: DFA
seo-description: 'Una volta attivata, l''integrazione DFA dei connettori dati fornisce le metriche seguenti per i rapporti di Adobe Analytics '
seo-title: Funzioni per l'integrazione
solution: Analytics
title: Funzioni per l'integrazione
topic: Connettori dati
uuid: 4 ad 8 e 6 e 8-3449-498 a -8596-37 c 0 ac 1657 cd
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Funzioni per l'integrazione{#integration-features}

Una volta attivata, l'integrazione DFA dei connettori dati fornisce le metriche seguenti per i rapporti di Adobe Analytics:

* View-through
* Clic su DFA
* Impressioni
* (Facoltativo) Dati costi DFA
* (facoltativo) Errori query DFA, Timeout

>[!NOTE]
>
>Questa integrazione non fornisce supporto per i tracker (precedentemente fate clic sui comandi). I tracker vengono utilizzati per registrare il numero di clic sui collegamenti di testo, i collegamenti nei messaggi e-mail o altri elementi codificati in un sito Web.

L'integrazione DFA dei connettori dati crea automaticamente i codici di monitoraggio DFA dai dati restituiti da DFA. Questi codici di tracciamento sono costruiti per identificare in modo univoco un annuncio e il relativo Posizionamento e Creative. Di seguito viene delineata la struttura del codice di tracciamento, a seconda della versione dell'integrazione. La versione 1.5 è simile alla seguente:

![](assets/DFA_id_struct1_5.png)

La versione 2.0 è simile alla seguente:

![](assets/DFA_id_struct2.png)

Questi ID fungono da chiave condivisa tra Genesis e DFA per associare le classificazioni e le metriche corrette.

| ID sito | Il sito 3 rd party in cui è ospitato l'annuncio. La classificazione Nome sito fornisce un nome descrittivo di questo ID sito. |
|---|---|
| ID annuncio | Un ID per il messaggio commerciale inviato a un utente. La classificazione Nome annuncio contiene il nome dell'annuncio definito dall'organizzazione nel sistema DFA. Ad esempio: `Hybrid Coup Textlink - Build`. |
| ID posizionamento | Una rappresentazione nell'account DFA di un sito Web, una parte di un sito Web o un gruppo di siti Web in cui è stato acquistato l'annuncio. |
| ID creativo | Immagine, SWF Flash o altra risorsa da mostrare al visitatore. La classificazione Creative Name contiene il nome fornito a tale creatività nell'interfaccia DFA. |

Le altre due classificazioni, Strumento di consegna (doubleclick per Advertiser) e Channel (Banner Ad) hanno gli stessi valori per qualsiasi campagna DFA e contribuiscono a distinguere i dati importati DFA.

## Searchcenter De-Duplication {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

L'integrazione DFA è ora basata su Adobe searchcenter. Abilitando la duplicazione di searchcenter tramite la procedura guidata Connettori dati, i visitatori basati su ricerca non provocano l'eliminazione dei dati da Floodlight Server di DFA e *`s.campaign`* non verranno completati da DFA, permettendo quindi al visitatore di compilarlo. Inoltre, DFA e searchcenter ora popolano i valori di deduplicazione nelle variabili per ogni prodotto.

L'elenco seguente evidenzia la logica abilitata quando è abilitata la funzione di riduplicazione searchcenter:

Se **[!UICONTROL DFA]** &gt; **[!UICONTROL SearchCenter deduplication]** è selezionato nella procedura guidata:

* Nel caso di un click-through DFA, l'integrazione popolerà la stringa «DFA Clickthrough» all'evar SCM configurato.
* Nel caso di una visualizzazione DFA, l'integrazione popolerà la stringa «DFA Viewthrough» all'evar SCM.

Se **[!UICONTROL SearchCenter]** &gt; **[!UICONTROL DFA deduplication]** è selezionato nella procedura guidata:

* Nel caso di una visualizzazione DFA, l'integrazione popolerà la stringa «DFA Viewthrough» all'evar SCM.

>[!NOTE]
>
>Se è abilitata la funzione searchcenter &gt; DFA de-duplicate e il parametro della stringa query searchcenter è impostato, la visita non sarà considerata per l'elaborazione DFA. Questo significa che il parametro della stringa query searchcenter deve essere diverso dal parametro click-through DFA, e nessun annuncio Visualizza deve impostare il parametro della stringa query searchcenter.

