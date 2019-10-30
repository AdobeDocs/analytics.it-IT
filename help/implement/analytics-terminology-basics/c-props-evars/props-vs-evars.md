---
description: Esistono diversi tipi di variabili in Experience Cloud. I due tipi più diffusi, Prop ed eVar, consentono alla vostra organizzazione di creare rapporti sulle dimensioni personalizzate sul sito che i report standard out-of-the-box non offrono.
keywords: Implementazione di Analytics;prop;evar;prop vs evar;convenzione di denominazione;variabili di traffico;persistenza;evento di successo;percorso
seo-description: Esistono diversi tipi di variabili in Experience Cloud. I due tipi più diffusi, Prop ed eVar, consentono alla vostra organizzazione di creare rapporti sulle dimensioni personalizzate sul sito che i report standard out-of-the-box non offrono.
seo-title: Confronto di eventi, prop ed eVar
solution: Analytics
title: Confronto di eventi, prop ed eVar
topic: Sviluppatore e implementazione
uuid: 0f02760f-ff69-481c-a817-799f02dafe8e
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Confronto di eventi, prop ed eVar

Esistono diversi tipi di variabili in Experience Cloud. I due tipi più diffusi, Prop ed eVar, consentono alla vostra organizzazione di creare rapporti sulle dimensioni personalizzate sul sito che i report standard out-of-the-box non offrono.

Per determinare quali variabili vengono assegnate dove, è importante comprendere le differenze tra le funzionalità Prop e eVar. Comprendere queste differenze consente all'organizzazione di decidere quale tipo di variabile è più adatto all'uso.

**Prop vs eVar**

Di seguito sono riportate le principali differenze tra prop ed eVar:

* **Convenzione** di denominazione: Le proprietà sono considerate variabili di traffico, ovvero vengono utilizzate per generare report sulla popolarità di varie dimensioni del sito. Le eVar sono considerate variabili di conversione. Vengono utilizzati per determinare quali dimensioni del sito contribuiscono maggiormente agli eventi di successo.
* **Persistenza**: Le proprietà non persistono oltre la richiesta di immagine su cui sono state attivate. Non possono essere associati ad altre variabili che non si trovano nella stessa richiesta di immagine. Le eVar, tuttavia, sono persistenti. Una variabile back-end viene utilizzata per mantenere il valore originariamente attivato in modo che possa essere associata agli eventi di successo in seguito.
* **Eventi** di successo: Gli eventi di successo, noti anche come eventi di conversione, sono metriche che misurano il numero di volte in cui un visitatore raggiunge un obiettivo. Questo evento può essere qualsiasi cosa, dall’acquisto sul sito, all’iscrizione a una newsletter. Le eVar sono progettate per generare rapporti sugli eventi di conversione, per mostrare quali valori sono più efficaci nell'influenzare i visitatori a raggiungere i vostri obiettivi. Le variabili di traffico non hanno la stessa funzionalità. Tuttavia, potete visualizzare le metriche di partecipazione se configurate correttamente la suite di rapporti.
* **Percorso**: Le proprietà possono utilizzare il percorso, che consente alla vostra organizzazione di visualizzare un determinato percorso seguito da un utente nel contesto della variabile visualizzata. Un rappresentante Adobe può attivare il percorso, se richiesto. Le eVar non possono utilizzare il percorso.
* **Metriche** potenzialmente disponibili: Le metriche disponibili tra prop ed eVar variano notevolmente in base alle impostazioni della variabile e alla piattaforma/versione dati. L'elenco seguente illustra cosa può essere attivato, non cosa è attivato per impostazione predefinita. Se desideri una metrica specifica nel reporting ma non la vedi, chiedi a uno degli utenti supportati della tua organizzazione di contattare l'Assistenza clienti.

