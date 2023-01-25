---
description: Descrizioni dei tipi di suite di rapporti e confronto tra le suite di rapporti globali e le suite di rapporti di aggregazione dati.
title: Approcci suite di rapporti
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
source-git-commit: e8cbf24f6e0c829dadb2a6e7db502d0e8ba1f07f
workflow-type: ht
source-wordcount: '967'
ht-degree: 100%

---

# Approcci suite di rapporti

<!-- change filename since page name changed? -->

Puoi configurare le suite di rapporti come *suite di rapporti globali* o *suite di rapporti di aggregazione dati*.

## Suite di rapporti globali

Una suite di rapporti globale raccoglie dati da tutti i domini e le app di proprietà della tua organizzazione. Richiede l’implementazione per inviare tutte le richieste di immagini a un’unica suite di rapporti.

Nella maggior parte dei casi, Adobe consiglia di implementare una suite di rapporti globale. Consulta le [considerazioni sulla suite di rapporti globale](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=it) per i vantaggi dell’implementazione di una suite di rapporti globale.

Puoi fornire sottoinsiemi dei dati della suite di rapporti globale della tua azienda a utenti finali diversi utilizzando gli approcci *assegnazione di tag multisuite* e *suite di rapporti virtuale*:

* **Assegnazione di tag multisuite**: consente di inviare richieste di immagini non solo a una suite di rapporti globale, ma anche a specifiche suite di rapporti figlio. I dati del rapporto globale vengono deduplicati in tutte le suite di rapporti.

   Ad esempio, puoi raccogliere tutti i dati in una suite di rapporti globale e impostare suite di rapporti secondarie in base al marchio, all’area geografica o a un altro differenziatore. I diversi team della tua azienda possono quindi concentrarsi sui dati delle suite di rapporti che ritengono pertinenti.

   Per utilizzare l’assegnazione tag multisuite, implementa suite di rapporti figlio e una suite di rapporti globale che includa tutti i dati provenienti dagli elementi figlio. Il codice di tracciamento per le tue app e pagine Web includerà l’ID suite di rapporti (RSID) per la suite di rapporti globale e gli RSID per le suite di rapporti figlio applicabili.<!-- Wording/be more specific? And include any links? -->

   Viene effettuata una chiamata al server separata a ogni suite di rapporti nella richiesta di immagine. Le chiamate alle suite di rapporti figlio sono chiamate secondarie.

* **Suite di rapporti virtuali**: una [suite di rapporti virtuale](/help/components/vrs/vrs-about.md) è una query su segmenti specifici raccolti in una suite di rapporti globale, disponibile per gruppi di utenti specifici. Le suite di rapporti virtuali consentono di curare gli elementi dei rapporti per utenti finali diversi senza utilizzare l’assegnazione tag multisuite, evitando in tal modo le chiamate al server secondarie.

   Per utilizzare le suite di rapporti virtuali, implementa una suite di rapporti globale, quindi analizza i dati per creare suite di rapporti virtuali con segmenti specifici applicati e con autorizzazioni di gruppo specifiche. È possibile creare suite di rapporti virtuali nella gestione delle suite di rapporti virtuali ([!UICONTROL Components] > [!UICONTROL Virtual Report Suites]). Per ulteriori informazioni, consulta la sezione sul [flusso di lavoro per suite di rapporti virtuali](/help/components/vrs/c-workflow-vrs/vrs-workflow.md).

Invece di usare più suite di rapporti con tag, spesso è preferibile utilizzare le suite di rapporti virtuali; tuttavia queste presentano alcune limitazioni. Consulta le [considerazioni sulle suite di rapporti virtuali e sull’assegnazione di tag a più suite](/help/components/vrs/vrs-considerations.md) per capire quale approccio scegliere in base alle tue esigenze di business. Per un confronto approfondito tra suite di rapporti virtuali e la funzionalità di tag per più suite, vedi il [confronto tra suite di rapporti virtuali e tag per più suite](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78).

## Rapporti di aggregazione dati

>[!NOTE]
>
>[!DNL Reports & Analytics] è l’unico strumento che supporta i rapporti di aggregazione dati; Adobe non consiglia più l’uso delle aggregazioni dati. Piuttosto, è consigliabile utilizzare una suite di rapporti globale con assegnazione di tag a più suite o le suite di rapporti virtuali.

