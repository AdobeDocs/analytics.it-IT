---
title: Variabili elenco
description: Crea e configura variabili di elenco da utilizzare nei rapporti.
feature: Admin Tools
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 6%

---

# Variabili elenco

Crea e configura variabili di elenco da utilizzare nei rapporti. Imposta qui i valori delimitatore, scadenza, allocazione e max.

Puoi accedere alla configurazione nell’Admin Console:

1. Vai a  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**
2. Seleziona la suite di rapporti.
3. Fai clic su  **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]** .

* **Nome**: Ogni valore delimitato può contenere un massimo di 255 caratteri (o meno se si utilizzano caratteri multibyte). È la lunghezza massima di ogni elemento.
* **Delimitatore valore**: Carattere utilizzato per separare i valori all’interno della Var elenco. Nella maggior parte dei casi si tratta di caratteri quali virgole, due punti, un tubo o qualcosa di simile.

   >[!NOTE]
   >
   >I caratteri multibyte non sono supportati come delimitatori nelle Var elenco. Il delimitatore deve essere un byte singolo.

* **Scadenza**: Simile alla scadenza di eVar, questo determina il tempo che può trascorrere tra la Var elenco e l’evento di conversione per correlarli.
   * **A livello di visualizzazione di una pagina o di una visita**: Gli eventi di successo al di là della visualizzazione della pagina o della visita non verranno collegati ai valori all’interno della Var elenco.
   * **In base a un periodo di tempo, ad esempio giorno, settimana, mese e così via**: Gli eventi di successo oltre il periodo di tempo specificato non verranno collegati a nessun valore all’interno della Var elenco. È inoltre possibile definire un numero personalizzato di giorni.
   * **Eventi di conversione specifici**: Qualsiasi altro evento di successo attivato dopo l’evento specifico designato non verrà collegato a nessun valore all’interno della Var elenco.
   * **Mai**: Qualsiasi quantità di tempo può passare tra la Var elenco e l’evento di successo.

* **Allocazione**: Questa impostazione determina il modo in cui gli eventi di successo dividono il credito tra i valori:
   * **Completo**: Tutti i valori delle variabili definiti prima della scadenza della variabile ottengono il pieno credito per gli eventi di successo.
   * **Lineare**: Tutti i valori delle variabili definiti prima della scadenza della variabile ricevono credito diviso per gli eventi di conversione.
   * I valori delle variabili non vengono mai sovrascritti, ma vengono aggiunti ai valori che ricevono credito per gli eventi di successo.

* **Valori massimi**: Indica il numero di valori attivi consentiti per questa variabile di elenco. Ad esempio, se è impostato su 3, vengono salvati solo gli ultimi 3 valori acquisiti e tutti i valori precedenti acquisiti vengono scartati. Nota che se più valori per lo stesso elenco var vengono inviati sullo stesso hit e si è limitati utilizzando valori massimi, ogni valore avrà la stessa marca temporale e non vi è alcuna garanzia su quale valore viene salvato.

Un limite massimo di 250 valori viene memorizzato una volta per visitatore. Se vengono superati i 250 valori per visitatore, vengono usati gli ultimi 250 valori. La scadenza di tali valori si basa sulla scadenza configurata per la variabile.

L’impostazione Max Values è utile per limitare l’attribuzione a un numero specifico di valori. Ad esempio, se una var elenco è impostata su &quot;A,B,C&quot; nella prima pagina di una visita e poi impostata su &quot;X,Y,Z&quot; nella pagina successiva, l’attribuzione viene distribuita a questi sei valori in base all’allocazione. Se desideri limitare l’attribuzione a solo &quot;X,Y,Z&quot;, puoi impostare valori massimi a tre.
