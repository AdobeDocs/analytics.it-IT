---
title: Domande frequenti sulle origini dati
description: Domande frequenti sulle origini dati.
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 7%

---

# Domande frequenti sulle origini dati

Domande frequenti sulle origini dati.

+++Qual è il costo dell&#39;utilizzo delle origini dati?
Le origini dati non comportano costi né vengono conteggiate per l’utilizzo delle chiamate al server. [Origini dati a elaborazione completa](full-processing-eol.md) conteggiato per le chiamate server prima del loro ritiro.
+++

+++In che modo le origini dati influiscono sull’attribuzione e sulla scadenza delle eVar?
Se un transactionID corrisponde tra un’origine dati e un hit online, i valori eVar associati assumono la stessa attribuzione e scadenza come se fossero impostati sull’hit online.

Tutti gli altri dati caricati tramite origini dati non hanno alcun tipo di attribuzione o scadenza.
+++

+++In che modo le origini dati influiscono sulle metriche predefinite, come visualizzazioni di pagina, visite o visitatori univoci?
I dati caricati tramite origini dati non influiscono [Visualizzazioni pagina](/help/components/metrics/page-views.md), [Visite](/help/components/metrics/visits.md), o [Visitatori univoci](/help/components/metrics/unique-visitors.md) in qualsiasi modo. L’unica metrica predefinita su cui influiscono include [Occorrenze](/help/components/metrics/occurrences.md).
+++

+++È possibile eliminare i dati importati utilizzando origini dati?

**No.** I dati caricati nei rapporti tramite origini dati sono **permanente**. Una volta importata, non può essere rimossa, neanche per Adobe. Adobe consiglia vivamente di caricare i dati di origini dati in una suite di rapporti di prova prima di caricarli in una suite di rapporti di produzione.
+++

+++Quanti dati posso importare alla volta?

L’elaborazione viene messa in pausa se la dimensione supera i 50 MB e non riprende finché il totale non è inferiore a 50 MB. Assicurati che la dimensione totale di tutti i file sul sito FTP sia inferiore a 50 MB.
+++

+++Cosa succede se trasferisco valori negativi nel reporting tramite origini dati?

Il valore diminuisce di conseguenza. Alcune organizzazioni utilizzano valori di origine dati negativi per tentare di correggere i dati. I valori negativi dell’origine dati possono influire sui rapporti in modi potenzialmente indesiderati o imprevisti. L’Adobe consiglia di utilizzare le origini dati negative solo come ultima risorsa.
+++

+++Per le estensioni dei file viene fatta distinzione tra maiuscole e minuscole?
Sì. File con estensione di `.TXT` o `.FIN` non vengono elaborati. Assicurati che le estensioni dei file siano tutte in minuscolo.
+++

+++Quante colonne è possibile aggiungere a un file di origine dati?
In un file di origine dati è possibile includere tutte le colonne desiderate, purché siano tutte colonne valide. Consulta [Formato file](file-format.md) per un elenco di nomi di variabili/colonne validi.
+++

+++È possibile utilizzare le origini dati senza utilizzare il percorso FTP fornito dall&#39;Adobe?
È possibile utilizzare [API origini dati](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), che ti consente di inviare chiamate API direttamente a Adobe. Queste chiamate API includono `UploadData` che consente di inviare dati tramite un payload di oggetti JSON.
+++
