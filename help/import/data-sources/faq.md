---
title: Domande frequenti sulle origini dati
description: Domande frequenti sulle origini dati.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 7%

---

# Domande frequenti sulle origini dati

Domande frequenti sulle origini dati.

+++Qual è il costo per l&#39;utilizzo delle origini dati?
Le origini dati non generano alcun costo, né contano per l’utilizzo delle chiamate al server. [Origini dati di elaborazione completa](full-processing-eol.md) conteggiati per le chiamate server prima del loro pensionamento.
+++

+++In che modo le origini dati influiscono sull’attribuzione e sulla scadenza per le eVar?
Se un ID transazione corrisponde tra un’origine dati e un hit online, i valori eVar associati si basano sulla stessa attribuzione e scadenza come se fossero impostati sull’hit online.

Tutti gli altri dati caricati tramite origini dati non hanno alcun tipo di attribuzione o scadenza.
+++

+++In che modo le origini dati influiscono sulle metriche predefinite, ad esempio visualizzazioni di pagina, visite o visitatori univoci?
I dati caricati tramite origini dati non hanno alcun impatto [Visualizzazioni pagina](/help/components/metrics/page-views.md), [Visite](/help/components/metrics/visits.md)oppure [Visitatori unici](/help/components/metrics/unique-visitors.md) in qualsiasi modo. L’unica metrica predefinita che interessa include [Occorrenze](/help/components/metrics/occurrences.md).
+++

+++Posso eliminare i dati importati utilizzando origini dati?

**No.** I dati caricati nei rapporti utilizzando origini dati sono **permanente**. Non può essere rimosso, neanche per Adobe, una volta importato. Adobe consiglia vivamente di caricare i dati delle origini dati in una suite di rapporti di prova prima di caricarli in una suite di rapporti di produzione.
+++

+++Quanti dati posso importare alla volta?

L’elaborazione viene messa in pausa se la dimensione supera i 50 MB e non riprende finché il totale non è inferiore a 50 MB. Assicurati che la dimensione totale di tutti i file sul sito FTP sia inferiore a 50 MB.
+++

+++Cosa succede se trasferisco valori negativi nel reporting tramite origini dati?

Il valore diminuisce di conseguenza. Alcune organizzazioni utilizzano valori di origine dati negativi per tentare di correggere i dati. I valori negativi delle origini dati possono influenzare i rapporti in modi potenzialmente indesiderati o imprevisti. L&#39;Adobe consiglia di utilizzare origini dati negative solo come ultima risorsa.
+++

+++Sono sensibili all’uso di maiuscole e minuscole nelle estensioni dei file?
Sì. File con estensione `.TXT` o `.FIN` non vengono elaborati. Assicurati che le estensioni dei file siano tutte minuscole.
+++

+++Quante colonne posso aggiungere a un file di origine dati?
È possibile includere tutte le colonne desiderate in un file di origine dati, se sono tutte colonne valide. Vedi [Formato file](file-format.md) per un elenco di nomi di variabili/colonne validi.
+++

+++Posso utilizzare le origini dati senza utilizzare la posizione FTP fornita da Adobe?
È possibile utilizzare [API origini dati](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), che consente di inviare chiamate API direttamente ad Adobe. Queste chiamate API includono `UploadData` , che ti consente di inviare dati tramite un payload di oggetti JSON.
+++
