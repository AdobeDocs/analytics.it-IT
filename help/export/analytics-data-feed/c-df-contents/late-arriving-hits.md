---
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042
translation-type: tm+mt

---
# Hit in arrivo

I dati della cronologia possono essere inseriti dopo che un processo di feed di dati ha terminato l'elaborazione per un determinato giorno o giorno, ad esempio attraverso hit con marca temporale o origini dati. Gli hit in arrivo sono una personalizzazione retroend fornita da Adobe per includere questi dati nei feed di dati.

## Funzionamento degli hit in arrivo

Quando un feed di dati elabora normalmente dati, l'aspetto dei dati è solo all'interno della relativa finestra di rapporti (in genere è l'ora o il giorno più recente). Se i dati vengono visualizzati dopo che un feed ha terminato l'elaborazione della finestra di reporting, questi dati non vengono mai inclusi in alcun feed di dati.

Con gli hit imminenti abilitati, il metodo di elaborazione cambia per includere tali dati. Ogni volta che un feed di dati elabora dati, osserva eventuali hit ritardati arrivati e li batch nel successivo file di feed dati inviato al tuo sito FTP.

## Attivazione degli hit in arrivo

I prossimi hit in arrivo possono essere attivati manualmente da Adobe su singoli feed di dati. Prima di procedere, considerate quanto segue:

* I dati per giorni diversi vengono spesso visualizzati nei feed di dati quando sono abilitati gli hit in arrivo. Assicuratevi che la piattaforma utilizzata per assimilare i feed dati possa contenere dati da giorni diversi all'interno dello stesso file.
* Gli hit in arrivo verso il basso aumentano il tempo di elaborazione. In genere questo ritardo è inferiore a ora, ma può essere più ore o più se la suite di rapporti riceve un numero elevato di hit in arrivo. Adobe consiglia di abilitare questa impostazione se l'arrivo tempestivo per i feed di dati è imperativo per il flusso di lavoro dell'organizzazione.
* Se un file di feed di dati viene rielaborato, gli hit in arrivo successivi inclusi nel file originale non sono inclusi nel file rielaborato.

Se desideri abilitare gli hit in arrivo per un feed di dati ricorrente esistente, chiedi a un utente supportato di contattare l'Assistenza clienti e includere quanto segue:

* Nota che desideri abilitare gli hit in arrivo per un feed di dati specifico
* ID suite di rapporti
* Nome feed dati
