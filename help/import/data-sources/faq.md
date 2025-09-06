---
title: Domande frequenti sulle origini dati
description: Domande frequenti sulle origini dati.
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 7%

---

# Domande frequenti sulle origini dati

Domande frequenti sulle origini dati.

+++Qual è il costo dell&#39;utilizzo delle origini dati?
Le origini dati non comportano costi né vengono conteggiate per l’utilizzo delle chiamate al server. [Origini dati a elaborazione completa](full-processing-eol.md) conteggiate per le chiamate al server prima del loro ritiro.
+++

+++In che modo le origini dati influiscono sull’attribuzione e sulla scadenza delle eVar?
Le origini dati non hanno alcun tipo di attribuzione o scadenza.
+++

+++In che modo le origini dati influiscono su metriche quali visualizzazioni di pagina, visite o visitatori univoci?
I dati caricati tramite origini dati non influiscono in alcun modo sulle [visualizzazioni pagina](/help/components/metrics/page-views.md), [visite](/help/components/metrics/visits.md) o [visitatori univoci](/help/components/metrics/unique-visitors.md). L&#39;unica metrica predefinita interessata include [Occorrenze](/help/components/metrics/occurrences.md).
+++

+++I dati caricati tramite origini dati vengono eseguiti tramite elaborazione aggiuntiva, come le regole di elaborazione?
No. Dati caricati tramite origini dati:

* Non passa attraverso [Regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
* Non passa attraverso [Regole di elaborazione del canale di marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md)
* Non passa attraverso [regole VISTA](/help/technotes/vista.md)
+++

+++È possibile eliminare i dati importati utilizzando origini dati?
Sì. Puoi eliminare questi dati utilizzando [Data Repair API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/). Adobe consiglia vivamente di caricare i dati di origini dati in una suite di rapporti di prova prima di caricarli in una suite di rapporti di produzione per ridurre la necessità di rimuovere i dati.
+++

+++Quanti dati posso importare alla volta?
L’elaborazione viene messa in pausa se la dimensione supera i 50 MB e non riprende finché il totale non è inferiore a 50 MB. Assicurati che la dimensione totale di tutti i file sul sito FTP sia inferiore a 50 MB.
+++

+++Cosa succede se trasferisco valori negativi nel reporting tramite origini dati?
Il valore diminuisce di conseguenza. Alcune organizzazioni utilizzano valori di origine dati negativi per tentare di correggere i dati. I valori negativi dell’origine dati possono influire sui rapporti in modi potenzialmente indesiderati o imprevisti. Adobe consiglia di utilizzare valori negativi nelle origini dati solo come ultima risorsa.
+++

+++Le estensioni dei file sono sensibili all&#39;uso di maiuscole e minuscole?
Sì. I file con estensione di `.TXT` o `.FIN` non vengono elaborati. Assicurati che le estensioni dei file siano tutte in minuscolo.
+++

+++Quante colonne è possibile aggiungere a un file di origine dati?
In un file di origine dati è possibile includere tutte le colonne desiderate, purché siano tutte colonne valide. Vedere [Formato file](file-format.md) per un elenco di nomi di variabili/colonne validi.
+++

+++È possibile utilizzare le origini dati senza utilizzare il percorso FTP fornito da Adobe?
È possibile utilizzare l&#39;[API origini dati](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), che consente di inviare chiamate API direttamente ad Adobe. Queste chiamate API includono un metodo `UploadData`, che consente di inviare dati tramite un payload di oggetti JSON.
+++
