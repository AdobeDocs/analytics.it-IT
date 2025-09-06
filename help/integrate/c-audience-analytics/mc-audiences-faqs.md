---
description: Risposte alle domande che potresti avere durante l’implementazione di Audience Analytics.
solution: Experience Cloud
title: Domande frequenti per Audience Analytics
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 4%

---

# Domande frequenti

Risposte alle domande che potresti avere durante l’implementazione di Audience Analytics.

## Domande frequenti legali {#legal}

+++ Come posso sapere se i miei dati di Analytics contengono dati personali (PII, Personally Identifiable Information)? E se sì, cosa posso fare?

Se hai e-mail, indirizzi e così via in una prop o eVar, puoi usare l’hashing dei dati durante la raccolta. Se il tuo paese considera l&#39;indirizzo IP come PII, [attiva l&#39;offuscamento dell&#39;IP](/help/admin/tools/exclude-ip.md). Parla con il tuo amministratore di Analytics per vedere cosa stai raccogliendo. Parla con l&#39;Ufficio legale per capire quali sono le informazioni di cui si occupano.

+++

+++ Come posso sapere se le mie suite di rapporti eseguono la personalizzazione nel sito o il targeting offsite/nel sito?

Queste non si applicano all’invio di dati di Adobe Analytics a Adobe Audience Manager. Chiediti:

* Condividerai un segmento condiviso con Analytics con una dimensione MCA di nuovo in Experience Cloud?

* Stai esportando (ad esempio tramite feed di dati) in un sistema di Business Intelligence (BI) usato a tale fine?

+++

## Domande frequenti specifiche per Adobe Audience Manager {#aam-specific}

+++ Come si crea una destinazione Analytics in Audience Manager?

Vedere [Configurare una destinazione Analytics in Adobe Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=it)&quot;.

+++

+++ Dopo aver creato e salvato una destinazione Analytics, quanto tempo ci vuole affinché i dati vengano visualizzati nelle suite di rapporti selezionate?

Possono essere necessarie diverse ore per popolare le suite di rapporti con nuovi dati.

+++

+++ Ho creato una nuova destinazione Analytics, ma non la vedo nella sezione Mappature di destinazione dei miei segmenti disponibili. Dove è andata la destinazione o come la trovo?

Una destinazione Analytics scompare dalla sezione Mappature di destinazione di un segmento quando si seleziona l&#39;opzione **[!UICONTROL Automatically map all current and future segments]** in **[!UICONTROL Segment Mappings]**. Per evitare questo problema, selezionare **[!UICONTROL Manually map segments]** invece dell&#39;opzione automatica.

+++

Questo mi darà tutte le informazioni da Adobe Audience Manager, in Analytics?

No, solo i dati relativi alle persone che arrivano sul tuo sito durante o dopo l’abilitazione di Audience Manager Audiences e durante/dopo la qualificazione dei segmenti.

+++

+++ Questo mi darà un pubblico indirizzabile totale per segmento?

Non esattamente. Ti dirà il numero di visitatori in quel segmento che sono arrivati al tuo sito durante o dopo la qualifica del segmento.

+++

+++ Quali sono le differenze tra questa destinazione di cookie legacy e Analytics?

I segmenti vengono qualificati e restituiti in tempo reale - sullo stesso hit. I nomi descrittivi vengono visualizzati automaticamente.

+++

+++ Cosa succede se alcune delle mie suite di rapporti contengono dati personali e altre no?&lt;

Suggerimento: crea due destinazioni: aggiungi le suite di rapporti sui dati personali a una destinazione e le suite di rapporti sui dati non personali all’altra.

+++

## Domande frequenti specifiche per Analytics {#aa-specific}

+++ Questa integrazione emergerà come dimensione o segmento in Analytics?

Come dimensioni: ID e nome del pubblico.

+++

+++Dove posso utilizzare queste dimensioni in Analytics?

Ovunque; vengono trattati come qualsiasi altra dimensione raccolta in Analytics.

+++

+++ Perché non vedo i dati provenienti da Analytics?

È probabile che siano presenti controlli sulla privacy di Adobe Audience Manager in conflitto tra origine dati e destinazione.

+++

+++ Perché mancano alcuni dei miei segmenti in Analytics, anche se ho scelto di inviare tutti i segmenti?&lt;

* I controlli di esportazione dei dati Adobe Audience Manager sulla destinazione e nelle origini dati dei segmenti potrebbero essere in conflitto, impedendo l’invio di alcuni segmenti.

