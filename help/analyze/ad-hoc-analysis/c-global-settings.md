---
description: Configurare le impostazioni comportamentali globali. Ad esempio, è possibile configurare le impostazioni Salvataggio automatico, Grafico e tabella e specificare il font e le impostazioni internazionali.
seo-description: Configurare le impostazioni comportamentali globali. Ad esempio, è possibile configurare le impostazioni Salvataggio automatico, Grafico e tabella e specificare il font e le impostazioni internazionali.
seo-title: Impostazioni
title: Impostazioni
uuid: 34444052-479 b -4923-b 379-a 03 ca 614 bf 3 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Impostazioni

Configurare le impostazioni comportamentali globali. Ad esempio, è possibile configurare le impostazioni Salvataggio automatico, Grafico e tabella e specificare il font e le impostazioni internazionali.

## Impostazioni {#concept_D21E3D6F13EA4F97913F60C243B72173}

Configurare le impostazioni comportamentali globali. Ad esempio, è possibile configurare le impostazioni Salvataggio automatico, Grafico e tabella e specificare il font e le impostazioni internazionali.

Click **[!UICONTROL Tools]** &gt; **[!UICONTROL Settings]** to access [!UICONTROL Global Settings].

## General Settings Tab - Definitions {#reference_EADAF83466994F89BCC6B0F49A9A53DB}

Configurare le impostazioni comportamentali per le origini dati, il salvataggio del progetto, i grafici e le tabelle.

<!-- 

r_dsc_general_settings.xml

 -->

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Impostazioni dati </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Conta istanze ripetute</span>: Specifica se le istanze vengono conteggiate nei rapporti. Pertanto, se si hanno più valori sequenziali per la stessa variabile, è possibile conteggiarli come una o più istanze della variabile. </p> <p>Ad esempio, potrebbe venire visualizzato il ricaricamento della pagina, che rappresenta il numero di volte in cui le pagine del sito Web vengono ricaricate o aggiornate durante una singola visita. Questa opzione consente di specificare se più hit sulla stessa pagina sono conteggiati come uno o come visualizzazioni di pagina multiple. </p> <p> <span class="uicontrol"><span class="keyword"> Ad Hoc</span></span>: Specifica <span class="keyword"> Ad Hoc</span> come unica origine di dati per i rapporti. Questi dati provengono da richieste di immagini generate da pagine Web. </p> <p> <span class="uicontrol"><span class="keyword"> Origini</span> </span>dati: Specifica se utilizzare i dati caricati da altre sorgenti Adobe o origini dati personalizzate. This data becomes available to products in the <span class="keyword"> Experience Cloud</span>. See <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html" scope="external" format="html"> Data Sources</a> for more information. </p> <p> <span class="uicontrol"></span>Entrambi: (Impostazione predefinita) Utilizza dati provenienti <span class="keyword"> da analisi</span> ad hoc e altre origini dati. </p> <p>Note: Changing these options can result in reporting discrepancies between <span class="keyword"> ad hoc analysis</span> data and the <span class="keyword"> marketing reports and analytics data.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Impostazioni salvataggio automatico </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Salvataggio automatico attivato</span>: Abilita la funzionalità di salvataggio automatico. </p> <p> <span class="uicontrol"> Salva automaticamente frequenza progetto</span>: Consente di regolare gli incrementi temporali della funzione di salvataggio automatico. Il salvataggio automatico del progetto viene creato solo in caso di arresto anomalo ad hoc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Impostazioni grafico </p> </td> 
   <td colname="col2"> <p><b>Comprimi i grafici per impostazione predefinita</b>: Fate clic su questo pulsante per visualizzare i rapporti senza un grafico nella sezione superiore. Una volta visualizzato un rapporto con questa opzione, potete estenderlo manualmente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Impostazioni tabella </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Mostra numeri di riga</span>: Attiva o disattiva la numerazione delle righe nella tabella del rapporto. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ranked Tab - Definitions {#reference_FB9BADD7E3DA42C1BB2A02A6E9D5C1CF}

Configura il modo in cui i dati vengono visualizzati nelle colonne e seleziona le metriche predefinite per i rapporti sul traffico e sulla conversione.

<!-- 

r_dsc_ranked_tab.xml

 -->

| Campo | Definizione |
|--- |--- |
| Impostazioni colonna | Configurate la modalità di visualizzazione dei dati delle celle in tabelle e grafico a barre in grafici. |
| Seleziona metriche predefinite | Seleziona le metriche predefinite per i rapporti Traffico e Conversione, oltre alle metriche disponibili per tutti i rapporti. Includi predefinito rapporto specifico: Specifica se includere le metriche predefinite durante la personalizzazione della visualizzazione. |

## Site Analysis Tab - Definitions {#reference_9DD37C8EF718409E990E149596282FF8}

Configurare le metriche e altre impostazioni grafiche per il rapporto Analisi sito.

<!-- 

r_dsc_site_analysis_tab.xml

 -->

| Campo | Definizione |
|--- |--- |
| Metrics (Metriche) | Seleziona le metriche rappresentate dalla larghezza cilindrica e dall'altezza del cilindro. Determina quale metrica viene visualizzata utilizzando il colore e determina i colori che rappresentano valori bassi e valori elevati per quella metrica. Puoi definire le metriche per l'asse X e Y e aggiungere qualsiasi altra metrica in cui desideri visualizzare nel testo a comparsa del rapporto. Puoi anche invertire qualsiasi metrica selezionata per la visualizzazione. |
| Generale e avvisi | Abilitare e disabilitare alcuni elementi grafici del rapporto. Potete configurare gli avvisi visualizzati nel rapporto quando le metriche associate alle pagine rappresentate dai cilindri superano un valore specifico. |

## Font and Locale Tab - Definitions {#reference_5F2129B67CC44E5BA9EA7E30A35BFB49}

Specificate le impostazioni regionali per la lingua e il font predefinito. Per rendere effettive le modifiche di font e impostazioni internazionali, riavviare il riavvio.

<!-- 

r_dsc_font_locale.xml

 -->

| Campo | Definizione |
|--- |--- |
| Selezionare un'impostazione internazionale | Consente di specificare la lingua da visualizzare nell'interfaccia utente. |
| Selezionare un font | Consente di specificare un font in cui visualizzare. |