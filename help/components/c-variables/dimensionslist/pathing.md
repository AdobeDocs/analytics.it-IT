---
description: Un gruppo di rapporti basati sull'analisi dei percorsi. Tecnicamente, per percorso si intende lo spostamento da un nome di pagina all’altro (da un valore all’altro).
solution: Analytics
title: Tracciatura percorso
topic: Reports
uuid: c4ff9fa8-e567-4039-9c86-322800a942da
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Tracciatura percorso

Un gruppo di rapporti basati sull'analisi dei percorsi. Tecnicamente, per percorso si intende lo spostamento da un nome di pagina all’altro (da un valore all’altro).

Utilizzate Flusso [di](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html) Analysis Workspace per opzioni di percorso più flessibili.

> [!NOTE] Per abilitare il percorso, passare a **[!UICONTROL Admin > Report Suites > Edit Settings > Traffic > Traffic Variables]**. Per abilitare il percorso nei rapporti Sezione del sito e Server, contatta l'Assistenza clienti.

Per conoscere l'ordine in cui vengono raccolti i valori, è necessario abilitare il percorso per la variabile che raccoglie tali valori. Il percorso è attivato per impostazione predefinita per le pagine. Il percorso non è abilitato per le proprietà per impostazione predefinita, perché è appropriato solo in alcuni casi. Contatta l’Assistenza clienti per abilitare il percorso di una prop.

> [!NOTE] In Analisi ad hoc, quando attivi le classificazioni su una prop, le metriche di percorso diventano disponibili per tutte le classificazioni configurate per la prop abilitata.

**Esempio - Percorsi sulle sezioni del sito**

Abilitando il percorso per la *`s.channel`* variabile è possibile tenere traccia dello spostamento dei visitatori del sito tra le sezioni del sito (man mano che il valore cambia).

![](assets/path_sections.png)

I percorsi sono quindi disponibili in vari rapporti sui percorsi, come [!UICONTROL Next Site Section Flow]ad esempio, che mostrano come i visitatori si spostano tra i gruppi di pagine o le sezioni del sito.

![](assets/paths_report.png)

**Esempio - Percorso delle ricerche**

Lo stesso concetto di passaggio da un valore a un altro si applica anche ad altre variabili di traffico, incluso *`s.props`*. Ad esempio, se attivi il percorso per il termine di ricerca interno, *`s.prop`* puoi vedere il percorso seguito dai visitatori attraverso i termini di ricerca.

**Esempio - Percorso per stato di accesso**

Potresti voler sapere come le persone si spostano nel tuo sito in base allo stato di accesso di un visitatore. Per visualizzare queste informazioni, non visualizzereste i rapporti sui percorsi per verificare lo stato di accesso, in quanto mostrerebbero come i visitatori hanno modificato i valori in quel rapporto, o come i visitatori potrebbero essere cambiati passando dal login al logout. Al contrario, concatenate il valore del segmento con la *`s.pageName`* variabile e quindi il percorso della variabile risultante. Di seguito è riportato un esempio di codice per il percorso della pagina per stato membro:

```js
s.pageName="Home Page"; 
s.prop18="Gold"; // Member Status 
s.prop19=s.prop18 + ":" + s.pageName;
```

Quindi, abilitate il percorso *`s.prop19`* per vedere come i membri si muovono attraverso le pagine.

> [!NOTE] Se si esegue un'analisi ad hoc, è possibile segmentare i percorsi di pagina senza la necessità di concatenare i valori dei segmenti e applicare qualsiasi segmento ai rapporti sui percorsi.

