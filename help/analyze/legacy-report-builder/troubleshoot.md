---
description: Scopri come ottimizzare la consegna di Report Builder e un elenco di messaggi di errore che potrebbero verificarsi.
title: Risoluzione dei problemi e procedure consigliate per Report Builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
feature: Report Builder
role: User, Admin
exl-id: 41a640ce-2316-439b-b3ba-f0bace9af268
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1403'
ht-degree: 52%

---

# Risoluzione dei problemi e procedure consigliate per Report Builder

{{legacy-arb}}

Questo articolo descrive la risoluzione dei problemi e le best practice da utilizzare per ottimizzare Report Builder. Include inoltre un elenco dei messaggi di errore che potrebbero essere visualizzati.

## Utenti di Report Builder 5.0 e apertura di cartelle di lavoro 5.1 {#section_C29898775999453FABB5FB0E098415C8}

Adobe ha cambiato il separatore tra dimensioni e classificazioni, ora è || anziché _. Questa modifica presenta implicazioni di compatibilità per utenti di Report Builder 5.0 che aprono una cartella di lavoro di Report Builder v5.1 con richieste di classificazione. Ogni volta che viene aperta una cartella di lavoro di una versione precedente alla 5.1 tutte le relative richieste di classificazione serializzate vengono convertite in questo formato.

Questo introduce un problema di compatibilità per le versioni successive: quando si passa alla v5.1, se una cartella di lavoro viene condivisa con un utente in Report Builder v5.0, tale utente non sarà in grado di riconoscere la richiesta di classificazione, in quanto cerca il carattere “_” mentre la v5.1 ha serializzato “||”.

Si verificherà questo effetto collaterale all’apertura di una cartella di lavoro ARB v5.1 con richiesta di classificazione:

* All’apertura della cartella di lavoro viene visualizzato il seguente avviso: “La cartella di lavoro è stata salvata l’ultima volta con Report Builder v5.1. Questa versione ha introdotto alcune funzionalità incompatibili con la versione di Report Builder installata in questo computer. Prima di aggiornare la cartella di lavoro, si consiglia di effettuare l’aggiornamento alla versione più recente di Report Builder”.
* Facendo clic con il pulsante destro del mouse su una richiesta ARB con classificazione, i menu di scelta rapida di Report Builder (modifica richiesta, aggiungi richiesta dipendente...) non verranno visualizzati.
* Se si esegue un aggiornamento completo facendo clic sul terzo pulsante o aggiornando un set di richieste dal modulo Request Manager, la richiesta di classificazione verrà eseguita senza errori. Tuttavia, i valori delle classificazioni non verranno forniti.
* È comunque possibile modificare la richiesta aprendo Request Manager e passando da una riga all’altra fino a raggiungere la richiesta corretta.
* Se si modifica la richiesta lasciando invariati tutti i parametri e si fa clic su Fine, la risposta verrà fornita correttamente. La modifica della richiesta risolve il problema mano a mano che i parametri del layout di risposta vengono nuovamente serializzati. Quindi c’è una soluzione alternativa, anche se richiede molto tempo.

## Problemi di autenticazione in Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Report Builder richiede l’autenticazione per creare richieste di dati dalle suite di rapporti. A volte si verificano problemi durante l&#39;accesso a Report Builder a seconda delle impostazioni in [!DNL Analytics] o della rete.

* **Società di accesso non valida**: questo errore si verifica in genere quando la società di accesso viene immessa in modo errato o in caso di problemi di attività di rete. Effettua le seguenti operazioni:
   * Per verificare che non sia presente un errore ortografico o uno spazio errato, controlla l’ortografia della società di accesso.
   * Accedi ad Analytics con la stessa società di accesso per assicurarti che sia corretta. Se non riesci ad accedere con tali credenziali, contatta uno degli amministratori dell’organizzazione per ottenere la società di accesso corretta.
