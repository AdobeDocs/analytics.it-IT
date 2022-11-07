---
description: Gli elenchi di pubblicazione consentono di inviare facilmente vari rapporti specifici per diversi gruppi dell’organizzazione senza creare diversi rapporti pianificati separati. Gli elenchi di pubblicazione sono utili se disponi di suite di rapporti specifiche per posizione e desideri fornire a ciascun reparto una copia di un dashboard specifico. In alternativa, puoi utilizzare gli elenchi di pubblicazione per inviare dati a più persone senza dover digitare separatamente i loro indirizzi e-mail, se lavori con una singola suite di rapporti.
title: Elenchi di pubblicazione
feature: Admin Tools
uuid: 07dad661-c302-4981-80d1-3169ad1fe90e
exl-id: 5c9a0ae7-742b-4247-bcbc-2e979af6160c
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 6%

---

# Elenchi di pubblicazione

Gli elenchi di pubblicazione consentono di inviare facilmente vari rapporti specifici per diversi gruppi dell’organizzazione senza creare diversi rapporti pianificati separati. Gli elenchi di pubblicazione sono utili se disponi di suite di rapporti specifiche per posizione e desideri fornire a ciascun reparto una copia di un dashboard specifico. In alternativa, puoi utilizzare gli elenchi di pubblicazione per inviare dati a più persone senza dover digitare separatamente i loro indirizzi e-mail, se lavori con una singola suite di rapporti.

È possibile specificare più elenchi di pubblicazione durante la pianificazione di un rapporto.

## Fine del ciclo di vita degli elenchi di pubblicazione

Come probabilmente saprete, il 31 dicembre 2023 Adobe deprecherà sia Reports and Analytics (R&amp;A) che il prodotto punto Site Catalyst. [Puoi saperne di più sulla fine del ciclo di vita e su come prepararti ad esso qui](https://express.adobe.com/page/6WnF8JK6IRDhf/).

Una delle funzioni di R&amp;A che si prevede raggiungerà la fine del ciclo di vita in questa data è Elenchi di pubblicazione. Alcune funzioni, come Eventi calendario e Rapporto di riepilogo pagina, hanno o avranno una versione di parità in Analysis Workspace. Tuttavia, gli elenchi di pubblicazione non sono tra questi e diventeranno obsoleti quando le attività di R&amp;A raggiungeranno la fine del loro ciclo di vita. **Non sarà possibile creare nuovi elenchi di pubblicazione o accedere a quelli esistenti per inviare o pianificare progetti di Analysis Workspace.**

Per attenuare eventuali interruzioni dei flussi di lavoro di distribuzione dei rapporti correnti che si basano su Elenchi di pubblicazione, è necessario considerare le seguenti alternative:

* Se utilizzi Elenchi di pubblicazione per distribuire la stessa versione del rapporto a più utenti (senza applicare sostituzioni alla suite di rapporti):

   Una volta ricreati i rapporti in Analysis Workspace come progetti, puoi utilizzare una combinazione di un gruppo di contatti o di una lista di distribuzione creata per il client di posta e la funzione Progetti pianificati di Workspace per inviare o pianificare la consegna ricorrente del progetto. Come per gli elenchi di pubblicazione, una versione PDF/CSV del progetto viene quindi inviata a ogni ID e-mail che fa parte del gruppo/elenco. Ulteriori informazioni [Progetti programmati qui](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html#:~:text=Scheduled%20Analysis%20Workspace%20projects%20can,options%20in%20the%20left%20rail.).

* Se utilizzi gli elenchi di pubblicazione per distribuire più versioni del rapporto o del dashboard a più utenti (tramite la funzione di sostituzione della suite di rapporti):

   Analysis Workspace non supporta le sostituzioni delle suite di rapporti. Inoltre, non supporta la possibilità di bloccare le suite di rapporti quando si condividono o si pianificano progetti. Per replicare il flusso di lavoro, potrebbe essere necessario creare più versioni dello stesso progetto con una suite di rapporti diversa applicata a ogni versione e quindi utilizzare la funzione di progetto pianificata descritta in precedenza.

Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe.

## Descrizioni di Publishing List Manager {#section_099DF8AC5691495F9B22C71266DD6004}

| Elemento | Descrizione |
|--- |--- |
| [!UICONTROL Search for] | Consente di filtrare la tabella per cercare un elenco di pubblicazione. |
| [!UICONTROL Report Suites to Include] | Sostituisce la suite di rapporti per un rapporto pianificato o tutti i minirapporti in un dashboard. Sebbene non vi siano limiti tecnici al numero di voci separate della suite di rapporti, si consiglia di limitarla a circa 50. Non esiste un limite stabilito al numero di e-mail che possono essere incluse. |
| [!UICONTROL E-mail Addresses] | Elenco delimitato da virgole di tutte le e-mail che riceveranno il rapporto con la nuova suite di rapporti.  Fai clic su **[!UICONTROL Click to Edit]** per specificare gli indirizzi e-mail da ricevere. Inserisci ogni indirizzo e-mail, separando più indirizzi e-mail con un punto e virgola (;). Press `<Enter>` al termine dell’immissione degli indirizzi e-mail. <br>Il campo Conteggio e-mail visualizza il numero di indirizzi e-mail attualmente associati alla voce della suite di rapporti. |
| [!UICONTROL Duplicate] | Crea una copia dell’elenco di pubblicazione. |
