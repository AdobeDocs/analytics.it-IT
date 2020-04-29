---
description: 'null'
title: Configurare una visualizzazione dell’abbandono
uuid: fc117745-baf3-46fb-873d-9307092cc337
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Configurare una visualizzazione dell’abbandono

Puoi specificare i punti di contatto per creare una sequenza di abbandono multidimensionale. In genere, un punto di contatto è una pagina del sito. Tuttavia, i punti di contatto non sono limitati alle pagine. Ad esempio, puoi aggiungere eventi (quali unità) nonché visitatori univoci e visite ripetute. Puoi anche aggiungere dimensioni, ad esempio una categoria, un tipo di browser e un termine di ricerca interna.

Puoi perfino aggiungere segmenti all’interno di un punto di contatto. Ad esempio, puoi confrontare segmenti quali utenti iOS e utenti Android. Trascina i segmenti desiderati nella parte superiore della sezione Abbandono per aggiungere al rapporto le informazioni su tali segmenti. Per mostrare solo tali segmenti, puoi rimuovere l’impostazione di base Tutte le visite.

Non esiste alcun limite al numero di passaggi che puoi aggiungere o al numero di dimensioni che puoi usare.

Puoi eseguire percorsi con variabili eVar, comprese le eVar di merchandising e [listVar](https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/page-variables.html) (variabili con più valori per hit, quali prodotti, listVar, eVar di merchandising ed elenchi di più valori list prop). Ad esempio, se qualcuno sta guardando “scarpe,camicie” su una pagina e “camicie,calze” sulla pagina successiva, il prossimo rapporto di flusso dei prodotti da “scarpe” sarà “camicie” e “calze” e NON “camicie”.

1. Trascina una visualizzazione [!UICONTROL Fallout] (Abbandono) dal menu a discesa Visualizzazioni in una [!UICONTROL Freeform Table] (Tabella a forma libera).

1. Trascina la dimensione Pagina nella tabella a forma libera, trascina una pagina (in questo esempio, Home - JJEsquire) nel campo **[!UICONTROL Add TouchPoint]** (Aggiungi punto di contatto) come primo punto di contatto.

   ![](assets/fallout1.png)

   Passa il cursore del mouse su un punto di contatto per vedere il relativo valore di abbandono e altre informazioni su tale livello, quali il nome del punto di contatto, il conteggio di visitatori per tale punto, e il relativo tasso di successo (nonché il confronto tra questo e il tasso di successo di altri punti di contatto).

   I numeri cerchiati nella porzione grigia della barra mostrano l’abbandono tra i punti di contatto (non l’abbandono complessivo per quel punto). Punto di contatto % mostra il corretto proseguimento dal passaggio precedente verso il passaggio corrente nel rapporto di abbandono.

   Puoi anche aggiungere una sola pagina al rapporto di abbandono, invece che l’intera dimensione. Fai clic sulla freccia destra “>” sulla dimensione pagina per scegliere la specifica pagina da aggiungere al rapporto di abbandono.

1. Continua ad aggiungere punti di contatto fino a completare la sequenza.

   Per **combinare più punti di contatto**, trascinali su un punto di contatto.

   >[!NOTE]
   >
   >Per unire più segmenti si usa l’operatore AND; per unire più elementi, ad esempio elementi dimensione, si usa l’operatore OR.

   ![](assets/multiple_obj_touchpoint.png)

1. Puoi anche **vincolare singoli punti di contatto all’hit successivo** (anziché alla fine) all’interno del percorso. Sotto ogni punto di contatto, un selettore consente di scegliere tra le opzioni “Eventual Path” (Percorso finale) e “Next Hit” (Hit successivo), come illustrato di seguito:

   ![](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Percorso finale </p> <p>(impostazione predefinita) </p> </td> 
   <td colname="col2"> <p>Conteggia i visitatori che accederanno alla pagina successiva del percorso, ma non necessariamente all’hit successivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hit successivo </p> </td> 
   <td colname="col2"> <p>Conteggia i visitatori che accederanno alla pagina successiva del percorso, in corrispondenza dell’hit successivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Impostazioni di Abbandono {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Impostazione | Descrizione |
|--- |--- |
| Contenitore Abbandono <ul><li>Visita</li><li>Visitatore</li></ul> | Consente di passare da Visita a Visitatore per analizzare il percorso dei visitatori. Il valore predefinito è Visitatore.  Queste impostazioni consentono di comprendere il coinvolgimento dei visitatori a livello dei singoli visitatori (attraverso più visite) o di limitare l’analisi a una singola visita. |
| Mostra “Tutti i visitatori” come primo punto di contatto | Puoi deselezionare questa opzione se preferisci non avere “Tutti i visitatori” come primo punto di contatto. |

Quando **fai clic con il pulsante destro del mouse su un punto di contatto**, vengono visualizzate le seguenti opzioni:

| Opzione | Descrizione |
|--- |--- |
| Tendenza punto di contatto | I dati di tendenza di un punto di contatto sono rappresentati in un grafico a linee, con alcuni dati di rilevamento anomalie pregenerati. |
| Tendenza punto di contatto (%) | Visualizza la tendenza della percentuale di abbandono totale. |
| Tendenza tutti i punti di contatto (%) | Visualizzare nello stesso grafico la tendenza di tutte le percentuali dei punti di contatto nell’abbandono (tranne Tutte le visite, se incluso). |
| Analisi approfondita a questo punto di contatto | Puoi vedere cosa hanno fatto i visitatori tra due punti di contatto (questo punto di contatto e il punto di contatto successivo) se hanno continuato fino al punto di contatto successivo. Viene creata una tabella a forma libera in cui sono riportate le dimensioni. Puoi sostituire le dimensioni e altri elementi della tabella. |
| Analisi abbandono a questo punto di contatto | Puoi vedere cosa hanno fatto, immediatamente dopo il passaggio selezionato, i visitatori che hanno abbandonato. |
| Crea segmento da punto di contatto | Crea un nuovo segmento dal punto di contatto selezionato. |
