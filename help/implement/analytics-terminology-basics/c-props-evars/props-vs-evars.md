---
description: In Experience Cloud sono disponibili diversi tipi di variabili. I due tipi più popolari, Prop ed evar, consentono all'organizzazione di effettuare rapporti su dimensioni personalizzate al sito che i rapporti standard non offrono.
keywords: Implementazione di Analytics; prop; evar; prop vs evar; convenzione di denominazione; variabili di traffico; persistenza; evento success; papath
seo-description: In Experience Cloud sono disponibili diversi tipi di variabili. I due tipi più popolari, Prop ed evar, consentono all'organizzazione di effettuare rapporti su dimensioni personalizzate al sito che i rapporti standard non offrono.
seo-title: Confronto di prop ed evar
solution: Analytics
title: Confronto di prop ed evar
topic: Sviluppatore e implementazione
uuid: 0 f 02760 f-ff 69-481 c-a 817-799 f 02 dafe 8 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Confronto di prop ed evar

In Experience Cloud sono disponibili diversi tipi di variabili. I due tipi più popolari, Prop ed evar, consentono all'organizzazione di effettuare rapporti su dimensioni personalizzate al sito che i rapporti standard non offrono.

Per determinare quali variabili vengono assegnate dove, è importante comprendere le differenze tra le funzionalità Prop e evar. Comprendere queste differenze consente all'organizzazione di stabilire quale tipo di variabile è più efficace.

**Prop vs evar**

Di seguito sono riportate le differenze principali tra prop e evar:

* **Convenzione di denominazione**: Le proprietà sono considerate variabili di traffico, ovvero vengono utilizzate per generare rapporti sulla popolarità delle varie dimensioni del sito. Le evar sono considerate variabili di conversione. Vengono utilizzati per determinare quali dimensioni del sito contribuiscono maggiormente agli eventi di successo.
* **Persistenza**: Prop non persiste oltre la richiesta di immagine su cui sono stati attivati. Non possono essere associati ad altre variabili che non si trovano nella stessa richiesta di immagine. Le evar, tuttavia, sono persistenti. Viene utilizzata una variabile di back-end per mantenere il valore inizialmente attivato, in modo che possa essere associato agli eventi di successo in seguito.
* **Eventi di successo**: Gli eventi di successo, noti anche come eventi di conversione, sono metriche che misurano il numero di volte che un visitatore raggiunge un obiettivo. Per effettuare l'iscrizione a una newsletter, è possibile che si verifichi un qualsiasi acquisto sul sito. Le evar sono progettate per generare rapporti sugli eventi di conversione, per mostrare quali valori hanno maggior successo nell'influenzare i visitatori per raggiungere gli obiettivi. Le variabili di traffico non hanno la stessa funzionalità. Tuttavia, potete visualizzare le metriche di partecipazione se configurate correttamente la suite di rapporti.
* **Percorso**: Prop può utilizzare i percorsi, che consentono all'organizzazione di visualizzare un percorso specifico acquisito dall'utente nel contesto della variabile visualizzata. Se richiesto, un rappresentante Adobe può abilitare i percorsi. Le evar non possono utilizzare i percorsi.
* **Metriche potenzialmente disponibili**: Le metriche disponibili tra prop e evar variano in base alle impostazioni della variabile e alla piattaforma dati/versione. L'elenco seguente illustra cosa può essere abilitato, non quanto è abilitato per impostazione predefinita. Se desideri una metrica specifica nel reporting ma non la trovi, chiedi a uno degli utenti supportati della tua organizzazione di contattare l'Assistenza clienti.

<table id="table_FB963F60857A4AD79562324FB6F4B6A9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Metrica </p> </th> 
   <th colname="col2" class="entry"> <p>Proprietà </p> <p>(Variabili di traffico) </p> </th> 
   <th colname="col3" class="entry"> <p>Evar </p> <p>(Variabili di conversione) </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Profondità pagina media </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_165C1BF1574247CEA9190ADCABF79D69" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo medio trascorso </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_9F0F396E11B442959EC3E5D4D508496D" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bounce Rate </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_A268EAF747EA45F8A6A93A1B66667A06" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_09D486144CEA4293A505DCA3F90B82EC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Non recapitate </p> </td> 
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
   <td colname="col1"> <p>Ingressi </p> </td> 
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
   <td colname="col1"> <p>Metriche acquisto </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8F8AB7CD02764245BA73CA1E6B69BAE1" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ricarica </p> </td> 
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
   <td colname="col1"> <p>Visitatori univoci </p> </td> 
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

* **Suddivisioni**: I prop utilizzano correlazioni, che visualizzano visualizzazioni di pagina per altre variabili di traffico attivate nella stessa richiesta di immagine. Le evar utilizzano le sottorelazioni, che forniscono una suddivisione su altre variabili di conversione in relazione agli eventi di successo.

## Exclusive advantages to Props or eVars {#section_B384031AB8674065BA5187B0A3A3DAB9}

Con la versione 15, le funzionalità tra Prop e evar sono molto meno distinte. Le evar sono state aggiornate di recente per includere funzionalità quali visite/visitatori unici con carico minimo di elaborazione, nonché metriche di percorsi.

I prop contengono un paio di vantaggi per evar, alcuni dei quali possono essere aggirati:

* I dati prop vengono raccolti e disponibili in modo quasi immediato. Le evar possono richiedere oltre 30 minuti per essere visualizzate nei dati della suite di rapporti.
* Tutti i prop possono avere rapporti con diagramma di flusso abilitati, che permettono di vedere il percorso che i visitatori intraprendono al tuo sito. These pathing flow reports are available for both Props and eVars in [!UICONTROL Ad Hoc Analysis].
* I prop possono essere più livelli correlati, dove evar può essere sottocorrelato solo una volta. Questa limitazione può essere mitigata utilizzando la segmentazione, fornendo dati identici come correlazioni.
* Le metriche di partecipazione consentono di vedere quali valori prop hanno partecipato prima di un evento di successo.

Le evar, invece, hanno diversi vantaggi rispetto alla natura limitata dei prop:

* Le evar possono utilizzare eventi di successo come metriche. I prop non possono.
* La scadenza evar può essere personalizzata, inclusa la scadenza di ogni hit (nessun valore persistente). I prop non persistono in alcun modo.

Le metriche di percorsi, come il Tempo totale trascorso, le Voci e le Uscite, originariamente non erano disponibili per le evar. Tuttavia, gli aggiornamenti recenti hanno reso disponibili queste metriche, aumentando il valore delle evar.

## Which to Use {#section_022D016A4EEB45179A15BFF044A261A4}

**Prop:** Se la latenza è la preoccupazione più importante e intendi misurare solo il traffico (non eventi di successo) con questa dimensione.

**Evar:** Se le suddivisioni e le relazioni di dati sono i principali problemi.

>[!TIP]
>
>Se non vuoi mantenere un evar, puoi modificarne la scadenza in «hit» in modo che non contenga dati oltre l'hit.

