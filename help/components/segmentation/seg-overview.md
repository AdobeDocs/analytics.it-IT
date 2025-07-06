---
description: Scopri come i segmenti ti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni con siti web.
title: Informazioni sui segmenti
feature: Segmentation
exl-id: 11d930ca-5d59-4ea5-b6e5-fe3d57be94fd
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '972'
ht-degree: 73%

---

# Informazioni sui segmenti

I segmenti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni con siti web. I segmenti sono progettati come insight sul pubblico che puoi creare per esigenze specifiche e successivamente puoi verificarli, modificarli e condividerli con altri membri del team o utilizzarli in altri prodotti Adobe e in altre funzionalità di Analytics.

I segmenti si basano su una gerarchia a livello di [!UICONTROL Visitor], [!UICONTROL Visit] e [!UICONTROL Hit] che utilizza un modello di contenitori nidificati. I contenitori nidificati ti consentono di definire gli attributi e le azioni dei visitatori in base alle regole tra e all’interno dei contenitori. I segmenti di Analytics possono essere generati, approvati, condivisi, salvati ed eseguiti tra più prodotti e funzionalità in [!DNL Adobe Experience Cloud]. I segmenti possono essere generati da un rapporto, incorporati in un rapporto dashboard o contrassegnati con segnalibro per l’accesso rapido.

