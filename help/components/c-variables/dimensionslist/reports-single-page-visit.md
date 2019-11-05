---
description: Per non confondersi con la metrica Visite di pagina singola in Analisi ad hoc, il rapporto Visite di pagina singola mostra le pagine inserite e uscite dai visitatori del sito Web, senza adottare misure per visualizzare altre pagine.
seo-description: Per non confondersi con la metrica Visite di pagina singola in Analisi ad hoc, il rapporto Visite di pagina singola mostra le pagine inserite e uscite dai visitatori del sito Web, senza adottare misure per visualizzare altre pagine.
seo-title: Visita singola pagina
solution: Analytics
title: Visita singola pagina
topic: Rapporti
uuid: 5ca52be8-c7f5-464a-8a06-55e8271760b4
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Visita singola pagina

Per non confondersi con la metrica Visite di pagina singola in Analisi ad hoc, il rapporto Visite di pagina singola mostra le pagine inserite e uscite dai visitatori del sito Web, senza adottare misure per visualizzare altre pagine.

Questo rapporto è utilizzato più comunemente nel contesto del [!UICONTROL Pages] rapporto, ma può essere visualizzato anche in tutte le variabili di traffico con [!UICONTROL pathing] abilitato. Potete utilizzare questo rapporto per identificare le pagine di entrata che meno hanno la probabilità di obbligare un visitatore a esplorare ulteriormente il sito, o per determinare quante visite sono composte da una singola pagina. Queste informazioni consentono di ottimizzare il contenuto per ridurre le uscite su tali pagine.

## Proprietà del report {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* È possibile recuperare un rapporto identico richiamando un [!UICONTROL Pages] rapporto, utilizzando [!UICONTROL Single Access] come metrica.

* Una singola visita di pagina è considerata una visita contenente un valore univoco, non una singola richiesta di immagine.

   * Nel contesto di un rapporto [sulle](/help/components/c-variables/dimensionslist/reports-pages.md)pagine, all’interno della visita è possibile attivare solo una pagina univoca.
   * Nel contesto di un rapporto [sulle sezioni del](/help/components/c-variables/dimensionslist/reports-site-sections.md)sito, viene attivata una singola sezione del sito all’interno della visita.
   * Nel contesto di una variabile [di](/help/admin/admin/c-traffic-variables/traffic-var.md)traffico, una visita compila il rapporto se viene attivato un singolo valore univoco.

* Le visite a pagina singola possono essere costituite da molte richieste di immagini, purché la variabile nel contesto del rapporto contenga un unico valore. Non appena viene popolato un secondo valore univoco, la visita non viene più considerata una visita a una singola pagina.
* Questo è considerato un tipo di rapporto di percorso. Per impostazione predefinita, il percorso della [!UICONTROL Pages] variabile è attivato. Tuttavia, qualsiasi variabile di traffico ha anche questa funzionalità. L’abilitazione del percorso per ulteriori variabili di traffico dipende dal contratto. Per informazioni, contattate l'Account Manager della vostra organizzazione.
* Questo rapporto può utilizzare un filtro di ricerca per individuare specifici elementi di riga.
* Questo rapporto può essere visualizzato sia in formato [con tendenze](/help/components/c-variables/dimensionslist/reports-types.md) che in formato [classifica](/help/components/c-variables/dimensionslist/reports-types.md) .

* Nessuna analisi approfondita disponibile in questo rapporto.
* L'unica metrica disponibile in questo rapporto è [!UICONTROL Visits].

