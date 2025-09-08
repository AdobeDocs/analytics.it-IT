---
description: Casi di utilizzo comuni per le regole di elaborazione.
subtopic: Processing rules
title: Casi di utilizzo delle regole di elaborazione
feature: Processing Rules
role: Admin
exl-id: 914a0d31-d256-456e-a44a-008490e86a23
source-git-commit: 0616f35599fd40ee8b88f7809f943bb11a84429b
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 26%

---

# Casi di utilizzo delle regole di elaborazione

Le modalità di utilizzo delle regole di elaborazione all’interno dell’organizzazione sono molto estese. Le sezioni seguenti illustrano alcuni modi comuni per utilizzarli a proprio vantaggio.

+++Copiare una variabile di dati di contesto in una eVar

Le regole di elaborazione vengono utilizzate per spostare i valori da [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) a [Prop](/help/components/dimensions/prop.md) e [eVar](/help/components/dimensions/evar.md). Senza regole di elaborazione, le variabili dei dati di contesto sono prive di significato e non compilano alcun rapporto in Analytics.

L&#39;elenco [!UICONTROL Context Variables] contiene tutte le variabili inviate alla suite di rapporti negli ultimi 30 giorni. Se conosci il nome della variabile di dati di contesto ma non lo hai inviato alla suite di rapporti corrente, puoi aggiungerlo manualmente:

![Aggiunta manuale di una variabile di dati di contesto a una regola di elaborazione](assets/add-context-variable.png)

L&#39;esempio seguente prende la variabile di dati di contesto `search_term` e inserisce il relativo valore in eVar3:

| Set di regole | Valore |
| --- | --- |
| Condizione | `search_term` (dati contestuali) è impostato |
| Azione | [!UICONTROL Overwrite value of] eVar3 con `search_term` (dati contestuali) |

