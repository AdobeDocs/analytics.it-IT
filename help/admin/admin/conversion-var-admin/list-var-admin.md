---
title: Variabili elenco
description: Creare e configurare le variabili di elenco da utilizzare nei rapporti.
translation-type: tm+mt
source-git-commit: a492de4ccbcd6f3f8ca81c9fecbcca4780e0f589
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 6%

---


# Variabili elenco

Creare e configurare le variabili di elenco da utilizzare nei rapporti. Impostate qui i valori di delimitatore, scadenza, allocazione e max.

Potete accedere alla configurazione nel Admin Console :

1. Vai a  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**
2. Seleziona la suite di rapporti.
3. Fai clic su  **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]** .

* **Nome**: Ogni valore delimitato può contenere un massimo di 255 caratteri (o meno se si utilizzano caratteri multibyte). Questa è la lunghezza massima di ogni elemento.
* **Delimitatore** valore: Il carattere utilizzato per separare i valori all&#39;interno della Var elenco. Nella maggior parte dei casi, si tratta di caratteri quali virgole, due punti, una tubatura o qualcosa di simile.

   >[!NOTE] I caratteri multibyte non sono supportati come delimitatori nelle variabili di elenco. Il delimitatore deve essere a byte singolo.

* **Scadenza**: Simile alla scadenza  eVar, questo determina il tempo che può trascorrere tra la Var dell&#39;elenco e l&#39;evento di conversione per il quale devono essere correlati.
   * **A un livello** di visualizzazione pagina o visita: Gli eventi di successo oltre la visualizzazione della pagina o la visita non verrebbero collegati ad alcun valore all’interno della Var elenco.
   * **In base a un periodo di tempo, ad esempio giorno, settimana, mese, ecc**.: Gli eventi di successo oltre il periodo di tempo specificato non verrebbero collegati ad alcun valore all&#39;interno della Var elenco. È inoltre possibile definire un numero personalizzato di giorni.
   * **Eventi** di conversione specifici: Eventuali altri eventi di successo attivati dopo lo specifico evento designato non verranno collegati ai valori all&#39;interno della Var elenco.
   * **Mai**: Qualsiasi quantità di tempo può passare tra la Var elenco e l&#39;evento success.

* **Allocazione**: Questa impostazione determina in che modo gli eventi di successo dividono il credito tra i valori:
   * **Completa**: Tutti i valori delle variabili definiti prima della scadenza della variabile ottengono il credito completo per gli eventi di successo.
   * **Lineare**: Tutti i valori delle variabili definiti prima della scadenza della variabile ricevono credito diviso per gli eventi di conversione.
   * I valori delle variabili non vengono mai sovrascritti, ma vengono aggiunti ai valori che vengono accreditati per gli eventi di successo.

* **Valori** max: Indica il numero di valori attivi consentiti per questa variabile dell&#39;elenco. Ad esempio, se è impostato su 3, vengono salvati solo gli ultimi 3 valori acquisiti e tutti i valori acquisiti in precedenza vengono scartati. Tenere presente che se più valori per lo stesso elenco var vengono inviati nello stesso hit e avete applicato delle restrizioni utilizzando i valori massimi, ogni valore avrà la stessa marca temporale e non vi è alcuna garanzia per quale valore viene salvato.

Un limite massimo di 250 valori viene memorizzato alla volta per ogni visitatore. Se vengono superati i 250 valori per visitatore, vengono usati gli ultimi 250 valori. La scadenza di tali valori si basa sulla scadenza configurata per la variabile.

L’impostazione Valori massimi è utile per limitare l’attribuzione a un numero specifico di valori. Ad esempio, se una variabile di elenco è impostata su &quot;A,B,C&quot; nella prima pagina di una visita e quindi su &quot;X,Y,Z&quot; nella pagina successiva, l&#39;attribuzione viene distribuita a questi sei valori in base all&#39;allocazione. Se desiderate limitare l’attribuzione solo a &quot;X,Y,Z&quot;, potete impostare i valori massimi su tre.
