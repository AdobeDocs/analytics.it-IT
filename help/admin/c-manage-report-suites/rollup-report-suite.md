---
description: Descrizioni dei tipi di suite di rapporti e confronto delle suite di rapporti globali e delle suite di rapporti rollup.
title: Avvisi suite di rapporti
topic: Strumenti di amministrazione
uuid: c90b8e38-2c95-4318-8165-a362106b6142
translation-type: tm+mt
source-git-commit: 9bc2e0425fa99efb32561ad1f80605e078eb7650
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 0%

---


# Avvisi suite di rapporti

<!-- change filename since page name changed? -->

Puoi configurare le suite di rapporti come *suite di rapporti globali* o *suite di rapporti rollup*.

## Suite di rapporti globali

Una suite di rapporti globale raccoglie dati da tutti i domini e le app di proprietà della tua organizzazione. Richiede l’implementazione per inviare tutte le richieste di immagini a un’unica suite di rapporti.

Nella maggior parte dei casi, Adobe consiglia di implementare una suite di rapporti globale. Consulta &quot;[Considerazioni globali sulla suite di rapporti](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html)&quot; per i vantaggi dell&#39;implementazione di una suite di rapporti globale.

Puoi fornire sottoinsiemi dei dati globali della suite di rapporti della tua azienda a utenti finali diversi utilizzando gli approcci *multi-suite tagging* e *suite di rapporti virtuali* :

* **Assegnazione di tag** a più suite: L’assegnazione tag a più suite consente di inviare richieste di immagini non solo a una suite di rapporti globale, ma anche a suite di rapporti figlio individuali. I dati del rapporto globale vengono deduplicati in tutte le suite di rapporti.

   Ad esempio, puoi raccogliere tutti i dati in una suite di rapporti globale e impostare suite di rapporti secondarie in base al marchio, alla regione o a un altro differenziatore. I diversi team della tua azienda possono quindi concentrarsi sui dati nelle suite di rapporti che sono pertinenti per loro.

   Per utilizzare l’assegnazione tag a più suite, implementa suite di rapporti figlio e una suite di rapporti globale che includa tutti i dati provenienti dagli elementi figlio. Il codice di tracciamento per le pagine web e le app includerà l&#39;ID suite di rapporti (RSID) per la suite di rapporti globale e anche gli RSID per le suite di rapporti figlio applicabili.<!-- Wording/be more specific? And include any links? -->

   Viene effettuata una chiamata server separata a ogni suite di rapporti nella richiesta di immagine. Le chiamate alle suite di rapporti figlio sono chiamate secondarie.

* **Suite** di rapporti virtuale: Un rapporto  [virtuale ](/help/components/vrs/vrs-about.md) è costituito da una query su segmenti specifici raccolti in una suite di rapporti globale e disponibili per gruppi di utenti specifici. Le suite di rapporti virtuali ti consentono di curare gli elementi dei rapporti per utenti finali diversi senza utilizzare l’assegnazione tag a più suite, evitando in tal modo le chiamate al server secondario.

   Per utilizzare le suite di rapporti virtuali, implementa una suite di rapporti globale, quindi analizza i dati per creare suite di rapporti virtuali con segmenti specifici applicati e con autorizzazioni di gruppo specifiche. È possibile creare suite di rapporti virtuali in Gestione suite di rapporti virtuale ([!UICONTROL Components] > [!UICONTROL Virtual Report Suites]). Per ulteriori informazioni, consulta &quot;[Flusso di lavoro suite di rapporti virtuali](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)&quot;.

