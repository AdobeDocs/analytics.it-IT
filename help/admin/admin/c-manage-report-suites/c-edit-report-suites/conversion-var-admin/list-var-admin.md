---
title: Variabili elenco
description: Crea e configura variabili elenco da utilizzare nei rapporti.
feature: Admin Tools
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
source-git-commit: 21029930b5cae6acb6bc6a59836ddc1ca33cb27e
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 92%

---

# Variabili elenco

Crea e configura variabili elenco da utilizzare nei rapporti. Imposta il delimitatore, la scadenza, l’allocazione e i valori massimi.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Finding Methods]**

* **Nome**: ogni valore delimitato può contenere al massimo 255 caratteri (o meno se si utilizzano caratteri multibyte). È la lunghezza massima di ogni elemento.
* **Delimitatore valore**: carattere utilizzato per separare i valori nella variabile elenco. Nella maggior parte dei casi si tratta di caratteri come virgole, due punti, pipe o altri dello stesso tipo.

  >[!NOTE]
  >
  >I caratteri multibyte non sono supportati come delimitatori nelle variabili elenco. Il delimitatore deve essere un byte singolo.

* **Scade**: simile alla scadenza in eVar, questo campo determina il tempo che può trascorrere tra la variabile elenco e l’evento di conversione per effettuare la correlazione.
   * **A livello di visualizzazione pagina o di visita**: gli eventi di successo oltre la visualizzazione pagina o la visita non verranno collegati ai valori all’interno della variabile elenco.
   * **In base a un periodo di tempo, ad esempio giorno, settimana, mese e così via**: gli eventi di successo oltre il periodo di tempo specificato non verranno collegati a nessun valore all’interno della variabile elenco. È anche possibile definire un numero personalizzato di giorni.
   * **Eventi di conversione specifici**: qualsiasi altro evento di successo attivato dopo l’evento specifico designato non verrà collegato a nessun valore all’interno della variabile elenco.
   * **Mai**: qualsiasi quantità di tempo può passare tra la variabile elenco e l’evento di successo.

* **Allocazione**: questa impostazione determina il modo in cui gli eventi di successo dividono il credito tra i valori:
   * **Completo**: tutti i valori delle variabili definiti prima della scadenza della variabile ricevono il pieno credito per gli eventi di successo.
   * **Lineare**: tutti i valori delle variabili definiti prima della scadenza della variabile ricevono credito diviso per gli eventi di conversione.
   * I valori delle variabili non vengono mai sovrascritti, ma vengono aggiunti ai valori che ricevono credito per gli eventi di successo.

* **Valori massimi**: specifica il numero di valori attivi consentiti per questa variabile elenco. Ad esempio, se è impostato su 3, vengono salvati solo gli ultimi 3 valori acquisiti e tutti i valori precedenti acquisiti vengono scartati. Nota che se più valori per la stessa variabile elenco vengono inviati per lo stesso hit ed esiste un limite per l’uso dei valori massimi, ogni valore avrà la stessa marca temporale e non vi è alcuna garanzia riguardo al valore che viene salvato.

Un limite massimo di 250 valori viene memorizzato una volta per visitatore. Se vengono superati i 250 valori per visitatore, vengono usati gli ultimi 250 valori. La scadenza di tali valori si basa sulla scadenza configurata per la variabile.

L’impostazione dei valori massimi è utile per limitare l’attribuzione a un numero specifico di valori. Ad esempio, se una variabile elenco è impostata su “A, B, C” nella prima pagina di una visita e poi impostata su “X, Y, Z” nella pagina successiva, l’attribuzione viene distribuita a questi sei valori in base all’allocazione. Se vuoi limitare l’attribuzione solo a“X, Y, Z”, puoi impostare i valori massimi su tre.