Un rapporto di aggregazione dati è una semplice aggregazione di dati provenienti da più suite di rapporti, senza deduplicazione né raggruppamenti di segmenti o dati. Le aggregazioni dati non richiedono alcuna implementazione di codice. Per utilizzare i rapporti di aggregazione dati, [implementa suite di rapporti figlio](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) e poi [combinale in un rapporto di aggregazione dati](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-rollups.md) utilizzando [!UICONTROL Admin Tools].

I rapporti di aggregazione dati sono gratuiti: le suite di rapporti figlio eseguono le proprie chiamate al server, ma l’aggregazione dati non comporta chiamate aggiuntive. Le aggregazioni dati sono una funzione legacy e presentano molte limitazioni.

### Limitazioni dei rapporti di aggregazione dati {#limitations-rollups}

* Le aggregazioni dati forniscono dati totali, ma non includono i valori singoli nei rapporti. Ad esempio, i valori eVar1 non sono inclusi, ma può esserlo il relativo valore totale aggregato.
* I dati non vengono deduplicati quando l’aggregazione dati combina i dati di diverse suite di rapporti.
* Le aggregazioni dati vengono eseguite ogni notte a mezzanotte.
* Quando aggiungi una suite di rapporti a un’aggregazione dati esistente, i dati storici non vengono inclusi nell’aggregazione.
* Affinché l‘aggregazione dati funzioni, tutte le suite di rapporti figlio devono contenere dei dati. Se in un’aggregazione dati sono incluse nuove suite di rapporti, assicurati di inviare a ciascuna almeno una visualizzazione di pagina.
* Le suite di rapporti di aggregazione dati possono includere fino a 40 suite di rapporti figlio.
* Le suite di rapporti di aggregazione dati possono includere fino a 100 eventi.
* I dati contenuti nelle suite di rapporti di aggregazione dati non supportano raggruppamenti o segmenti.
* Il rapporto Pagine viene sostituito dal rapporto Siti più popolari, che riporta le metriche a livello di suite figlio.

## Confronto tra le funzioni Suite di rapporti globale e Rapporto di aggregazione dati

**Chiamate al server secondarie**: le aggregazioni dati non generano chiamate al server aggiuntive oltre a quelle raccolte da una singola suite di rapporti. Se l’organizzazione utilizza l’assegnazione di tag a più suite, vengono effettuate chiamate al server secondarie per ogni suite di rapporti aggiuntiva inclusa in una richiesta di immagine.

>[!TIP]
>
>Se utilizzi solo una suite di rapporti globale con [suite di rapporti virtuali](/help/components/vrs/vrs-considerations.md), non sono necessarie chiamate al server secondarie.

**Modifiche all’implementazione**: le aggregazioni dati non richiedono modifiche all’implementazione; per le suite di rapporti globali è invece necessario includere nell’implementazione l’ID della suite di rapporti globale.

**Duplicazione**: le suite di rapporti globali deduplicano i visitatori univoci, le aggregazioni dati no. Ad esempio, se un utente visita tre dei tuoi domini nello stesso giorno, le aggregazioni dati contano tre visitatori univoci giornalieri. Le suite di rapporti globali registrano invece un solo visitatore univoco.

**Intervallo temporale**: le aggregazioni dati vengono elaborate solo ogni notte a mezzanotte; le suite di rapporti globali presentano i dati con latenza standard.

**Ambito**: le aggregazioni dati non possono comunicare tra diverse suite di rapporti. Le suite di rapporti globali possono attribuire il merito alle variabili di conversione e fornire percorsi tra diverse suite di rapporti.

**Dati storici**: le aggregazioni dati possono aggregare i dati storici; le suite di rapporti globali presentano i dati solo a partire dal momento in cui sono state implementate.

**Rapporti**: le suite di rapporti globali forniscono dati su tutte le dimensioni; le aggregazioni dati forniscono dati aggregati solo sui rapporti di alto livello.

**Prodotti supportati**: le aggregazioni dati possono essere utilizzate solo in Reports &amp; Analytics. Non sono supportati in Analysis Workspace o Data Warehouse. Le suite di rapporti globali possono essere utilizzate in tutti i prodotti.

**Numero di suite di rapporti aggregate**: le aggregazioni dati supportano un massimo di 40 suite di rapporti figlio. Le suite di rapporti globali possono essere implementate in qualsiasi numero di domini o app di tua proprietà.
