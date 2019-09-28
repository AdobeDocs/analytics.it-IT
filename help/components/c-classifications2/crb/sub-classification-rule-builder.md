---
description: È possibile combinare Generatore regole di classificazione con sottoclassificazioni per semplificare la gestione delle classificazioni e ridurre il numero di regole richieste. Potrebbe essere utile eseguire questa operazione se il codice di tracciamento è composto da codici da classificare separatamente.
seo-description: È possibile combinare Generatore regole di classificazione con sottoclassificazioni per semplificare la gestione delle classificazioni e ridurre il numero di regole richieste. Potrebbe essere utile eseguire questa operazione se il codice di tracciamento è composto da codici da classificare separatamente.
seo-title: 'Sottoclassificazioni e Generatore regole di classificazione: casi di utilizzo'
solution: Analytics
subtopic: Classificazioni
title: 'Sottoclassificazioni e Generatore regole di classificazione: casi di utilizzo'
topic: Strumenti di amministrazione
uuid: 6db6a4a9-b93c-413b-8049-1e6cc1ba4a38
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Sottoclassificazioni e Generatore regole di classificazione: casi di utilizzo

È possibile combinare Generatore regole di classificazione con sottoclassificazioni per semplificare la gestione delle classificazioni e ridurre il numero di regole richieste. Potrebbe essere utile eseguire questa operazione se il codice di tracciamento è composto da codici da classificare separatamente.

## Sottoclassificazioni e Generatore regole di classificazione: casi di utilizzo {#concept_6C8672C242544D7487E82886BBFABE6E}

È possibile combinare Generatore regole di classificazione con sottoclassificazioni per semplificare la gestione delle classificazioni e ridurre il numero di regole richieste. Potrebbe essere utile eseguire questa operazione se il codice di tracciamento è composto da codici da classificare separatamente.

Per informazioni concettuali sulle sottocategorie, consultate [Sottoclassificazioni](../../../components/c-classifications2/c-sub-classifications.md#concept_19EE5513A7DC43C38CC396E96F306CFE) .

**Esempio**

Presupponiamo il seguente codice di tracciamento:

`channel:broad_campaign:creative`

Una gerarchia di classificazione consente di applicare una classificazione a una classificazione (chiamata *`sub-classification`*). Ciò significa che è possibile utilizzare l'utilità di importazione come un database relazionale, con più tabelle. Una tabella mappa i codici di tracciamento completi alle chiavi, mentre un'altra li mappa ad altre tabelle.

![](assets/sub_class_table.png)

Dopo aver installato questa struttura, è possibile utilizzare il Generatore [regole di](../../../components/c-classifications2/crb/classification-rule-builder.md) classificazione per caricare file di piccole dimensioni che aggiornano solo le tabelle di ricerca (le tabelle verdi e rosse nell'immagine precedente). Quindi, potete utilizzare il generatore di regole per mantenere aggiornata la tabella di classificazione principale.

L'attività seguente descrive come eseguire questa operazione.

## Impostazione di sottoclassificazioni mediante il Generatore di regole{#task_2D9016D8B4E84DBDAF88555E5369546F}

<!-- 

t_rule_builder_subclass.xml

 -->

Esempi di passaggi che descrivono come caricare le sottocategorie utilizzando il Generatore di regole.

>[!NOTE]
>
>Questi passaggi descrivono come eseguire il caso d’uso descritto in [Sottoclassificazioni e nel Generatore](../../../components/c-classifications2/crb/sub-classification-rule-builder.md)di regole.

1. Creare classificazioni e sottoclassificazioni in Gestione [classificazione](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html).

   Esempio:

   ![Informazioni sul passaggio](assets/sub_class_create.png)

1. Nel Generatore [regole di](../../../components/c-classifications2/crb/classification-rule-builder.md#concept_C1F219E622044D43852EF5168FF7192A)classificazione, classificate la chiave di classificazione secondaria dal codice di tracciamento originale.

   A tale scopo, è necessario utilizzare un'espressione regolare. In questo esempio, la regola da compilare *`Broad Campaign code`* utilizzerebbe questa espressione regolare:

   | `#` | Tipo di regola | Corrispondenza | Imposta classificazione | A |
   |---|---|---|---|---|
   |  | Espressione regolare | `[^\:]:([^\:]):([^\:]`) | Codice campagna ampio | `$1` |
   |  | Espressione regolare | `[^\:]:([^\:]):([^\:]`) | Codice creativo | `$2` |

   >[!NOTE]
   >
   >A questo punto, non vengono compilate le sottoclassificazioni *`Campaign Type`* e *`Campaign Director`*.

1. Caricate un file di classificazione che include solo le sottoclassificazioni specificate.

   Consultate Classificazioni [a](../../../components/c-classifications2/c-sub-classifications.md#concept_35AD906CDDC4441DAAF70664CF76AA0A)più livelli.

   Esempio:

   | Chiave | Canale | Codice campagna ampio | Ampio codice campagna;Hat;Tipo campagna | Ampio codice campagna&amp;Hat;Campaign Director | ... |
   |---|---|---|---|---|---|
   | * |  | 111 | Brand (Marchio) | Suzanne |  |
   | * |  | 222 | Brand (Marchio) | Frank |  |

1. Per mantenere le tabelle di ricerca, caricate un file piccolo (come mostrato sopra).

   Caricate questo file, ad esempio, quando *`Broad Campaign code`* viene introdotto un nuovo file. Questo file viene applicato ai valori classificati in precedenza. Analogamente, se create una nuova classificazione secondaria ( *`Creative Theme`* ad esempio una classificazione secondaria di *`Creative code`*), caricate solo il file di classificazione secondaria, anziché l’intero file di classificazione.

   Per riportare queste sottocategorie, funziona esattamente come per le classificazioni di livello principale. Ciò riduce l'onere di gestione necessario per utilizzarli.