* **Firewall**: Report Builder utilizza le porte 80 e 443. Assicurati che queste porte siano consentite dal firewall dell’organizzazione. Per ulteriori esclusioni del firewall, consulta inoltre gli indirizzi IP interni di Adobe.

## Raccomandazioni per l’ottimizzazione delle richieste {#section_33EF919255BF46CD97105D8ACB43573F}

I seguenti fattori possono aumentare la complessità delle richieste e rallentarne l’elaborazione.

* **Fattori che possono rallentare le consegne**: troppi segnalibri, dashboard e cartelle di lavoro di Report Builder sono stati pianificati in poche ore. Considera anche che troppe cartelle di lavoro di Report Builder sono state pianificate più o meno nello stesso momento. In questo caso, la coda dell’API del rapporto viene inserita nel backlog.
* **Fattori che possono rallentare il runtime della cartella di lavoro**: aumento significativo delle classificazioni o aumento dell&#39;intervallo di date della richiesta nel tempo.
* **Cause che causano errori di consegna della cartella di lavoro**: formule Excel complesse in una cartella di lavoro, in particolare quelle che riguardano data e ora.
* **Celle che restituiscono 0 (nessun valore)**: un apostrofo o una virgoletta singola nel nome del foglio di Excel causerà la mancata restituzione di valori in Report Builder. Si tratta di una limitazione di Microsoft Excel.
* **Prestazioni singole richieste**: la velocità di elaborazione può essere influenzata dalle impostazioni seguenti:

  | Impostazione | Prestazioni più rapide | Prestazioni più lente |
  |--- |--- |--- |
  | Raggruppamenti e ordine dei raggruppamenti | Pochi | Molti |
  |  | Esempio: in caso di raggruppamento da A a Z, il numero di elementi per A deve sempre essere minore del numero di elementi per Z, in caso contrario il tempo di richiesta può aumentare notevolmente. |  |
  | Intervallo date | Intervallo piccolo | Intervallo ampio |
  | Filtro | Filtro specifico | Filtri più popolari |
  | Granularity (Granularità) | Aggregata | Oraria<ul><li>Giornaliero</li><li>Settimanale</li><li>Mensile</li><li>Trimestrale</li><li>Annuale</li></ul> |
  | Numero di voci | Set di dati piccolo | Set di dati grande |

* **Ora di pianificazione**: pianificazione scaglionata su un periodo di 24 ore (vedere la tabella seguente). I segnalibri, le dashboard e le cartelle di lavoro di Report Builder esistenti pianificati insieme potrebbero causare ritardi. Pianifica le richieste più grandi e complesse la mattina presto per consentire l’esecuzione di richiami manuali e aggiornamenti durante la giornata lavorativa.

  | Tempo di pianificazione | 1:00 - 2:00 | 2:00 - 7:00 | 7:00 - 18:00 | 18:00 - mezzanotte |
  |--- |--- |--- |--- |--- |
  | Utilizzo di Report Builder | Poco utilizzato | Molto utilizzato | Utilizzo lato client.<br>Volumi più elevati di utenti che aggiornano localmente e richiedono invii immediati.<br>Inoltre, verifica se la coda API viene cancellata quando scadono le cartelle di lavoro pianificate. | Non molto utilizzato |

* **Timeout**: qualsiasi rapporto pianificato scade dopo quattro ore. Il sistema tenta di pianificare altre tre volte, generando potenzialmente un errore. In genere, più grande è il set di dati, più lungo sarà il tempo necessario per l&#39;esecuzione. Questi sono visibili nella reportistica di [!DNL Analytics] e in Report Builder:

## Descrizioni dei messaggi di errore di esempio {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Questa sezione include un elenco di esempi di messaggi di errore che possono verificarsi quando si utilizza Report Builder.

>[!NOTE]
>
>Questo è un esempio di messaggi di errore e non un elenco esaustivo. Per ulteriori informazioni sulla risoluzione degli errori, contatta l’amministratore.

