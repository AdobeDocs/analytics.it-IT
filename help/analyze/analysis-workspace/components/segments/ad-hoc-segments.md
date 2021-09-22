---
description: Utilizzare segmenti ad hoc in Analysis Workspace.
title: Segmenti ad hoc
feature: Workspace Basics
role: User, Admin
source-git-commit: 31507092e659fa08a50e00f91bd36411e354cb21
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 34%

---


# Segmenti ad hoc

Ecco un video sulla creazione di segmenti ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Puoi creare segmenti ad-hoc se desideri esplorare rapidamente in che modo un segmento potrebbe influenzare il progetto, senza passare al Generatore di segmenti. Considera questi segmenti come segmenti temporanei a livello di progetto. In genere non fanno parte della &quot;libreria&quot; del segmento, come i segmenti di componente nella barra a sinistra. Tuttavia, puoi salvarli, come illustrato di seguito.

Per un confronto tra le attività dei segmenti ad hoc e i segmenti a livello di componente a tutti gli effetti, visita [qui](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

1. Rilascia qualsiasi tipo di componente (dimensione, elemento dimensione, evento, metrica, segmento, modello di segmento, intervallo di date) nella zona di rilascio del segmento nella parte superiore di un pannello. I tipi di componente vengono automaticamente convertiti in segmenti.
Ecco un esempio di come creare un segmento per il dominio di riferimento Twitter:

   ![](assets/ad-hoc1.png)

   Il pannello applica automaticamente questo segmento e potrai vedere immediatamente i risultati.

1. Puoi aggiungere a un pannello un numero illimitato di componenti.
1. Se decidi di salvare questo segmento, consulta la sezione seguente.

Nota bene:

* Nella zona dei segmenti **non è possibile** rilasciare i tipi di componenti seguenti: metriche calcolate e dimensioni/metriche da cui non è possibile creare i segmenti.
* Per eventi e dimensioni intere, Analysis Workspace crea dei segmenti di hit di tipo “esiste”. Esempi: `Hit where eVar1 exists` o `Hit where event1 exists`.
* Se nella zona di rilascio dei segmenti viene rilasciato “Non specificato” o “Nessuno”, vengono automaticamente convertiti in un segmento di tipo “non esiste” in modo da essere trattati correttamente nella segmentazione.

>[!NOTE]
>
>I segmenti creati in questo modo sono interni al progetto.

## Salvare segmenti ad-hoc {#ad-hoc-save}

Puoi scegliere di salvare questi segmenti seguendo questi passaggi:

1. Passa il mouse sul segmento nella zona di rilascio e fai clic sull’icona “i”.
1. Nel pannello informazioni visualizzato, fai clic su **[!UICONTROL Save]**.

   ![](assets/segment-info.png)

