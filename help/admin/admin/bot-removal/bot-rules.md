---
description: Regole bot consente di rimuovere il traffico generato da spider noti e bot dalla suite di rapporti. La rimozione del traffico bot permette di misurare meglio l'attività degli utenti sul sito Web.
seo-description: Regole bot consente di rimuovere il traffico generato da spider noti e bot dalla suite di rapporti. La rimozione del traffico bot permette di misurare meglio l'attività degli utenti sul sito Web.
seo-title: Regole bot
solution: Analytics
subtopic: Regole bot
title: Regole bot
topic: Strumenti di amministrazione
uuid: 3 cb 9 e 29 d -1 c 37-43 de-b 7 ac -34441093 a 60 e
translation-type: tm+mt
source-git-commit: 4a627e268994d0152a19fb44e9bc06ea7ebc64c6

---


# Regole bot

Regole bot consente di rimuovere il traffico dalla suite di rapporti generata da spider e bot noti. La rimozione del traffico bot permette di misurare meglio l'attività degli utenti sul sito Web.

Dopo la definizione delle regole bot, tutto il traffico in arrivo viene confrontato con le regole definite. Il traffico che corrisponde a una di queste regole non viene raccolto nella suite di rapporti e non è incluso nelle metriche del traffico.

Per aggiornare o caricare le regole bot, passa **[!UICONTROL Analytics]** a &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**. Seleziona la suite di rapporti corretta, quindi vai a **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.

La rimozione del traffico bot in genere riduce il volume di traffico e le metriche di conversione. Molti clienti ritengono che la rimozione del traffico bot determini tassi di conversione aumentati e aumenti in altre metriche di usabilità. Prima di rimuovere il traffico bot, comunicate con i soggetti interessati affinché possano apportare le modifiche necessarie agli indicatori delle prestazioni chiave a seguito di questa modifica. Se possibile, si consiglia di rimuovere prima il traffico bot da una piccola suite di rapporti per stimare il potenziale impatto.

>[!NOTE] Consigliamo di definire on più di 500 regole bot per suite di rapporti. L'interfaccia utente consente di definire manualmente 500 regole. After this limit is reached, rules must be managed in bulk through the [Import File](../../../admin/admin/bot-removal/t-upload-bot-rules.md#task_95868D8564564E6A996163335C119806) and Export Bot Rules options.

I dati del traffico bot vengono memorizzati in un archivio separato per essere visualizzati nei rapporti [!UICONTROL Bots] e [!UICONTROL Bot Pages] nei rapporti.

| Tipo di regola | Descrizione |
|--- |--- |
| IAB | Selezionando [!UICONTROL Include IAB] usa l'elenco internazionale di IAB (International Advertising Bureau) International Spiders &amp; Bots List per rimuovere il traffico bot. Questo elenco viene aggiornato mensilmente dall'IAB. <br>Per inviare un bot all'elenco IAB, visita [IAB](https://www.iab.net/sites/spiders/form.php). <br>Adobe non è in grado di fornire l'elenco bot IAB dettagliato ai clienti, anche se potete utilizzare il report Bots per visualizzare un elenco di bot che hanno eseguito l'accesso al sito. |
| Regole bot personalizzate | See [Create a custom bot rule](../../../admin/admin/bot-removal/t-create-bot-rules.md). |

## Impatto delle regole bot sulla raccolta dati {#section_F01A3130E7A04A9993371CF26F6586F2}

Regole bot vengono applicate a tutti i dati di analisi. I dati rimossi da Regole bot sono visibili solo nei report Bots e Bot Pages.

Le regole VISTA vengono applicate dopo Regole bot (consultate [Ordine di elaborazione](../../../admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E)).

**Elaborazione visite ad alto hit:** Se in una visita si verificano più di 100 hit, il reporting determina se l'ora della visita in secondi è inferiore o uguale al numero di hit nella visita. In questa situazione, a causa del costo di elaborazione di visite lunghe e intense, il reporting inizia con una nuova visita. Le visite ad alto hit sono in genere causate da attacchi bot e non sono considerate esplorazioni normali dei visitatori.

>[!NOTE]
>
>Gli hit contrassegnati come *`bots`* sono fatturati come [chiamate al server](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/overage-overview.html).

## Impatto dell'oscuramento IP sul filtro bot {#section_92E60B95BE8940D983F28C79E0CD6B12}

L'elenco bot IAB si basa unicamente sull'agente utente, pertanto il filtraggio basato su tale elenco non viene influenzato dalle impostazioni di offuscamento IP. Per filtraggio bot non IAB (regole personalizzate), l'IP potrebbe far parte dei criteri di filtro. Se si filtrano i bot utilizzando IP, il filtro bot viene eseguito dopo che l'ultimo ottetto è stato rimosso, se questa impostazione è attivata, ma prima delle altre opzioni di oscuramento IP, ad esempio eliminando l'intero IP o sostituendolo con un ID univoco.

Se l'offuscamento IP è abilitato, l'esclusione IP avviene prima che l'indirizzo IP non venga oscurato, in modo che i clienti non debbano modificare nulla quando abilitano l'offuscamento IP.

Se l'ultimo ottetto viene rimosso, viene eseguito prima del filtro IP. Pertanto, l'ultimo ottetto viene sostituito con un 0 e le regole di esclusione IP devono essere aggiornate per corrispondere agli indirizzi IP con uno zero alla fine. Corrispondenza * deve corrispondere a 0.