* Se utilizzi caratteristiche di dati di terze parti nei segmenti, tali segmenti non possono essere condivisi con destinazioni (un set di suite di rapporti) che contengono dati personali.

+++

+++ Perché vedo &quot;Limite di pubblico raggiunto&quot; nel mio rapporto Analytics? (Nota: verrà rappresentato anche come ID pubblico = -1 e `::max_audiences_exceeded::` in Data Warehouse)

Per impostazione predefinita, l’integrazione di Audience Analytics per Adobe Audience Manager invia ad Analytics tutti i segmenti per i quali un visitatore si qualifica, in base all’hit. Se un visitatore appartiene a più di 150 segmenti Adobe Audience Manager in un singolo hit, gli ultimi **150 segmenti qualificati** vengono inviati ad Analytics, mentre l&#39;elenco rimanente viene troncato. Ad Analytics viene inviato un flag aggiuntivo che indica che l’elenco dei segmenti è stato troncato e viene visualizzato come &quot;Limite di pubblico raggiunto&quot; nella dimensione Nome pubblico e &quot;-1&quot; nella dimensione ID pubblico.

Anche se è improbabile che un visitatore sia idoneo per più di 150 segmenti su un particolare hit, ciò può accadere per una piccola percentuale di tempo. Se nei rapporti si verifica il &quot;Limite di pubblico raggiunto&quot;, sono disponibili due opzioni:

* Opzione 1: continua a lasciare che l’integrazione funzioni nel suo stato predefinito, inviando gli ultimi 150 segmenti qualificati per un visitatore specifico.

* Opzione 2: in Adobe Audience Manager, scegli i 150 segmenti più importanti per la tua azienda per l’integrazione. Adobe Audience Manager quindi controlla i visitatori solo rispetto a tali 150 segmenti. Lo svantaggio di questo approccio è che ricevi solo quei 150 segmenti su tutti i visitatori. D’altro canto, l’approccio dell’opzione 1 può offrire segmenti illimitati a causa della natura specifica dell’integrazione.

+++

+++ Per questa integrazione verranno fatturate altre chiamate server ad Analytics?

No. I tipi di pubblico di Adobe Audience Manager sono incorporati nell’hit Analytics lato server. Questo non comporta chiamate server aggiuntive ad Analytics (primaria o secondaria).

+++

## Domande frequenti sull&#39;inoltro lato server (SSF) {#SSF}

+++ Se hai implementato un SSF legacy, devo andare anche dall’amministratore di Analytics e attivare l’SSF della suite di rapporti?

Sì. Nella configurazione della destinazione Adobe Audience Manager, verranno visualizzate solo le suite di rapporti con SSF attivato.

+++

+++ Perché non posso attivare alcune suite di rapporti per SSF in Analytics Admin?

È possibile abilitare solo le suite mappate sull’organizzazione Experience Cloud.

Per ulteriori domande frequenti su questo argomento, vedi [Domande frequenti sull&#39;inoltro lato server](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md).

+++

## Domande frequenti generiche {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ Perché i conteggi dei visitatori dei segmenti sono diversi tra Audience Manager e Analytics?

Vedi [Differenze nel numero di visitatori](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md).

+++

+++ Qual è la differenza tra &quot;tipi di pubblico&quot; in Adobe Audience Manager e &quot;segmenti&quot; in Analytics?

Consulta [Informazioni sui segmenti in Analytics e Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md). I tipi di pubblico di Adobe Audience Manager vengono inviati e condivisi come componenti &quot;dimensionali&quot; da utilizzare in Analytics. Ad esempio, non vengono visualizzati come segmenti nel Generatore di segmenti, ma come dimensioni con cui puoi creare i segmenti.

+++

+++ Qual è la differenza tra attributi del cliente e dati del cliente integrati da Adobe Audience Manager?

Gli attributi del cliente non sono basati sul tempo, ma vengono applicati retroattivamente e proseguono. I dati integrati di Adobe Audience Manager sono basati solo sul tempo e possono essere utilizzati solo successivamente. Inoltre, attributi del cliente è una tabella di ricerca per gli ID visitatore di Experience Cloud, mentre l’integrazione di Adobe Audience Manager è costituita dai dati uniti in ogni hit di un visitatore.

+++

+++ E gli approcci legacy a questo problema, ad esempio la vecchia beta o le destinazioni dei cookie del plug-in Consulting?

È consigliabile implementare la nuova integrazione e rimuovere le destinazioni obsolete.

+++
