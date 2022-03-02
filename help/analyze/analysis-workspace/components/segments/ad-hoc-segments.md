---
description: Usare i segmenti ad hoc in Analysis Workspace.
title: Segmenti ad hoc
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: f50e3d9a1d3c1705c55a14af0e42a0da3ac00955
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 57%

---

# Segmenti di progetto ad hoc

I segmenti di progetto ad hoc ti consentono di trascinare e rilasciare qualsiasi componente direttamente nella zona di rilascio del pannello per creare un segmento. Il segmento diventa un [segmento a livello di progetto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?#what-are-project-only-segments%3F) locale al progetto corrente.

Ecco un video sulla creazione di segmenti di progetto ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

1. Puoi rilasciare qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, segmento, modello di segmento, intervallo di date) nella zona di rilascio dei segmenti, nella parte superiore di un pannello. I tipi di componente vengono automaticamente convertiti in segmenti ad hoc o [Segmenti rapidi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html) se compatibile.
Ecco un esempio di come creare un segmento per il dominio di riferimento Twitter:

   ![](assets/ad-hoc1.png)

   Il pannello applica automaticamente questo segmento e puoi vedere immediatamente i risultati.

1. Puoi aggiungere un numero illimitato di segmenti a un pannello.
1. Se decidi di salvare questo segmento, consulta la sezione seguente.

Nota bene:

* Nella zona dei segmenti **non è possibile** rilasciare i tipi di componenti seguenti: metriche calcolate e dimensioni/metriche da cui non è possibile creare i segmenti.
* Per eventi e dimensioni intere, Analysis Workspace crea dei segmenti di hit di tipo “esiste”. Esempi: `Hit where eVar1 exists` o `Hit where event1 exists`.
* Se nella zona di rilascio dei segmenti viene rilasciato “Non specificato” o “Nessuno”, vengono automaticamente convertiti in un segmento di tipo “non esiste” in modo da essere trattati correttamente nella segmentazione.

Per un confronto dei diversi segmenti che puoi creare e applicare all’interno di un progetto, vai [qui](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

## Salvare segmenti ad-hoc {#ad-hoc-save}

I segmenti ad hoc possono essere resi disponibili ad altri progetti salvandoli.

1. Passa il mouse sul segmento nella zona di rilascio e fai clic sull’icona “i”.
1. Fai clic sulla matita di modifica per passare al Generatore di segmenti.
1. Controlla **[!UICONTROL Make available to all projects and add to your component list]**.
1. Fai clic su **[!UICONTROL SAVE]**.

Una volta salvato, il segmento è disponibile nell’elenco dei componenti della barra a sinistra e può essere condiviso con altri utenti dal Gestore segmenti.
