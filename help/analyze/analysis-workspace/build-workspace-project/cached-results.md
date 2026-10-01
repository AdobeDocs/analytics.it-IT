---
title: Utilizzare i risultati nella cache per un caricamento più rapido in Analysis Workspace
description: Abilita un’impostazione di progetto in Analysis Workspace che memorizza nella cache i risultati per 12 ore in modo che i progetti vengano caricati all’istante. Aggiorna in qualsiasi momento per visualizzare i dati più recenti.
feature: Workspace Basics
hide: true
role: User
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: c457b289-f974-4a67-a5b6-dec3ffa77675
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3d882467f98ee1e9a4e7b023ab7593031f530513
workflow-type: tm+mt
source-wordcount: '1296'
ht-degree: 0%
---

# Utilizzare i risultati memorizzati nella cache nei progetti Workspace

>[!CONTEXTUALHELP]
>id="aa_project_cached_results"
>title="Utilizza i risultati memorizzati nella cache per un caricamento più rapido"
>abstract="Quando questa opzione è abilitata, i risultati vengono caricati istantaneamente per 12 ore dopo la prima apertura di un progetto da parte di un utente o dopo la consegna da parte di una pianificazione. Chiunque apra il progetto in quel periodo di tempo vede gli stessi risultati, anche se i dati continuano a scorrere in background. Per caricare i risultati più recenti, aggiorna i singoli pannelli o l’intero progetto."

{{release-limited-testing}}

Puoi configurare i progetti Analysis Workspace in modo da mostrare i risultati memorizzati nella cache per una finestra di 12 ore, che consente di caricare i risultati immediatamente per chiunque apra il progetto dopo averlo caricato inizialmente.

I progetti possono essere caricati inizialmente da un utente che apre il progetto o da una consegna pianificata del progetto.

## Comprendere i risultati memorizzati in cache in un progetto

### Quando i risultati vengono memorizzati in cache

La prima volta che il progetto viene caricato, i risultati vengono caricati a velocità normale e Analysis Workspace li memorizza nella cache per una finestra di 12 ore. Ciò si verifica quando:

* Qualcuno apre il progetto

* Il progetto viene eseguito per una consegna pianificata

Ad esempio, se la consegna di un progetto è pianificata per le 06:00, i risultati vengono memorizzati nella cache fino alle 18:00. Chiunque apra il progetto tra le 6:00 e le 18:00 vede i risultati caricarsi all’istante, inclusa la prima persona ad aprirlo.

Dopo 12 ore, i risultati memorizzati in cache scadono. Al successivo caricamento del progetto, che si tratti dell’apertura di un utente o dell’esecuzione di una consegna pianificata, i risultati vengono caricati alla velocità normale e inizia una nuova finestra di 12 ore.

### Quali risultati vengono memorizzati nella cache

#### Il progetto viene inizialmente memorizzato nella cache con la relativa configurazione originale

Analysis Workspace memorizza nella cache i risultati del progetto così come è stato configurato originariamente, con le suite di rapporti selezionate, i segmenti applicati, gli intervalli di date, le selezioni a discesa del pannello e così via. Tutti coloro che aprono il progetto visualizzano questi risultati memorizzati nella cache.