* **Questa caratteristica può essere applicata solo a una cartella di lavoro aperta.**: se in Excel non sono aperte cartelle di lavoro (documenti foglio di calcolo) e si fa clic su una delle icone nella barra degli strumenti di Report Builder, viene visualizzato questo messaggio. Inoltre, la barra degli strumenti viene disattivata fino all’apertura di un foglio di calcolo. Tuttavia, è possibile fare clic sull’icona della guida online mentre la barra degli strumenti è ancora abilitata senza causare questo errore.
* **Uscire da [!UICONTROL Request Wizard] prima di attivare [!UICONTROL Request Manager].**: anche se [!UICONTROL Request Manager] e [!UICONTROL Request Wizard] sono collegati correttamente, non è possibile iniziare a lavorare con [!UICONTROL Request Manager] prima di completare o annullare le azioni eseguite in [!UICONTROL Request Wizard].
* **Nessuna richiesta associata a questo intervallo.**: questo messaggio di errore si verifica se si fa clic sul pulsante [!UICONTROL From Sheet] in [!UICONTROL Request Manager] quando una cella del foglio di calcolo non contiene richieste. Per identificare le celle del foglio di calcolo contenenti richieste, fai clic sulle singole richieste elencate nella tabella in [!UICONTROL Request Manager]. Se una richiesta è associata alle celle, queste ultime appaiono evidenziate quando la richiesta viene selezionata nella tabella.
* **L’intervallo selezionato non è valido. Seleziona un altro intervallo.**: se è selezionata una cella del foglio di calcolo a cui è già stata mappata una richiesta, si verifica questo errore. Elimina la richiesta mappata alle celle o scegli un altro intervallo di celle da mappare. Per eliminare le celle è importante individuare le celle contenenti richieste ed eliminare la richiesta prima di eliminare le celle (ovvero rimuovere righe o colonne).
* **Esci dalla cella Excel con lo stato attivo prima di utilizzare questa funzione.**: se sei in *modalità di modifica* in una cella Excel e fai clic su una delle icone di Report Builder, viene visualizzato questo messaggio di errore. La modalità di modifica in una cella Excel indica che la cella è selezionata e il cursore viene visualizzato al suo interno. In una cella di Excel è inoltre attiva la modalità di modifica quando si digita direttamente nella barra [!UICONTROL Formula] o nella [!UICONTROL Name Box] nella parte superiore di Excel.
* **L’intervallo selezionato interseca l’intervallo di un’altra richiesta. Modifica la selezione.**: se hai già mappato un set di celle al foglio di calcolo, viene visualizzato questo errore.
* **Ripristino della cartella di lavoro (record rimossi: formula dalla parte /xl/calcChain.xml)**: a volte le formule di una cartella di lavoro vengono danneggiate durante il salvataggio o il trasferimento. Quando il file viene aperto, Excel tenta di eseguire queste formule e ha esito negativo. È possibile risolvere il problema rimuovendo `calcChain.xml` dal foglio di calcolo, obbligando Excel ad aggiornare i calcoli della formula.
   1. Rinominare l&#39;estensione di file della cartella di lavoro da `.xlsx` a `.zip`.
   2. Decomprimere il contenuto e aprire la cartella `/xl/`.
   3. Elimina `calcChain.xml`.
   4. Comprimere nuovamente il contenuto e ripristinare l&#39;estensione del file in `.xlsx`.
   5. Apri la cartella di lavoro in Excel e aggiorna tutte le richieste Report Builder.
* **È possibile che le celle di Excel associate ai filtri di input o all&#39;intervallo di output siano state eliminate**: Report Builder utilizza i nomi di Excel per allegare le richieste di dati alle celle. Se si eliminano i nomi di Excel da Gestione nomi, è possibile visualizzare questo errore. Non è possibile recuperare le richieste se i nomi Excel vengono eliminati. Se la cartella di lavoro è stata pianificata, è possibile scaricarne una copia da Gestione pianificazione oppure aprire le copie consegnate in precedenza della cartella di lavoro.
