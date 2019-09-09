---
title: Domande frequenti su Analytics tra dispositivi
description: Domande frequenti per Analytics cross-device
translation-type: tm+mt
source-git-commit: c104fbda3dc4a6be6b596c60c6e1973407d94f80

---


# Domande frequenti

**Come si utilizza CDA per vedere in che modo le persone passano da un tipo di dispositivo a un altro?**

Puoi usare una visualizzazione Flusso con la dimensione Tipo dispositivo mobile.

1. Accedi ad Adobe Analytics e crea un nuovo progetto Workspace vuoto.
2. Fai clic sulla scheda Visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sul quadro a destra.
3. Fai clic sulla scheda Componenti a sinistra, quindi trascina la dimensione «Tipo dispositivo mobile» nella posizione centrale «Dimensione o Elemento».
4. Questo rapporto di flusso è interattivo. Fare clic su uno qualsiasi dei valori per espandere i flussi nelle pagine successive o precedenti. Usate il menu di scelta rapida per espandere o comprimere le colonne. Dimensioni diverse possono essere utilizzate anche nello stesso rapporto sul flusso.

**Posso vedere in che modo le persone si spostano tra diverse esperienze utente (ad es. browser desktop rispetto a un'app mobile)?**

L'utilizzo di Tipo dispositivo mobile come illustrato sopra consente di vedere il modo in cui le persone si spostano tra i tipi di dispositivi mobili e i tipi di dispositivi desktop. Tuttavia, potrebbe essere utile distinguere i browser desktop dai browser mobili. Un modo per farlo è creare un evar che registra se l'esperienza si è verificata in un browser desktop, nel browser per dispositivi mobili o nell'app mobile. Quindi crea un diagramma di flusso come descritto qui sopra, utilizzando la tua evar «esperienza» anziché la dimensione Tipo dispositivo mobile. Questo fornisce una visualizzazione leggermente diversa sul comportamento cross-device.

**Quanto indietro vengono utilizzati dagli utenti CDA?**

* Adobe mantiene i dati legati per circa 30 giorni. Se un dispositivo non è identificato dal grafico Co-op o dal grafico privato, ma viene successivamente identificato entro 30 giorni, CDA torna indietro e ristabilisce tale dispositivo come appartenente a persona identificata fino a 30 giorni nel passato. Se parte del comportamento non identificato dell'utente non rientra nella finestra di lookback di 30 giorni, tale parte del percorso dell'utente non viene troncata.
* Adobe mantiene mappature dispositivo nel grafico Co-op e grafico privato per circa 6 mesi. Un ECID che non ha attività da oltre sei mesi viene rimosso dal grafico. I dati già cuciti in CDA non vengono modificati, ma gli hit successivi per quell'ECID vengono trattati come nuovo individuo.

**In che modo CDA gestisce gli hit con marca temporale?**

Adobe considera gli hit con marca temporale come se fossero stati ricevuti al momento della marca temporale, non quando Adobe ha ricevuto l'hit. Gli hit con marca temporale precedenti a 1 mese non possono essere cucito, poiché sono considerati fuori dall'intervallo Adobe mantenendo i dati utilizzati per la sovrapposizione.
