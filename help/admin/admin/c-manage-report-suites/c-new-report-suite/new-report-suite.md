---
description: Per creare una nuova suite di rapporti, puoi selezionare un modello preimpostato o utilizzare come modello una suite di rapporti esistente.
title: 'Nuova suite di rapporti: impostazioni'
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 100%

---

# Nuova suite di rapporti: impostazioni

Per creare una nuova suite di rapporti, puoi selezionare un modello preimpostato o utilizzare come modello una suite di rapporti esistente.

Descrizioni degli elementi utilizzati per [creare una suite di rapporti](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>La [documentazione delle suite di rapporti virtuali](/help/components/vrs/c-workflow-vrs/vrs-create.md) mostra come creare suite di rapporti virtuali.

| Elemento | Descrizione |
| --- | --- |
| ID suite di rapporti | Specifica un ID univoco; può contenere solo caratteri alfanumerici. Una volta creato, non è possibile modificare questo ID. Adobe imposta il prefisso ID richiesto, che non può essere modificato.  Quando crei più suite di rapporti, assicurati di usare una convenzione di denominazione tale da garantire ID univoci per le suite di rapporti. |
| Titolo sito | Identifica la suite di rapporti negli strumenti di amministrazione. Questo titolo viene utilizzato anche nell’elenco a discesa Suite di rapporti nell’intestazione della suite. |
| Fuso orario | Determina eventi e dati di marca temporale. |
| URL di base | (Facoltativo) Definisce il dominio di base per la suite di rapporti. Questo URL funziona come filtro URL interno se non definisci esplicitamente i filtri URL interni per la suite di rapporti. |
| Pagina predefinita | (Facoltativo) Elimina le occorrenze del valore Pagina predefinita dagli URL rilevati. Se il rapporto  Pagine più popolari contiene URL anziché nomi di pagina, impedisce l’utilizzo di più URL per la stessa pagina web.  Ad esempio, gli URL `https://example.com` e `https://example.com/index.html` si riferiscono in genere alla stessa pagina.<p> Puoi rimuovere i nomi di file estranei in modo che, nei rapporti, entrambi questi URL vengano visualizzati come `https://example.com`. Se non imposti questo valore, Analytics rimuove automaticamente i seguenti nomi di file dagli URL: `index.htm`, `index.html`, `index.cgi`, `index.asp`, `default.htm`, `default.html`, `default.cgi`, `default.asp`, `home.htm`, `home.html`, `home.cgi` e `home.asp`. Per disabilitare la rimozione del nome file, specifica un valore di pagina predefinito che non si verifica mai negli URL. |
| Data pubblicazione | Informa Adobe della data in cui la suite di rapporti diventerà attiva. Se la pianificazione dell’implementazione cambia, fornisci una stima del traffico aggiornata utilizzando lo strumento Traffico previsto permanente in Gestione del traffico. |
| Visualizzazioni pagina stimate al giorno | Identifica una stima del numero di visualizzazioni di pagina che la suite di rapporti supporterà in un giorno. Volumi di traffico elevati richiedono un processo di approvazione più lungo. Per evitare ritardi nell’elaborazione, specifica una stima che sia quanto più accurata possibile. |
| Valuta di base | Specifica la valuta predefinita utilizzata per memorizzare tutti i dati monetari. La funzione di reporting di Analytics converte le transazioni in altre valute nella valuta di base, utilizzando il tasso di conversione corrente al momento in cui riceve i dati. Per identificare la valuta di una determinata transazione, la funzione di reporting di Analytics utilizza la variabile JavaScript  currencyCode. |
| Disabilita supporto caratteri multibyte | Disattiva il supporto di caratteri multibyte per la suite di rapporti. Se disattivi il supporto per caratteri multibyte, il sistema presuppone che i dati siano in formato `ISO-8859-1`. Il set di caratteri delle pagine web deve essere specificato nella variabile JavaScript  charSet. <p>Il supporto per caratteri multibyte memorizza i caratteri nella suite di rapporti utilizzando il formato UTF-8. Al momento della ricezione, il sistema converte i dati dal set di caratteri della pagina web al set di caratteri UTF-8, in modo da poter utilizzare qualsiasi lingua nei rapporti di marketing.  Per modificare il supporto dei caratteri multibyte per una suite di rapporti esistente, contatta il tuo Account Manager o l’Assistenza clienti. |

{style=&quot;table-layout:auto&quot;}
