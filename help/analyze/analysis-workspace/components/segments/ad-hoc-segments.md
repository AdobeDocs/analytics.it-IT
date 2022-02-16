---
description: Usare i segmenti ad hoc in Analysis Workspace.
title: Segmenti ad hoc
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 100%

---

# Segmenti di progetto ad hoc

Ecco un video sulla creazione di segmenti di progetto ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Puoi creare segmenti di progetto ad hoc se desideri esplorare rapidamente in che modo un segmento potrebbe influenzare il progetto, senza passare al Generatore di segmenti. Considera questi segmenti come segmenti temporanei a livello di progetto. In genere non fanno parte della “libreria” di segmenti, come i segmenti dei componenti nella barra a sinistra. Tuttavia, puoi salvarli, come illustrato di seguito.

Per un confronto tra le funzionalità dei segmenti rapidi e quelle dei segmenti veri e propri a livello di componente, visita [questa pagina](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

1. Puoi rilasciare qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, segmento, modello di segmento, intervallo di date) nella zona di rilascio dei segmenti, nella parte superiore di un pannello. I tipi di componente vengono automaticamente convertiti in segmenti.
Ecco un esempio di come creare un segmento per il dominio di riferimento Twitter:

   ![](assets/ad-hoc1.png)

   Il pannello applica automaticamente questo segmento e puoi vedere immediatamente i risultati.

1. Puoi aggiungere a un pannello un numero illimitato di componenti.
1. Se decidi di salvare questo segmento, consulta la sezione seguente.

Nota bene:

* Nella zona dei segmenti **non è possibile** rilasciare i tipi di componenti seguenti: metriche calcolate e dimensioni/metriche da cui non è possibile creare i segmenti.
* Per eventi e dimensioni intere, Analysis Workspace crea dei segmenti di hit di tipo “esiste”. Esempi: `Hit where eVar1 exists` o `Hit where event1 exists`.
* Se nella zona di rilascio dei segmenti viene rilasciato “Non specificato” o “Nessuno”, vengono automaticamente convertiti in un segmento di tipo “non esiste” in modo da essere trattati correttamente nella segmentazione.

>[!NOTE]
>
>I segmenti creati in questo modo sono interni al progetto.

## Salvare segmenti di progetto ad hoc {#ad-hoc-save}

Puoi scegliere di salvare i segmenti seguendo questi passaggi:

1. Passa il mouse sul segmento nella zona di rilascio e fai clic sull’icona “i”.
1. Nel pannello informazioni visualizzato, fai clic su **[!UICONTROL Save]**.

   ![](assets/segment-info.png)

## Cosa sono i segmenti solo progetto?

I segmenti Solo progetto sono segmenti rapidi o segmenti di progetto ad hoc Workspace. Quando li modifichi o li apri nel generatore di segmenti, viene visualizzata la casella Solo progetto. Se si APPLICA un segmento rapido nel generatore ma non si seleziona la casella che lo rende disponibile, si tratta comunque di un segmento solo progetto, ma non può più essere aperto nel generatore di segmenti rapidi. Se si seleziona la casella e si SALVA, diventa un segmento dell’elenco dei componenti.
