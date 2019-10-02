---
title: Configurazione di Analytics tra dispositivi
description: Learn how to set up Cross-Device Analytics after you meet the prerequisites.
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# Configurazione di Analytics tra dispositivi

> [!NOTE] Cross-Device Analytics documentation is subject to change as the feature is further developed. Check back regularly for updates.

Once all prerequisites are met, use the following steps to enable Cross-Device Analytics. You must belong to a Product Profile Admin group or have admin privileges in Adobe Analytics to follow these steps.

> [!IMPORTANT] All prerequisites must be met before following these steps. If all prerequisites are not met, the feature is not available or will not work. See Cross-Device Analytics for prerequisites and limitations.[](cda-home.md)

## Choose the cross-device report suite that will be enabled for CDA

When your organization is provisioned to use CDA, you choose which report suite to use. This choice can be communicated through your Adobe Account Manager. Adobe quindi abilita la suite di rapporti selezionata per l'elaborazione CDA.

## Creare una suite di rapporti virtuali per dispositivi diversi per visualizzare la visualizzazione su più dispositivi

Gli amministratori con accesso per creare suite di rapporti virtuali possono creare suite di rapporti virtuali CDA come segue:

1. Andate a [experience.adobe.com](https://experiencecloud.adobe.com) ed effettuate l'accesso utilizzando le credenziali AdobeID.
2. Click the 9-grid icon at the top, then click Analytics.
3. Passa il cursore del mouse sui componenti in alto, quindi fai clic su Suite di rapporti virtuale.
4. Fai clic su Aggiungi.
5. Immettete un nome per la suite di rapporti virtuali e accertatevi che sia selezionata la suite di rapporti abilitata per CDA.
6. Fate clic sulla casella di controllo "Abilita elaborazione tempo rapporto" per abilitare diverse opzioni, tra cui Analisi multi-dispositivo.
7. Fate clic sulla casella di controllo "Stitch User Visits Between Devices" (Stitch Visite utente tra dispositivi).
8. Fate clic su Continue (Continua), completate la configurazione della suite di rapporti virtuali, quindi fate clic su Save (Salva).

![Casella di controllo CDA](assets/cda-checkbox.png)

## Aggiunte e modifiche alle suite di rapporti virtuali su più dispositivi

Quando Analytics cross-device è abilitato su una suite di rapporti virtuale, prendi nota delle seguenti modifiche:

* Accanto al nome della suite di rapporti virtuale viene visualizzata una nuova icona cross-device. Questa icona è esclusiva per le suite di rapporti virtuali su più dispositivi.
* Sono disponibili nuove metriche con etichetta 'Persone' e 'Dispositivi univoci'.
* La metrica "Visitatori unici" non è disponibile, in quanto viene sostituita con Persone e Dispositivi univoci.
* Durante la creazione di segmenti, il contenitore del segmento "Visitatore" viene sostituito con un contenitore "Persona".

## Metrica calcolata di compressione

La capacità di analisi multi-dispositivo di unire più dispositivi dipende da un'ampia gamma di fattori. L'efficacia della capacità della funzione di cucire i dati può essere misurata con una metrica calcolata denominata compressione. I fattori che contribuiscono alla compressione comprendono:

* Usando il grafico Co-op o il grafico Privato: In generale, le organizzazioni che utilizzano la cooperativa dispositivi tendono a visualizzare tassi di compressione migliori rispetto alle organizzazioni che utilizzano il grafico privato.
* Velocità di accesso: Più utenti accedono al sito, più Adobe è in grado di identificare e unire i visitatori tra i dispositivi. Anche i siti con un basso tasso di accesso hanno bassi tassi di compressione.
* Copertura Experience Cloud ID: È possibile unire solo i visitatori con un ECID. Una percentuale inferiore di visitatori del sito che utilizza un ECID è correlata a tassi di compressione più bassi.
* Utilizzo di più dispositivi: Se i visitatori del sito non utilizzano più dispositivi, è possibile visualizzare percentuali di compressione inferiori.
* Granularità del reporting: La compressione per giorno è generalmente inferiore alla compressione per mese o anno. Le possibilità di un singolo di utilizzare più dispositivi diventano più ridotte entro un singolo giorno rispetto a un intero mese. Segmentazione, filtraggio o utilizzo di dimensioni di suddivisione può anche mostrare una minore frequenza di compressione.

To see your organization's compression for a given time period:

1. Click Workspace at the top, then click 'Create New Project'.
2. Start with a Blank Project, then click Create.
3. Drag the Unique Devices metric onto the canvas area labeled 'Drop a Metric Here'.
4. Drag the People metric onto the canvas directly to the right of the Unique Devices metric header, so the two metrics are side-by-side.
5. Click the '' symbol next to available metrics on the left to open the Calculated Metric builder.`+`
6. Give this calculated metric the following settings:
   * Name: Cross-Device Compression
   * Format: Percent
   * Decimal Places: 2
   * Definizione: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] Click 'Add' in the top right corner of the definition area to add a static number. Drag People and Unique Devices from the list of available metrics on the left.
7. Fate clic su Salva.
8. Drag the new calculated metric onto the canvas directly to the right of the People metric header, so all three metrics are side-by-side.
9. Optional: The workspace loads the Day dimension by default. Trascina una dimensione data alternativa, ad esempio una settimana o un mese, sopra la dimensione Giorno, se desideri una granularità ora diversa.
