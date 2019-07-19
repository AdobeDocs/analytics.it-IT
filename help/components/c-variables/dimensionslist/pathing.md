---
description: Gruppo di rapporti basati sull'analisi dei percorsi. Tecnicamente, i percorsi passano da un nome di pagina a un altro (da un valore a un altro).
seo-description: Gruppo di rapporti basati sull'analisi dei percorsi. Tecnicamente, i percorsi passano da un nome di pagina a un altro (da un valore a un altro).
seo-title: Percorsi
solution: Analytics
title: Percorsi
topic: Rapporti
uuid: c 4 ff 9 fa 8-e 567-4039-9 c 86-322800 a 942 da
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Percorsi

Gruppo di rapporti basati sull'analisi dei percorsi. Tecnicamente, i percorsi passano da un nome di pagina a un altro (da un valore a un altro).

Use [Analysis Workspace Flow](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html) for more flexible pathing options.

>[!NOTE]
>
>To enable pathing, go to **[!UICONTROL Admin > Report Suites > Edit Settings > Traffic > Traffic Variables]**. Per abilitare i percorsi nei rapporti Site Section e Server, contatta l'Assistenza clienti.

Se è necessario conoscere l'ordine in cui vengono raccolti i valori, è necessario abilitare i percorsi per la variabile che raccoglie tali valori. Per impostazione predefinita, i percorsi sono abilitati per le pagine. Per impostazione predefinita, i percorsi non sono attivati per impostazione predefinita, perché sono appropriati solo in alcuni casi. Contatta l'Assistenza clienti per abilitare i percorsi su un prop.

>[!NOTE]
>
>In Analisi ad hoc, quando abilitate classificazioni su una prop, le metriche di percorsi diventano disponibili per tutte le classificazioni configurate per il prop abilitato.

**Esempio - Percorsi sulle sezioni del sito**

Enabling pathing for the *`s.channel`* variable allows you to track how site visitors move between Site Sections (as the value changes).

![](assets/path_sections.png)

Pathing is then available in various paths reports, such as [!UICONTROL Next Site Section Flow], which displays how visitors move through page groups, or sections of your site.

![](assets/paths_report.png)

**Esempio - Percorsi sulle ricerche**

This same concept of going from one value to another value applies to other traffic variables as well, including *`s.props`*. For example, if you enable pathing for your Internal Search Term *`s.prop`*, you could see the path visitors take through search terms.

**Esempio - Percorsi per lo stato di login**

Potrebbe essere utile sapere in che modo le persone navigano sul sito in base allo stato di accesso di un visitatore. Per visualizzare queste informazioni, non visualizzerai i rapporti percorsi per lo stato di accesso, perché mostrano in che modo i visitatori hanno modificato i valori in quel rapporto o in che modo i visitatori potrebbero aver effettuato l'accesso. Instead, concatenate the segment value with the *`s.pageName`* variable, and then path that resultant variable. Di seguito è riportato un codice di esempio per il percorso della pagina per stato membro:

```js
s.pageName=“Home Page”; 
s.prop18=“Gold”; // Member Status 
s.prop19=s.prop18 + “:” + s.pageName;
```

Then, enable pathing for *`s.prop19`* to see how members path through pages.

>[!NOTE]
>
>Se esegui analisi ad hoc, puoi segmentare i percorsi delle pagine senza dover concatenare i valori dei segmenti e applicare qualsiasi segmento ai rapporti sui percorsi.

