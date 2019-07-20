---
description: Quando un rapporto dispone di un numero elevato di valori univoci, Adobe fornisce funzionalità per garantire che nel rapporto vengano visualizzati i valori più importanti.
seo-description: Quando un rapporto dispone di un numero elevato di valori univoci, Adobe fornisce funzionalità per garantire che nel rapporto vengano visualizzati i valori più importanti.
seo-title: Valore del traffico insufficiente in Adobe Analytics
solution: Analytics
title: Valore del traffico insufficiente in Adobe Analytics
topic: Metrics (Metriche)
uuid: 56 f 723 f 8-94 e 8-478 f -8 ea 3-16 dad 21 dfa 1 f
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Valore del traffico insufficiente in Adobe Analytics

Quando un rapporto dispone di un numero elevato di valori univoci, Adobe fornisce funzionalità per garantire che nel rapporto vengano visualizzati i valori più importanti. Unique variable values collected after approximately 500,000 existing values are listed under a line item titled **(Low-Traffic)**.

## Funzionamento del traffico

* I rapporti non vengono modificati se la variabile non raggiunge 500,000 valori univoci in un dato mese.
* Quando una variabile raggiunge la prima soglia di 500,000, i dati iniziano a muoversi in basso traffico. Ogni valore oltre questa soglia attraversa la seguente logica:
   * Se un valore è già presente nei rapporti, aggiungete a tale valore come al solito.
   * Se un valore non è ancora in fase di reporting, verificate che tale valore sia stato visualizzato più di dieci volte al giorno. In caso affermativo, aggiungete questo valore al reporting. Se non viene conteggiato più di dieci volte, lasciatelo in basso traffico.
* Se una suite di rapporti raggiunge più di 1,000,000 valori univoci, viene applicato un filtro più aggressivo:
   * Se un valore è già presente nei rapporti, aggiungete a tale valore come al solito.
   * Se un valore non è ancora in fase di reporting, verificate che tale valore sia stato visualizzato più di circa 100 volte. In caso affermativo, aggiungete il valore al reporting. In caso contrario, lasciatela in basso traffico.

> [!NOTE] Se un valore di variabile riceve un traffico sufficiente a lasciare il bucket basso, i primi valori raccolti non passano al relativo elemento della riga. Le prime 10-100 istanze restano in basso traffico.

## Modifica delle soglie di limite univoche

Per impostazione predefinita, i limiti di soglia sono compresi tra 500,000 e 1 milioni di valori univoci. Questi limiti possono essere modificati a livello di singola variabile. Contattate il responsabile commerciale dell'organizzazione per richiedere questa modifica. Quando richiedete una modifica, includete:

* ID suite di rapporti
* La variabile di cui desiderate aumentare la soglia
* La prima e la seconda soglia desiderata

Questa modifica può avere un costo aggiuntivo e dipende dal contratto. Anche le modifiche alle soglie possono influire sulle prestazioni dei rapporti. Adobe consiglia vivamente di utilizzare un buon giudizio quando si richiede un aumento a valori univoci in una variabile.

Le soglie di traffico basso non sono visibili nell'interfaccia utente di Analytics. Se desideri ricevere ulteriori informazioni sulle soglie esistenti, chiedi all'assistenza clienti di contattare l'Assistenza clienti.

## Traffico con componenti e altre funzionalità

Diverse funzionalità gestiscono i valori di traffico basso in modi diversi.

* **Data Warehouse:** Non esiste alcun limite al numero di valori univoci nei report Data Warehouse. La sua unica architettura consente di generare rapporti su qualsiasi numero di valori univoci.
   * In alcuni scenari limitati, i valori di traffico basso possono comunque essere visualizzati. Gli esempi includono variabili elenco, proprietà elenco, evar di merchandising e dimensioni del dettaglio del canale di marketing.
* **Segmentazione:** Se i criteri del segmento includono una variabile con un numero elevato di valori univoci, i valori acquisiti in basso traffico non sono inclusi.
* **Classificazioni:** I rapporti di classificazione sono soggetti anche a limiti univoci. Se il valore della variabile principale di una classificazione è incluso in un traffico basso, il valore non è classificato.
   * Se si classificano i valori prima che siano visibili nei dati, questi valori contano verso la soglia univoca di quel mese.
