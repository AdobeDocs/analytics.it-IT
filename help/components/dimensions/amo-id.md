---
title: ID AMO
description: L’ID Adobe Media Optimizer, utilizzato nelle integrazioni Adobe Advertising.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 2%

---

# ID AMO

**[!UICONTROL AMO ID]** è una raccolta di identificatori concatenati utilizzati nelle integrazioni Adobe Advertising. I valori memorizzati in questa dimensione vengono automaticamente organizzati in dimensioni di classificazione separate e più leggibili dall’uomo da utilizzare nei rapporti di Analytics. La dimensione viene creata automaticamente quando si abilita l&#39;integrazione di [Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview).

## Popolare questa dimensione con i dati

Questa dimensione raccoglie i valori in diversi modi:

* Per il traffico di click-through, i dati vengono raccolti dal parametro della stringa di query `s_kwcid` nell&#39;[URL pagina](page-url.md), in genere nella pagina attraverso la quale il traffico guidato da annunci entra nel sito.
* Il traffico click-through può essere acquisito anche quando l’URL non contiene codici di tracciamento, ma Adobe Advertising JavaScript rileva un clic nei due minuti precedenti.
* Per il traffico view-through supportato, Adobe Advertising integra i valori sul backend utilizzando un ID supplementare (`SDID`).

## Elementi dimensionali

Gli elementi Dimension includono AMO ID, denominati anche valori `s_kwcid`. Il formato esatto dipende dal fatto che il traffico provenga da DSP o da Search, Social e Commerce. Gli AMO ID sono meno granulari degli EF ID e vengono utilizzati principalmente per le classificazioni e l’acquisizione di metriche Adobe Advertising in Analytics.

### DSP

```text
AC!{ad key}!{placement key}
```

* **`AC`**: indica il canale di visualizzazione.
* **`ad key`**: identificatore alfanumerico dell&#39;annuncio generato da Adobe Advertising.
* **`placement key`**: identificatore alfanumerico generato da Adobe Advertising per il posizionamento.

Esempio di valore:

```text
AC!iIMvXqlOa6Nia2lDvtgw!GrVv6o2oV2qQLjQiXLC7
```

### Annunci Search, Social e Commerce

Gli ID AMO di Search, Social e Commerce iniziano con `AL`, seguiti dall&#39;ID utente dell&#39;inserzionista, dall&#39;ID dell&#39;account di rete dell&#39;annuncio e quindi dagli identificatori specifici della rete. Gli ID degli account di rete degli annunci condivisi includono:

* **`3`**: Google Ads
* **`10`**: Microsoft Advertising
* **`45`**: Meta
* **`86`**: Yahoo! Rete di visualizzazione
* **`87`**: Naver
* **`88`**: Baidu
* **`90`**: Yandex
* **`94`**: Yahoo! Japan Ads
* **`105`**: Yahoo nativo (obsoleto)
* **`106`**: Pinterest (obsoleto)

#### Google Ads

Google Ads utilizza due formati correlati. Gli account più recenti possono includere l’ID della campagna e l’ID del gruppo di annunci, che supportano la generazione di rapporti a livello di campagna e di gruppo di annunci per le campagne Performance Max e Bozze/Esperimenti.

```text
AL!{user}!3!{creative}!{matchtype}!{placement}!{network}!{product partition}!{keyword}[!{campaign id}!{ad group id}]
```

* **`creative`**: ID creativo di Google Ads.
* **`matchtype`**: tipo di corrispondenza parola chiave (`e` per exact, `p` per phrase, `b` per broad).
* **`placement`**: dominio in cui è stato fatto clic sull&#39;annuncio.
* **`network`**: rete su cui si è verificato il clic (`g` per la ricerca Google, `s` per un partner di ricerca, `d` per la visualizzazione).
* **`product partition`**: ID gruppo di prodotti per annunci di prodotti.
* **`keyword`**: attivazione della parola chiave nei siti di ricerca o della parola chiave corrispondente nei siti di contenuto.
* **`campaign id`**: ID campagna Google Ads, se presente.
* **`ad group id`**: ID gruppo di annunci Google Ads, se presente.

Per gli annunci per ricerca dinamica, il campo della parola chiave viene compilato con il targeting automatico.

Esempio:

```text
AL!1234!3!569345525675!e!!g!!adobe express!15557590691!136734402131
```

#### Microsoft Advertising

```text
AL!{user}!10!{ad id}!!!!{keyword/order item id}!!{campaign id}!{ad group id}
```

* **`ad id`**: ID creativo di Microsoft Advertising.
* **`keyword/order item id`**: ID parola chiave di Microsoft Advertising.
* **`campaign id`**: ID campagna Microsoft Advertising.
* **`ad group id`**: ID gruppo di annunci di Microsoft Advertising.