È possibile generare e salvare i segmenti nel Generatore di segmenti o generarli da un rapporto di fallout (in [!UICONTROL Analysis Workspace]). Puoi anche utilizzare ed estendere segmenti predefiniti basati su regole specifiche tra contenitori nidificati, per filtrare i risultati e applicarli ai rapporti. Inoltre, i segmenti possono essere utilizzati insieme come [segmenti sovrapposti](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

Identificazione dei segmenti

- chi sono i visitatori (paese, genere, caffetteria),
- quali dispositivi e servizi utilizzano (browser, motore di ricerca, dispositivo mobile),
- luogo di navigazione (motore di ricerca, pagina di uscita precedente, ricerca naturale),
- e molto di più.

<!--![](assets/seg.png)-->

I segmenti possono essere basati sui seguenti valori:

- Visitatori in base agli attributi: tipo di browser, dispositivo, numero di visite, paese, genere.
- Visitatori in base alle interazioni: campagne, ricerca di parole chiave, motore di ricerca.
- Visitatori in base a uscite ed entrate: visitatori da Facebook, da una pagina di destinazione definita, da un dominio di riferimento.
- Visitatori in base a variabili personalizzate: campo modulo, categorie definite, ID cliente.

Durante la creazione di segmenti di pubblico nel Generatore di segmenti, puoi definire le condizioni utilizzando gli operatori [!UICONTROL AND] e [!UICONTROL OR] tra i contenitori.

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Visitatori</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visite</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Hit</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">E</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visite</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Hit</td>
</tr>
</table>

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Visitatori</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visite</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Hit</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">O</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visite</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Hit</td>
</tr>
</table>

<!--![](assets/standard_segment_containers.png)-->

Questo tipo di segmento filtra i set di dati in base alle caratteristiche unite utilizzando gli operatori [!UICONTROL AND] e [!UICONTROL OR].

- Puoi [applicare più segmenti a un rapporto o a un progetto](/help/components/segmentation/segmentation-workflow/t-seg-apply.md).
- I segmenti sono universali per tutte le suite di rapporti.
- Il [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md) semplifica la creazione dei segmenti.
- Il [Gestore segmenti](/help/components/segmentation/segmentation-workflow/seg-manage.md) ti consente di impostare [flussi di lavoro](/help/components/segmentation/segmentation-workflow/seg-workflow.md) con funzioni di condivisione dei segmenti, assegnazione di tag, verifica e approvazione.
- Puoi [assegnare tag ai segmenti](/help/components/segmentation/segmentation-workflow/seg-tag.md) per organizzarli ed effettuare ricerche in un secondo momento, anziché utilizzare le cartelle.
- Puoi creare [segmenti sequenziali](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).
- Il contenitore [!UICONTROL Page View] è stato rinominato contenitore [!UICONTROL Hit] per indicare che segmenta tutti i tipi di dati e non solo le visualizzazioni di pagina. Ad esempio, le chiamate di tracciamento dei collegamenti e le chiamate di tracciamento delle azioni dagli SDK per dispositivi mobili sono tutte incluse o escluse dal contenitore Hit.

## Segmentazione in Analysis Workspace:

Analysis Workspace contiene le seguenti funzioni aggiuntive:

- Puoi [confrontare i segmenti](../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md).
- Utilizza i segmenti come dimensioni nelle visualizzazioni a forma libera delle tabelle.
- Utilizzare i segmenti nell’[analisi dell’abbandono](../../analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md).

## Segmenti forniti da Adobe

La barra a sinistra del componente mostra i segmenti creati da te stesso e dalla tua azienda e i segmenti Adobe forniti come predefiniti. Quando si fa clic su **[!UICONTROL Show all]**, in genere questi segmenti vengono visualizzati nella parte inferiore dell&#39;elenco e sono identificati da ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg).

## Segmenti sequenziali {#sequential}

I segmenti sequenziali ti consentono di identificare i visitatori in base alla navigazione e alla visualizzazione di pagine nel sito, fornendo un segmento di azioni e interazioni definite. I segmenti sequenziali ti consentono di identificare cosa piace a un visitatore e cosa evita. Quando si creano segmenti sequenziali, l’operatore [!UICONTROL THEN] viene utilizzato per definire e ordinare la navigazione dei visitatori.

| Visita uno | Visita due | Visita tre |
|---|---|---|
| Durante la prima visita, il visitatore è passato alla pagina di destinazione principale A, ha escluso la pagina della campagna B e ha visualizzato la pagina di prodotto C. | Durante la seconda visita, ancora una volta il visitatore è passato alla pagina di destinazione principale A, ha escluso la pagina della campagna B ed è passato alla pagina di prodotto C, quindi è passato alla nuova pagina D. | Durante la terza visita, il visitatore è entrato e ha seguito lo stesso percorso della prima e della seconda visita, quindi ha escluso la pagina F per passare direttamente a una pagina di prodotto target G. |

I segmenti sequenziali possono essere basati sui seguenti valori hit:

- Visitatori in base alla sequenza di hit della pagina: visualizzazioni pagina all’interno di una singola visita, visualizzazioni pagina in visite separate, visite in cui sono state escluse visualizzazioni pagina.
- Visitatori in base al tempo tra e dopo le visualizzazioni pagina: dopo un limite di tempo, tra gli hit, dopo un evento.

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Visitatori</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visite</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Hit</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">POI</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visite</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Hit</td>
</tr>
</table>

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Visitatori</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visite</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Hit</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td style="background-color: #D3D3D3;"></td><td>E</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Hit</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">POI</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visite</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Hit</td>

<tr>
<td style="background-color: #E5E4E2;"></td><td style="background-color: #D3D3D3;"></td><td>O</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Hit</td>
</tr>
</tr>
</table>

<!--![](assets/sequential_segmentation_containers_view.png)-->

Un segmento sequenziale filtra i set di dati in base alle azioni degli utenti che utilizzano l’operatore [!UICONTROL THEN].

## Video sulla segmentazione {#segment-video}

Questo video offre una breve panoramica sui contenitori di segmenti e su come utilizzarli.


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Contenitori di segmenti](https://video.tv.adobe.com/v/25401?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


## Autorizzazioni {#permissions}

+++ **Quali diritti e privilegi servono per utilizzare, creare e gestire i segmenti?**

Per impostazione predefinita, tutti gli utenti possono creare e modificare segmenti personali. Tuttavia, gli amministratori possono decidere chi può disporre delle [autorizzazioni per la creazione di segmenti](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=it) e possono assegnarle a gruppi specifici. Questi segmenti possono essere condivisi direttamente con qualsiasi altro utente Analytics.

Gli amministratori possono modificare qualsiasi segmento e condividere i segmenti con i gruppi e con tutti gli altri utenti dell’organizzazione. [Diritti del segmento per ruolo](/help/components/segmentation/seg-reference/seg-rights.md)

+++

+++ **Posso visualizzare tutti i segmenti nella mia azienda?**

Sì, gli amministratori possono visualizzare tutti i segmenti all’interno dell’interfaccia utente di [!DNL Analysis Workspace].

Report Builder mostra i segmenti di tua proprietà e quelli condivisi con te.

+++

+++ **Posso gestire tutti i segmenti di Analytics nel Gestore segmenti?**

Sì, tutti i segmenti possono essere gestiti nel Gestore segmenti. Il Gestore segmenti mostra i segmenti visibili al proprietario (l’utente che ha creato il segmento), agli utenti condivisi e agli utenti amministratori. Il selettore dei segmenti mostra i segmenti di proprietà dell’utente e quelli condivisi con l’utente.

Gli amministratori possono visualizzare tutti i segmenti all’interno dell’interfaccia utente di Analysis Workspace.

Report Builder mostra solo i segmenti generati da te o quelli che sono stati condivisi con te specificamente.

+++

+++ **Perché non posso eliminare un segmento?**

Se il segmento è stato [pubblicato in Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-workflow.md), non è possibile eliminarlo o modificarlo. Tuttavia, puoi copiare il segmento e modificare la versione copiata.

+++
