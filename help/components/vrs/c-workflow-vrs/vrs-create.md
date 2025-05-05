---
description: Prima di iniziare a creare suite di rapporti virtuali, tieni presente alcuni aspetti.
keywords: Suite di rapporti virtuali
title: Creare suite di rapporti
feature: VRS
exl-id: 5ff6ff1a-5b99-41cc-a3a7-928197ec9ef9
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 4%

---

# Creare suite di rapporti

Prima di iniziare a creare suite di rapporti virtuali, tieni presente alcuni aspetti.

* Gli utenti non amministratori non possono visualizzare il gestore delle suite di rapporti virtuali.
* Non è possibile condividere le suite di rapporti virtuali. La &quot;condivisione&quot; viene eseguita tramite gruppi/autorizzazioni.
* Nella gestione delle suite di rapporti virtuali, puoi visualizzare solo le tue suite di rapporti virtuali. È necessario fare clic su &quot;mostra tutto&quot; per visualizzare i dati di tutti gli altri.

1. Passa a **[!UICONTROL Components]** > **[!UICONTROL Virtual report suites]**.
1. Fai clic su **[!UICONTROL Add +]**.

   ![](assets/new_vrs.png)

## Definire le impostazioni

Nella scheda [!UICONTROL Settings], definire queste impostazioni e quindi fare clic su **[!UICONTROL Continue]**.

| Elemento | Descrizione |
| --- |--- |
| Nome | Il nome della suite di rapporti virtuale non viene ereditato dalla suite di rapporti principale e deve essere distinto. |
| Descrizione | Aggiungi una buona descrizione a beneficio degli utenti aziendali. |
| Tag | Puoi aggiungere tag per organizzare le suite di rapporti. |
| Origine | La suite di rapporti da cui questa suite di rapporti virtuale eredita le impostazioni seguenti. La maggior parte dei livelli di servizio e delle funzioni (ad esempio, impostazioni eVar, Regole di elaborazione, Classificazioni e così via) vengono ereditati. Per apportare modifiche a queste impostazioni ereditate su una suite di rapporti virtuale, devi modificare la suite di rapporti principale ( Amministratore > Suite di rapporti). |
| Fuso orario | La scelta del fuso orario è facoltativa. Se scegli un fuso orario, questo viene salvato insieme alla suite di rapporti virtuale. Se non ne scegli uno, viene utilizzato il fuso orario della suite di rapporti principale.  Quando si modifica una suite di rapporti virtuale, il fuso orario salvato con la suite di rapporti virtuale viene visualizzato nel selettore a discesa. Se la suite di rapporti virtuale è stata creata prima dell’aggiunta del supporto per il fuso orario, il fuso orario della suite di rapporti principale viene visualizzato nel selettore a discesa. |
| Segmenti | Puoi aggiungere un solo segmento o sovrapporre segmenti.   Nota: quando si impilano due segmenti, questi vengono uniti da un&#39;istruzione AND. Non può essere modificata in un&#39;istruzione OR. Quando tenti di eliminare o modificare un segmento attualmente utilizzato in una suite di rapporti virtuale, viene visualizzato un avviso. |

## Definire la definizione di visita

Nella scheda [!UICONTROL Visit Definition], definire queste impostazioni e quindi fare clic su **[!UICONTROL Continue]**.

![](assets/visit-definition.png)


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Regolare la definizione di una visita](https://video.tv.adobe.com/v/23545?quality=12&learn=on){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]

| Elemento | Descrizione |
| --- |--- |
| **Configura definizione visita** |  |
| Abilita elaborazione dei tempi di report | Utilizza l’elaborazione dei tempi di report per modificare la lunghezza di timeout predefinita per la visita. Queste impostazioni non sono distruttive e si applicano solo ad Analysis Workspace. [Ulteriori informazioni](/help/components/vrs/vrs-report-time-processing.md) |
| Timeout della visita | Definisce la quantità di inattività che un visitatore univoco deve avere prima che una nuova visita venga avviata automaticamente. Questo influenzerà la metrica Visite, il contenitore del segmento di visita e le eVar che scadono durante la visita. |
| Inizia nuova visita con evento | Avvia una nuova sessione quando uno qualsiasi degli eventi specificati si attiva indipendentemente dal timeout di una sessione. |
| **Impostazioni di visita app mobile** | Modifica la definizione delle visite per gli hit delle app mobili raccolti dagli SDK di Adobe per dispositivi mobili. Queste impostazioni non sono distruttive e si applicano solo ad Analysis Workspace. |
| Impedire che gli hit di background diano inizio a una nuova visita | Impedisce che gli hit di background diano inizio a una nuova visita e che aumentino le metriche relative a visite e visitatori univoci. |
| Avvia una nuova visita a ogni avvio dell’app | Avvia una nuova sessione quando si verifica l&#39;avvio di un&#39;app. [Ulteriori informazioni](/help/components/vrs/vrs-mobile-visit-processing.md) |

## Includere e rinominare i componenti

![](assets/components.png)

1. Nella scheda [!UICONTROL Components], seleziona la casella di controllo per applicare la cura in modo da includere, escludere e rinominare i componenti per questa suite di rapporti virtuale in Analysis Workspace.
Per ulteriori informazioni sulla cura delle suite di rapporti virtuali, consulta [Cura dei componenti delle suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-components.html?lang=it#virtual-report-suites).

1. Trascina i componenti (dimensioni, metriche, segmenti o intervalli di date) che vuoi includere nella suite di rapporti virtuali nella sezione [!UICONTROL Included Components].

1. Al termine, fare clic su **[!UICONTROL Save]**.

## Anteprima dati

Sul lato destro di ogni scheda, puoi visualizzare in anteprima gli hit totali, le visite totali e i visitatori totali in questa suite di rapporti virtuale rispetto alla suite di rapporti originale.

## Visualizza compatibilità prodotto

Alcune funzioni delle suite di rapporti virtuali non sono supportate da tutti i prodotti Adobe Analytics. L’elenco di compatibilità dei prodotti consente di vedere quali prodotti all’interno di Adobe Analytics sono supportati in base alle impostazioni correnti della suite di rapporti virtuale.