Se qualcuno modifica la configurazione del progetto durante la visualizzazione del progetto memorizzato in cache, i risultati vengono caricati normalmente (non immediatamente) e [viene memorizzata nella cache una nuova variante di progetto](#project-variations-are-cached-as-the-project-is-modified).

#### Le varianti di progetto vengono memorizzate nella cache quando il progetto viene modificato

Una nuova variante del progetto viene creata quando qualcuno ne modifica la configurazione originale, ad esempio selezionando una voce dal menu a discesa di un pannello, applicando un segmento, modificando un intervallo di date o la suite di rapporti selezionata.

La prima volta viene caricata una nuova variante alla velocità normale. Dopodiché, anche i suoi risultati vengono memorizzati in cache, così chiunque carichi la stessa variante vede i risultati immediatamente.

Considera i seguenti aspetti:

* Analysis Workspace memorizza nella cache ogni variante di un progetto che viene caricata da un utente. Non memorizza in cache tutte le possibili varianti di un progetto.

* La memorizzazione nella cache di una nuova variante non sovrascrive o invalida i risultati già memorizzati nella cache. Il progetto originale viene memorizzato nella cache insieme ad altre varianti caricate dagli utenti.

>[!BEGINSHADEBOX]

**Scenario di esempio**

Supponiamo che un progetto di prestazioni globali della campagna includa segmenti per diverse aree geografiche e sia pianificato per la consegna alle 06:00:

| Tempo | Azione | Velocità di carico |
| --- | --- | --- |
| 06:00 | Consegna pianificata del progetto | Normale (i risultati vengono memorizzati nella cache per utilizzi futuri) |
| 07:06 | L’utente A apre il progetto | Istantanea |
| 07:07 | L&#39;utente A applica il segmento delle Americhe | Normale (i risultati vengono memorizzati nella cache per utilizzi futuri) |
| 08:01 | L&#39;utente B apre il progetto | Istantanea |
| 08:05 | L&#39;utente B applica il segmento delle Americhe | Istantanea |
| 08:12 | L’utente B applica il segmento EMEA | Normale (i risultati vengono memorizzati nella cache per utilizzi futuri) |

>[!ENDSHADEBOX]

### Modifiche che causano l’aggiornamento dei risultati memorizzati nella cache con il successivo caricamento del progetto

Le seguenti modifiche alla configurazione sottostante di un progetto inducono Analysis Workspace ad aggiornare i risultati alla successiva apertura del progetto, anche se la finestra di 12 ore non è scaduta:

* Modifiche a una definizione di [metrica calcolata](/help/components/calculated-metrics/cm-overview.md) utilizzata nel progetto

* Modifiche a una definizione di segmento utilizzata nel progetto

I risultati vengono caricati a velocità normale e quindi memorizzati nella cache, che inizia una nuova finestra di 12 ore.

### Chi visualizza i risultati memorizzati nella cache

I risultati memorizzati in cache vengono visualizzati per impostazione predefinita per tutti coloro che:

* Ha accesso al progetto

* Ha accesso alle suite di rapporti utilizzate nel progetto

* Caricamento di una variante del progetto già memorizzata nella cache, ad esempio un progetto con gli stessi segmenti o le stesse selezioni a discesa del pannello (per ulteriori informazioni, vedere [Quali risultati vengono memorizzati nella cache](#what-results-are-cached))

Durante la visualizzazione dei risultati memorizzati nella cache, puoi visualizzare i dati più recenti [aggiornando manualmente i risultati](#manually-refresh-results-on-cached-projects).

### Quando lasciare i risultati memorizzati nella cache disattivati in un progetto

Alcuni progetti dipendono dai risultati per riflettere i dati più recenti ogni volta che qualcuno li apre. Questo è comune per i progetti che si basano fortemente su dati dello stesso giorno, dati in arrivo o [classificazioni](/help/components/classifications/classifications-overview.md) che vengono aggiornate frequentemente.

Lascia disabilitati i risultati memorizzati nella cache nel progetto se la maggior parte degli utenti che accedono al progetto deve visualizzare:

* **Dati del giorno corrente**

  Se un progetto viene memorizzato nella cache alle 07:00, i risultati non includono i dati che arrivano dopo le 07:00, fino alla scadenza dei risultati memorizzati nella cache alle 19:00.

* **Dati in arrivo ritardato**

  I dati in arrivo in ritardo hanno [marche temporali](/help/implement/vars/page-vars/timestamp.md) da un periodo di tempo precedente, ma arrivano dopo che tale periodo è passato. Ad esempio, i dati di [Origini dati](/help/import/data-sources/overview.md) provenienti da un call center potrebbero essere caricati il giorno successivo, oppure un&#39;app mobile potrebbe inviare hit memorizzati mentre è offline. I risultati memorizzati nella cache non includono questi dati fino alla scadenza.

* **Valori di classificazione aggiornati**

  I risultati memorizzati nella cache continuano a mostrare i valori di classificazione precedenti, ad esempio i nomi dei prodotti precedenti, fino alla scadenza.

>[!NOTE]
>
>Se queste esigenze si presentano solo occasionalmente, abilita i risultati memorizzati nella cache e [aggiorna il progetto manualmente](#manually-refresh-results-on-cached-projects) quando hai bisogno dei dati più recenti.

## Abilitare i risultati memorizzati nella cache per un progetto

Chiunque possa aggiornare le impostazioni del progetto può abilitare i risultati memorizzati nella cache. Questo include il proprietario del progetto e chiunque abbia il ruolo **[!UICONTROL Edit original]** per il progetto. Per ulteriori informazioni sui ruoli di progetto, vedere [Condividere un ruolo di progetto specifico](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

>[!IMPORTANT]
>
>I risultati memorizzati nella cache potrebbero non essere adatti se devi visualizzare immediatamente i dati del giorno corrente, quelli in arrivo o i valori di classificazione aggiornati. Prima di abilitare questa impostazione, controllare [Quando lasciare disabilitati i risultati memorizzati nella cache in un progetto](#when-to-leave-cached-results-disabled-on-a-project).

Nel progetto Workspace in cui desideri abilitare i risultati memorizzati nella cache per un caricamento più rapido:

1. Passa a **[!UICONTROL Projects]** > **[!UICONTROL Project info and settings]**.

1. Seleziona **[!UICONTROL Use cached results for faster loading]** (Aggiungi set di dati).

1. Seleziona **[!UICONTROL Save]** (Salva).

## Visualizza quando i risultati memorizzati in cache vengono visualizzati in un progetto

Quando vengono visualizzati i risultati memorizzati nella cache, nella parte superiore del progetto viene visualizzata una marca temporale. La marca temporale specifica se tutti i risultati sono memorizzati in cache o solo alcuni risultati:

* **[!UICONTROL Showing results from]&#x200B;[_data e ora_]**: tutti i pannelli del progetto mostrano i risultati memorizzati nella cache dalla data e dall&#39;ora visualizzate.

* **[!UICONTROL Showing some results from]&#x200B;[_data e ora_]**: alcuni pannelli mostrano i risultati memorizzati nella cache dalla data e dall&#39;ora visualizzate, mentre altri sono stati aggiornati più di recente.

![Timestamp sul progetto memorizzato nella cache](assets/project-cache-timestamp.png)

I pannelli visualizzano anche una marca temporale che indica quando i risultati sono stati memorizzati in cache:

* **[!UICONTROL Showing results from]&#x200B;[_data e ora_]**: il pannello mostra i risultati memorizzati nella cache dalla data e dall&#39;ora visualizzate.

  >[!NOTE]
  >
  >Questa opzione non è disponibile durante la fase alfa del rilascio.

## Aggiorna manualmente i risultati nei progetti memorizzati in cache

Solo i risultati mostrati nel progetto vengono memorizzati in cache. I dati sottostanti continuano a fluire in Adobe Analytics come di consueto.

Per visualizzare i dati più recenti prima della scadenza dei risultati memorizzati nella cache, puoi aggiornare manualmente i risultati di un progetto in qualsiasi momento durante la finestra delle 12 ore. Quando aggiorni l’intero progetto, inizia una nuova finestra di 12 ore e tutti coloro che aprono il progetto durante tale finestra visualizzano i risultati aggiornati.

Nel progetto Workspace in cui desideri visualizzare i dati più recenti, puoi aggiornare i risultati per l’intero progetto o per un singolo pannello.

### Aggiorna i risultati per l&#39;intero progetto

Per caricare i risultati più recenti per tutti i pannelli e iniziare una nuova finestra di 12 ore:

1. Seleziona l&#39;icona **[!UICONTROL Refresh]** ![Aggiorna](/help/assets/icons/Refresh.svg) nella parte superiore del progetto, accanto alla marca temporale del progetto.

### Aggiorna i risultati per un singolo pannello

>[!NOTE]
>
>Questa opzione non è disponibile durante la fase alfa del rilascio.

Per caricare i risultati più recenti solo per un singolo pannello:

1. Seleziona l&#39;icona **[!UICONTROL Refresh]** ![Aggiorna](/help/assets/icons/Refresh.svg) accanto alla marca temporale di un pannello.

