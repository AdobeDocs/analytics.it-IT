---
description: 'null'
title: Domande frequenti su Project Converter
uuid: 8e1bf0e9-ce0f-443a-bcfe-45d3e2c82b1c
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 95%

---


# Domande frequenti su Project Converter

>[!IMPORTANT]
>
> Adobe sta spostando  Ad Hoc Analysis a fine ciclo di vita il 1 marzo 2021. [Ulteriori informazioni...](https://adobe.ly/discoverworkspace).

## Domande frequenti su Project Converter {#topic_8231595303AD403E9322645A63632D57}

* [Problemi di conversione noti](/help/analyze/ad-hoc-analysis/c-aha-project-converter/aha2aw-converter-faq.md#section_39C922A58B2E49C9877B363042801361)
* [Domande frequenti sulla conversione](/help/analyze/ad-hoc-analysis/c-aha-project-converter/aha2aw-converter-faq.md#section_1E53FE373AF045978F939916124E194E)

## Problemi di conversione noti {#section_39C922A58B2E49C9877B363042801361}

| Problema | Descrizione |
|--- |--- |
| Granularità al minuto con suddivisioni o in colonne | Se alla granularità al minuto è applicata una suddivisione o se la granularità dei minuti è presente in colonne, il progetto non può essere convertito in Analysis Workspace.  Una soluzione consiste nel rimuovere la suddivisione dalla granularità al minuto e rimuoverla dalle colonne, quindi convertire il progetto. Puoi quindi applicare le suddivisioni alla granularità al minuto in Analysis Workspace. |
| Metrica interna calcolata utilizzata insieme a un segmento di colonna | Se utilizzi una metrica interna calcolata insieme a un segmento di colonna, il progetto non può essere convertito in Analysis Workspace. Per risolvere questo problema, rimuovi le metriche interne calcolate dal progetto prima della conversione, quindi aggiungile di nuovo in Analysis Workspace. |


## Domande frequenti sulla conversione {#section_1E53FE373AF045978F939916124E194E}

<table id="table_48CC119236C94835A6A512E989BE4200"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>D: Esistono funzioni di Ad Hoc Analysis non supportate in Analysis Workspace?</b> </p> </td> 
   <td colname="col2"> <p>R: Il report di analisi del sito non è supportato in Analysis Workspace. In Ad Hoc Analysis e Workspace sono presenti anche alcune lievi differenze tra le altre visualizzazioni. Per maggiori informazioni, consulta le domande riportate di seguito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Come vengono convertite le impostazioni della tabella?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_A645A004FB094A1593439A6607FE9A6B"> 
     <li id="li_033CA771F08A4BC3B0BC52CDCCA03FF4"><b>Numero di righe visualizzate</b>: in Workspace vengono mostrate solo 10 righe (personalizzabile per visualizzare fino a 400 righe alla volta), mentre in Ad Hoc vengono visualizzate fino a 50.000 righe in una pagina. I dati si trovano comunque in Workspace ma sono impaginati in 10 righe per impostazione predefinita. </li> 
     <li id="li_A8B8890149334032A56D8D1C0F8691EA"><b>Ricerca avanzata:</b> non sono supportate più opzioni di ricerca simultanea, ma un’unica opzione di ricerca (come <span class="wintitle">Tutte le parole seguenti</span>, <span class="wintitle">La frase esatta</span>, <span class="wintitle">Qualsiasi parola tra le seguenti</span> o <span class="wintitle">Nessuna tra le parole seguenti</span>) sarà convertita in Analysis Workspace. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Come vengono convertiti i grafici?</b> </p> </td> 
   <td colname="col2"> <p>R: I grafici e i grafici sono denominati “visualizzazioni” in Workspace. </p> 
    <ul id="ul_597F5AB826EF434295D0CABD0313CAD5"> 
     <li id="li_AFB2805418034721A9519D999128C0A8"><b>Impostazioni</b>: Le impostazioni di visualizzazione come “Numero di elementi” o “Numero di barre” non sono supportate in Workspace. </li> 
     <li id="li_D5C7EA8815344EDB8585CBB8E1AF583E"><b>Grafico a torta</b>: esportato come visualizzazione ad <a href="https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/donut.html"  > Anello</a>. Questa visualizzazione in Workspace è limitata a 19 sezioni. </li> 
     <li id="li_91659FBFD77C4B3393D78447D658B7B4"><b>Grafico a bolle</b>: esportato come visualizzazione <a href="https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/scatterplot.html"  > grafico a dispersione</a>. Per impostazione predefinita, il grafico a dispersione disegna la prima metrica sull’asse x e la seconda metrica sull’asse y. Se esiste una sola metrica, i grafici a bolle saranno convertiti in visualizzazioni a linee. </li> 
     <li id="li_FA05085FFB1747EBAF63616AC2B8D59C"><b>Istogramma</b>: supporta una logica di bucket diversa in Workspace rispetto ad Ad Hoc Analysis. Pertanto, viene convertito in visualizzazione a <a href="https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/bar.html"  > barre</a>. </li> 
     <li id="li_959499D20796459CA0F6BBC8F0A8D808"><b>Dispersione</b>: nei progetti esportati in Analysis Workspace, l’asse Y è impostato come prima colonna, l’asse X come seconda colonna e il diametro come terza colonna. </li> 
     <li id="li_14E06D7A5106405A89A07B44FFD9A92D"><b>Tabelle di abbandono</b>: per visualizzare i fallthrough o le tabelle di abbandono, fai clic con il pulsante destro del mouse sul punto di controllo e seleziona un’opzione di suddivisione. </li> 
     <li id="li_240F43C386F04111A7632A8FCA37832C"><b>Intervalli di date a livello di report di abbandono</b>: gli intervalli di date dei report personalizzati non sono stati applicati alle visualizzazioni Abbandono. </li> 
     <li id="li_1FF5B3FD9E424E7190AF03FD4DD9D654"><b>Rapporto di flusso</b>: il flusso verrà spostato in un pannello separato per mantenere intervalli di dati e segmentazione. </li> 
     <li id="li_BE8F8F6EC2EA49E18EF52539BC1700E0"><b>Funnel di conversione</b>: verrà convertito in una tabella a forma libera perché non supportato in Analysis Workspace. La visualizzazione Abbandono è una sostituzione consigliata per il funnel di conversione, ma si comporta in modo leggermente diverso. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Come vengono convertiti i segmenti?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_15D5B17461E2402DB07DF8B0A10AAC37"> 
     <li id="li_CF9C3D235A664B15B21D9F89DC5EF7D3">I segmenti sono interni al progetto convertito (non pubblici). Puoi scegliere di renderli pubblici, come illustrato di seguito: <p><img placement="inline"  src="assets/internal_segment.png" id="image_5942392F18E845A5B41C3DED59374E89" width="300px" /> </p> </li> 
     <li id="li_AE61DAEC5C0047349DD192EFEEDB0BF9">I segmenti a livello di workspace di Ad Hoc Analysis vengono applicati a livello di progetto/pannello in Workspace. </li> 
     <li id="li_B1559E2C18724FE189AF87D0BEF16811">I segmenti a livello di report di Ad Hoc Analysis vengono applicati a livello di colonna di una tabella in Workspace. </li> 
     <li id="li_0E6DF6D44EA448A4A212BA2BB8E342CF">I segmenti di tabella Ad Hoc Analysis vengono applicati a livello di colonna in Workspace. </li> 
    </ul> <p>Puoi modificare i segmenti nello  strumento per la <a href="https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/seg-home.html"  >creazione dei segmenti</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Come vengono convertiti gli intervalli di date?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_A24AB597F3CE4847AF00D49A9A72A395"> 
     <li id="li_24FD18AF64114445939C4FBC03F2D406">Gli intervalli di date “Ultimo giorno X” in Ad Hoc Analysis <i>escludono</i> oggi, mentre Analysis Workspace <i>include</i> oggi. Di conseguenza, gli intervalli di date come “ultimi 90 giorni” potrebbero non corrispondere esattamente tra gli strumenti. Usa intervalli di date personalizzati per recuperare lo stesso periodo di tempo in Analysis Workspace. </li> 
     <li id="li_AA4390470C494748B4B12030B1226720">L’intervallo di date a livello di workspace di Ad Hoc Analysis vengono applicati a livello di progetto/pannello in Workspace. </li> 
     <li id="li_B8F0CDD413154856A315D087FEC4D418">L’intervallo di date a livello di report di Ad Hoc Analysis viene applicato a livello di colonna di una tabella in Workspace. </li> 
    </ul> <p>Puoi modificare i tuoi intervalli di date personalizzati in <span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> Componenti</span> &gt; <span class="uicontrol"> Intervalli di date</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Come vengono convertite le metriche calcolate?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_ADA380D5D09B4223AAE4853D4C64F679"> 
     <li id="li_010572F793F54680ABE64117DAB7E800">Le metriche calcolate sono interne al progetto esportato (non pubbliche). Puoi scegliere di renderle pubbliche facendo clic con il pulsante destro del mouse sulla metrica e scegliendo <span class="uicontrol"> Rendi pubbliche</span>. <p><img placement="inline"  src="assets/calc_metric_internal.png" id="image_EA19BA55B161499CBDB9275A5C94BA90" width="200px" /> </p> </li> 
     <li id="li_930546EC8FEB432C8810FAF93556FC9A">Tutti i tipi di metriche calcolate sono supportati per l’esportazione. </li> 
     <li id="li_DFF7C6F8BB2344928D49194DA0F6EC38"><b>Tipi di allocazione</b>: anche se Analysis Workspace non mostra esplicitamente il tipo di allocazione di una metrica calcolata, l’esportazione crea e corrisponde al tipo di allocazione presente in Ad Hoc Analysis. </li> 
    </ul> <p>Puoi modificare il tipo di allocazione nel <a href="https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/cm-overview.html"  >Generatore di metriche calcolate</a> facendo clic sull’icona di modifica (matita). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: In che modo le impostazioni globali dati in Ad Hoc vengono applicate ai progetti convertiti?</b> </p> </td> 
   <td colname="col2"> <p>Le impostazioni globali dati potrebbero comportare un funzionamento diverso dello stesso progetto esportato due volte: </p> 
    <ul id="ul_E3827883DD8045FAAB359D7E85E3EEFA"> 
     <li id="li_1056CA4813C44638BEB070228AE6914C"><b>Conta istanze ripetute.</b> Qualsiasi impostazione applicata al momento dell’esportazione viene applicata al progetto esportato in Analysis Workspace. </li> 
     <li id="li_D5405E2862CF434CA82AA9DE000F4BBC"><b>Origini dati.</b> In Analysis Workspace, vengono visualizzati tutti i dati di Analytics, comprese le origini dati. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Se il mio progetto Ad Hoc Analysis è programmato, la pianificazione verrà convertita in Analysis Workspace?</b> </p> </td> 
   <td colname="col2"> <p>No, le pianificazioni non vengono convertite. In Analysis Workspace, apri il progetto da programmare e vai a <span class="uicontrol"> Condividi</span> &gt; <span class="uicontrol"> Invia file secondo programma</span> per impostare una nuova pianificazione. Assicurati di annullare il progetto pianificato in Ad Hoc Analysis. </p> </td> 
  </tr> 
 </tbody> 
</table>