![Schermata dell&#39;interfaccia delle regole di elaborazione che mostra l&#39;utilizzo di una variabile di dati di contesto](assets/set-context-data.png)

L’esempio precedente funziona benissimo quando sono presenti solo poche eVar da compilare. Se nell’organizzazione sono presenti centinaia di variabili di dati di contesto che necessitano di una propria eVar, puoi utilizzare le istruzioni condizionali. Decine di istruzioni condizionali possono rientrare in un’unica regola di elaborazione, consentendo all’organizzazione di compilare tutte le eVar in una suite di rapporti senza incorrere nel limite di 150 regole di elaborazione.

L’esempio seguente compila più variabili con variabili di dati di contesto diverse. Un’azione contiene anche un’istruzione condizionale:

| Set di regole | Valore |
| --- | --- |
| Azione | [!UICONTROL Overwrite value of] eVar55 con `spa.billing_customer_name` (dati contestuali) |
| Azione | [!UICONTROL Overwrite value of] Prop7 con `testhierarchy` (dati contestuali), se `testhierarchy` (dati contestuali) è impostato |
| Azione | [!UICONTROL Overwrite value of] eVar8 con `spa.ims_org` (dati contestuali) |

![Schermata dell&#39;interfaccia delle regole di elaborazione che mostra come impostare un valore in modo condizionale](assets/add-conditional.png)

+++

+++Impostare un evento utilizzando una variabile di dati di contesto

Le regole di elaborazione possono attivare eventi in base a [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md).

L&#39;elenco [!UICONTROL Context Variables] contiene tutte le variabili inviate alla suite di rapporti negli ultimi 30 giorni. Se conosci il nome della variabile di dati di contesto ma non lo hai inviato alla suite di rapporti corrente, puoi aggiungerlo manualmente:

![Aggiunta manuale di una variabile di dati di contesto a una regola di elaborazione](assets/add-context-variable.png)

La seguente definizione di regola imposta un evento su ogni hit che contiene una variabile di dati di contesto specifica:

| Set di regole | Valore |
| --- | --- |
| Condizione | `search_term` (dati contestuali) è impostato |
| Azione | [!UICONTROL Set event] Evento1 a [!UICONTROL Custom Value] `1` |

![Schermata dell&#39;interfaccia delle regole di elaborazione che mostra come impostare un evento](assets/processing_rule_set_event.png)

+++

+++Compilare una variabile utilizzando un parametro di stringa query

È possibile compilare una variabile utilizzando un parametro di stringa query. Nella maggior parte dei casi, in genere si regola l’implementazione per ottenere i valori di stringa di query desiderati. Tuttavia, se non riesci a regolare facilmente l’implementazione per raccogliere questi dati, le regole di elaborazione rappresentano un’alternativa adeguata. Se un errore di battitura o altro problema simile impedisce la compilazione del valore, è possibile compilare la variabile utilizzando le regole di elaborazione.

Prima di sovrascriverlo, controlla sempre se un valore è vuoto o contiene il valore previsto.

| Set di regole | Valore |
| --- | --- |
| Condizione | Campagna non impostata |
| Azione | [!UICONTROL Overwrite value of] campagna con [!UICONTROL Query String Parameter] `cpid` |

![Schermata dell&#39;interfaccia delle regole di elaborazione che mostra la logica condizionale della campagna](assets/set-campaign-conditionally.png)

| Set di regole | Valore |
| --- | --- |
| Condizione | [!UICONTROL Query String Parameter] `q` [!UICONTROL Is Set] |
| Azione | [!UICONTROL Overwrite value of] Termini di ricerca interni con [!UICONTROL Query String Parameter] `q` |

![Schermata dell&#39;interfaccia delle regole di elaborazione che mostra la logica interna dei termini di ricerca](assets/populate-internal-search-terms.png)

+++

+++Imposta in modo condizionale qualsiasi evento

Gli eventi possono essere impostati in base a qualsiasi condizione disponibile nelle regole di elaborazione. Ad esempio, puoi attivare un evento quando il nome della pagina è &quot;Panoramica prodotto&quot;.

| Set di regole | Valore |
| --- | --- |
| Condizione | Se [!UICONTROL Page Name] È Uguale A &quot;Panoramica Prodotto&quot; |
| Azione | [!UICONTROL Set event] [!UICONTROL Product Views] A [!UICONTROL Custom Value] `1` |

![Schermata dell&#39;interfaccia delle regole di elaborazione che mostra un set di eventi condizionale](assets/set-product-view-event.png)

+++

+++Aggiungere una sottocategoria concatenando la categoria e il nome della pagina

L’opzione di concatenamento consente di popolare i valori combinando altri valori.

| Set di regole | Valore |
| --- | --- |
| Condizione | Nessuno (esegui sempre) |
| Azione | [!UICONTROL Overwrite value of] eVar1 con categoria [!UICONTROL Concatenated Value] e nome pagina |

![Schermata dell&#39;interfaccia delle regole di elaborazione che mostra un valore concatenato](assets/add-subcategory-using-concat.png)

+++

+++Pulire i valori in un rapporto

Puoi confrontare i valori con gli errori ortografici raccolti e aggiornarli in modo da visualizzarli correttamente nei rapporti.

Adobe consiglia di utilizzare l’opzione di corrispondenza più restrittiva possibile per evitare sovrascritture indesiderate. Puoi eseguire un rapporto sulla variabile e cercare le potenziali condizioni della regola che desideri utilizzare. Per i confronti tra stringhe non viene fatta distinzione tra maiuscole e minuscole.

| Set di regole | Valore |
| --- | --- |
| Condizione | Se prop1 [!UICONTROL Starts With] &quot;[!DNL Shoping]&quot; |
| Azione | [!UICONTROL Overwrite value of] Proprietà Con [!UICONTROL Custom Value] &quot;[!DNL Shopping]&quot; |

![Schermata dell&#39;interfaccia delle regole di elaborazione che mostra come correggere un errore di battitura](assets/clean-up-values-in-report.png)

+++

+++Rimuovere un evento da un hit

Puoi rimuovere o eliminare un evento specifico da un hit utilizzando le regole di elaborazione senza modificare l’implementazione. Se si imposta l&#39;evento sul valore personalizzato `0`, l&#39;evento non verrà conteggiato.

| Set di regole | Valore |
| Condizione | Nessuno (esegui sempre) |
| Azione | [!UICONTROL Set event] Evento1 a [!UICONTROL Custom value] `0` |

![Schermata dell&#39;interfaccia delle regole di elaborazione visualizzata in per rimuovere un evento](assets/remove_event.png)

+++