Spesso è consigliabile utilizzare suite di rapporti virtuali invece di assegnare tag a più suite, ma le suite di rapporti virtuali hanno alcune limitazioni. Consulta &quot;[Suite di rapporti virtuali e considerazioni sull’assegnazione di tag a più suite](/help/components/vrs/vrs-considerations.md)&quot; per determinare quale approccio alla suite di rapporti è la scelta migliore per le tue esigenze aziendali. Per un confronto approfondito delle suite di rapporti virtuali e delle funzionalità di assegnazione tag con più suite, consulta &quot;[Suite di rapporti virtuali e assegnazione di tag a più suite](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot;.

## Report di rollup

>[!NOTE]
>
>[!DNL Reports & Analytics] è l’unico strumento che supporta i rapporti di rollup e Adobe non consiglia più di utilizzare i rollup. È invece consigliabile utilizzare una suite di rapporti globale con tag per più suite o suite di rapporti virtuali.

Un rapporto di rollup è una semplice aggregazione di dati provenienti da più suite di rapporti, senza deduplicazione o raggruppamenti di segmenti o dati. I rollup non richiedono l’implementazione del codice. Per utilizzare i rapporti di rollup, [implementa suite di rapporti figlio](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) e quindi [combinale in un rapporto di rollup](/help/admin/c-manage-report-suites/t-rollups.md) utilizzando [!UICONTROL Admin Tools].

I rapporti rollup sono gratuiti: le suite di rapporti figlio eseguono le proprie chiamate al server, ma il rollup non comporta chiamate aggiuntive. I rollup sono una funzione legacy e hanno molte limitazioni.

### Limitazioni dei rapporti di rollup {#limitations-rollups}

* I rollup forniscono dati totali, ma non segnalano valori singoli nei rapporti. Ad esempio, i valori eVar1 non sono inclusi, ma il loro totale aggregato può essere.
* I dati non vengono deduplicati quando il rollup combina i dati tra le suite di rapporti.
* I rollup corrono di notte a mezzanotte.
* Quando aggiungi una suite di rapporti a un rollup esistente, i dati storici non vengono inclusi nel rollup.
* Tutte le suite di rapporti figlio devono contenere dati per poter eseguire il rollup in una funzione. Se in un rollup sono incluse nuove suite di rapporti, assicurati di inviare almeno una visualizzazione di pagina a ciascuna di queste suite di rapporti.
* Le suite di rapporti rollup possono includere un massimo di 40 suite di rapporti figlio.
* Le suite di rapporti rollup possono includere un massimo di 100 eventi.
* I dati contenuti nelle suite di rapporti rollup non supportano raggruppamenti o segmenti.
* Il rapporto Pagine viene sostituito dal rapporto Siti più popolari , che riporta le metriche a livello di suite figlio.

## Confronto tra le funzioni della suite di rapporti globale e delle funzioni dei rapporti rollup

**Chiamate** server secondarie: I rollup non generano chiamate server aggiuntive oltre a quelle raccolte da una singola suite di rapporti. Se l’organizzazione utilizza l’assegnazione tag a più suite, vengono effettuate chiamate server secondarie per ogni suite di rapporti aggiuntiva inclusa in una richiesta di immagine.

>[!TIP]
>
>Se utilizzi solo una suite di rapporti globale con [suite di rapporti virtuali](/help/components/vrs/vrs-considerations.md), non sono necessarie chiamate server secondarie.

**Modifiche** all&#39;implementazione: I rollup non richiedono modifiche di implementazione, mentre le suite di rapporti globali richiedono di includere l’ID suite di rapporti globale nell’implementazione.

**Duplicazione**: Le suite di rapporti globali deduplicano i visitatori univoci, mentre i rollup no. Ad esempio, se un utente visita tre dei tuoi domini nello stesso giorno, i rollup contano tre visitatori univoci giornalieri. Le suite di rapporti globali registrano un visitatore univoco.

**Intervallo di tempo**: I rollup vengono elaborati solo a mezzanotte ogni notte, mentre le suite di rapporti globali segnalano i dati con latenza standard.

**Ampiezza**: I rollup non possono comunicare tra le suite di rapporti. Le suite di rapporti globali possono attribuire il credito alle variabili di conversione tra suite di rapporti e fornire percorsi tra suite di rapporti.

**Dati** storici: I rollup possono aggregare i dati storici, mentre le suite di rapporti globali riportano solo i dati dal momento in cui sono stati implementati.

**Rapporti**: Le suite di rapporti globali forniscono dati su tutte le dimensioni; i rollup forniscono dati aggregati solo su report di alto livello.

**Prodotti** supportati: I rollup possono essere utilizzati solo in Reports &amp; Analytics. Non sono supportati in Analysis Workspace o Data Warehouse. Le suite di rapporti globali possono essere utilizzate in tutti i prodotti.

**Numero di suite** di rapporti aggregate: I rollup supportano solo un massimo di 40 suite di rapporti figlio. Le suite di rapporti globali possono essere implementate su qualsiasi numero di domini o app che possiedi.