I formati Microsoft legacy possono ancora esistere per alcuni account non migrati.

Esempio:

```text
AL!1234!10!79577297926903!!!!79577437127536!!291647087!1273234845019564
```

#### Baidu

```text
AL!{user}!88!{creative}!{placement}!{keyword id}
```

* **`creative`**: ID creativo Baidu.
* **`placement`**: sito Web su cui è stato fatto clic sull&#39;annuncio.
* **`keyword id`**: ID parola chiave Baidu.

#### Yahoo! Japan Ads

```text
AL!{user}!94!{creative}!{matchtype}!{network}!{keyword}
```

* **`creative`**: Yahoo! ID creativo di Japan Ads.
* **`matchtype`**: tipo di corrispondenza parola chiave (`be` esatta, `bp` frase, `bb` ampia).
* **`network`**: rete in cui si è verificato il clic (`n` nativo, `s` ricerca).
* **`keyword`**: attivazione parola chiave.

#### Yandex

```text
AL!{user}!90!{ad id}!{source type}!!!{phrase id}
```

* **`ad id`**: ID creativo Yandex.
* **`source type`**: tipo di sito in cui è stato visualizzato l&#39;annuncio (`b` ricerca, `c` contesto/contenuto, categoria `ct`).
* **`phrase id`**: ID parola chiave Yandex.

## Classificazioni

Quando si abilita l&#39;integrazione di [Analytics per Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview), vengono create automaticamente le seguenti classificazioni. I valori di classificazione vengono gestiti automaticamente dall’integrazione.

| Classificazione | Descrizione | DSP | Cerca,<br>Social, &amp;<br>Commerce |
| --- | --- | :---: | :---: |
| **[!UICONTROL Account]** | Il nome dell’account. | &check; | &check; |
| **[!UICONTROL Ad Display URL]** | L’URL visualizzato nell’annuncio. | | &check; |
| **[!UICONTROL Ad Description]** | La descrizione dell’annuncio (DSP) o il corpo dell’annuncio (Search, Social e Commerce). | &check; | &check; |
| **[!UICONTROL Ad Destination URL]** | L’URL di destinazione dell’annuncio. | | &check; |
| **[!UICONTROL Ad Group]** | Il nome del gruppo di annunci. | | &check; |
| **[!UICONTROL Ad Platform]** | Il nome del DSP pubblicitario o del motore di ricerca. | &check; | &check; |
| **[!UICONTROL Ad Title]** | Il tipo di annuncio (DSP) o il titolo dell’annuncio (Search, Social e Commerce). | &check; | &check; |
| **[!UICONTROL Ad Type]** | Il tipo di annuncio, ad esempio `text`, `video`, `display` o `native`. | &check; | &check; |
| **[!UICONTROL AdCloud Attribute 1]** -<br>**[!UICONTROL AdCloud Attribute 5]** | Le classificazioni dei segnaposto sono riservate per gli attributi personalizzati futuri. Non attualmente in uso. | | |
| **[!UICONTROL Campaign]** | Il nome della campagna. | &check; | &check; |
| **[!UICONTROL Creative Experience Name]** | Nome dell’esperienza creativa associata all’interazione dell’annuncio, che rappresenta un gruppo di varianti creative utilizzate nei test o nella personalizzazione. | &check; | |
| **[!UICONTROL Creative Branch Name]** | Nome del ramo all’interno di un’esperienza creativa che rappresenta una variante o un percorso specifico nell’esperimento creativo. | &check; | |
| **[!UICONTROL Creative Branch ID]** | Identificatore univoco assegnato a un ramo creativo in un’esperienza creativa. | &check; | |
| **[!UICONTROL Creative Name]** | Nome della risorsa pubblicitaria specifica fornita all’utente. | &check; | |
| **[!UICONTROL Creative Variant Name]** | Nome della variante specifica di un contenuto creativo utilizzato all’interno di un’esperienza o di un ramo creativo. | &check; | |
| **[!UICONTROL Keyword]** | La parola chiave. | | &check; |
| **[!UICONTROL Keyword Match Type]** | Parola chiave e tipo di corrispondenza. | | &check; |
| **[!UICONTROL Landing Type]** | Se la voce della pagina di destinazione era un view-through o un click-through. | &check; | &check; |
| **[!UICONTROL Match Type]** | Tipo di corrispondenza della ricerca. | | &check; |
| **[!UICONTROL Network]** | RTB (DSP) o il nome della rete di annunci (Search, Social e Commerce). | &check; | &check; |
| **[!UICONTROL Optimization]** | Il nome del pacchetto (DSP) o del portfolio (Search, Social e Commerce). | &check; | &check; |
| **[!UICONTROL Placement]** | Il nome del posizionamento. | &check; | |
| **[!UICONTROL Product Target]** | Il target di prodotto per un annuncio di elenco prodotti. | | &check; |