<table id="table_FB963F60857A4AD79562324FB6F4B6A9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Metrica </p> </th> 
   <th colname="col2" class="entry"> <p>Proprietà </p> <p>(Variabili di traffico) </p> </th> 
   <th colname="col3" class="entry"> <p>eVar </p> <p>(Variabili di conversione) </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Profondità media della pagina </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_165C1BF1574247CEA9190ADCABF79D69" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo medio trascorso </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_9F0F396E11B442959EC3E5D4D508496D" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percentuale non recapitate </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_A268EAF747EA45F8A6A93A1B66667A06" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_09D486144CEA4293A505DCA3F90B82EC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bounce </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_471A02B78FD842BB97ED3FF4A5908B03" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D2F11B5687484D9EBF6D1DEB3F303A20" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metriche calcolate </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_7FAB1CF2ACC44D9198C648D3FC9E52D9" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8BCC2EE92CC04778809D1BD48D2623D7" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eventi di conversione personalizzati </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D75C764B83AE4491A7E68C459FED1300" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Voci </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E9A1FCDFCB924D75ABFAEBD5570D4EE0" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5E57974B5A64F3FA3A145428420EB23" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uscite </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_BE343F94EAD74D54B6ABC80E8A76A9BD" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_3183B2BB62C24B048EDED3295F2BEC85" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Istanze </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8733F5AC189E43DAA8D1847416EA68C8" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_B10AB2898F3D4EBA947FADB27B118143" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visualizzazioni pagina </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8BD2B23FBDA64A648BED40A2993F7C1C" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_CBDFD74340FA4973847033C1F956F0AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metriche di partecipazione </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E63F978830FB46809E62654F37C4C182" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_6AB756A4598F4452887D29AD4971985A" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metriche di acquisto </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8F8AB7CD02764245BA73CA1E6B69BAE1" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ricariche </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_FBE0C84E01004937B7B408198A33A9E7" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metriche carrello acquisti </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_123993465D734EABB311730ED03263F6" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Accesso singolo </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_038C6991E3F341B18E7A355D17C88895" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo totale trascorso </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_090587D29F1649319033D5A15B34B138" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_841DF09FD32A44B1B1B876F4E0CE29AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitatori unici </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_38556E6A43B04E2E8A01855452D30A83" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5D4BDE1AA9C4C58A6402418390EEC52" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visite </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_017BB279C5824028870360A5D4D27556" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

* **Suddivisioni**: Le proprietà utilizzano le correlazioni, che visualizzano le visualizzazioni di pagina per altre variabili di traffico attivate nella stessa richiesta di immagine. Le eVar utilizzano le sottorelazioni, che forniscono una disaggregazione sulle altre variabili di conversione in relazione agli eventi di successo.

## Vantaggi esclusivi per proprietà o eVar {#section_B384031AB8674065BA5187B0A3A3DAB9}

Con la versione 15, le funzionalità tra Prop e eVar sono molto meno distinte. Le eVar sono state recentemente aggiornate per includere funzionalità quali visite/visitatori unici con un carico di elaborazione minimo, nonché metriche di percorsi.

Le proprietà presentano un paio di vantaggi delle eVar, alcuni dei quali possono essere aggirati:

* I dati prop vengono raccolti e disponibili nel reporting quasi immediatamente. La visualizzazione delle eVar nei dati della suite di rapporti può richiedere fino a 30 minuti.
* Tutti i prop possono avere rapporti simili a diagrammi di flusso abilitati, che consentono di visualizzare il percorso che i visitatori portano al sito. Questi rapporti sul flusso di percorso sono disponibili sia per Prop che per eVar in [!UICONTROL Ad Hoc Analysis].
* Le proprietà possono essere associate a più livelli, dove le eVar possono essere collegate solo una volta. Questa limitazione può essere attenuata utilizzando la segmentazione, fornendo dati identici come correlazioni.
* Le metriche di partecipazione consentono di vedere quali valori prop hanno partecipato prima di un evento di successo.

Le eVar presentano invece diversi vantaggi rispetto alla natura limitata dei Prop:

* Le eVar possono utilizzare eventi di successo come metriche. Le proprietà non possono.
* La scadenza dell'eVar può essere personalizzata, inclusa la scadenza di ogni hit (nessun valore persistente). Le proprietà non persistono in alcun modo.

Le metriche dei percorsi, come Tempo totale trascorso, Voci ed Uscite, non erano originariamente disponibili per le eVar. Tuttavia, gli aggiornamenti recenti hanno reso disponibili queste metriche, aumentando il valore delle eVar.

## Quale utilizzare {#section_022D016A4EEB45179A15BFF044A261A4}

**** Prop: Se la latenza è il problema maggiore e intendete misurare solo il traffico (eventi non di successo) con questa dimensione.

**** eVar: Se le suddivisioni dei dati e le relazioni sono le preoccupazioni maggiori.

>[!TIP]
>
>Se non si desidera che un'eVar persista, è possibile modificarne la scadenza in "hit" in modo che non contenga dati oltre l'hit.

