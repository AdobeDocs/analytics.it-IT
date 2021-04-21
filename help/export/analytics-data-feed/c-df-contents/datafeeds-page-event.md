---
description: Tabella di ricerca per determinare il tipo di hit in base al valore page_event .
keywords: Feed di dati;pagina;evento;page_event;post_page_event
title: Ricerca eventi pagina
feature: Nozioni di base su Reports & Analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
translation-type: tm+mt
source-git-commit: cddf2a76ca36914f133379959b7cbb5246bdd695
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 6%

---

# Ricerca eventi pagina

Tabella di ricerca per determinare il tipo di hit in base al valore page_event .

| Tipo di hit | Valore `page_event` | Valore `post_page_event` |
| --- | --- | --- |
| Visualizzazioni pagina | 0: Tutte le chiamate di visualizzazione pagina e le chiamate `trackState` dagli SDK per dispositivi mobili | Stesso valore di `post_page_event` |
| Tracciamento dei collegamenti | 10. Collegamenti personalizzati e chiamate `trackAction` nell&#39;SDK di Mobile<br>11: Download link<br>12: Collegamenti di uscita | 100: Collegamenti personalizzati e chiamate `trackAction` nell&#39;SDK di Mobile<br>101: Download link<br>102: Collegamenti di uscita |
| Video Milestone | 31. Media start<br>32: Aggiornamenti multimediali (nessuna altra elaborazione variabile)<br>33: Aggiornamenti multimediali (con altre variabili) | 76. Media start<br>77: Aggiornamenti multimediali (nessuna altra elaborazione variabile)<br>78: Aggiornamenti multimediali (con altre variabili) |
| Video Heartbeat | 50: Inizio flusso multimediale (non Primetime)<br>51: Streaming multimediale (non Primetime)<br>52: Scorrimento dei flussi multimediali (non Primetime)<br>53: Il flusso multimediale mantiene vivo (non Primetime)<br>54: Media stream ad start (non-Primetime)<br>55: Annunci multimediali vicini (non Primetime)<br>56: Estrazione annunci di flusso multimediale (non Primetime)<br>60: Avvio flusso multimediale Primetime<br>61: Stretta flusso multimediale Primetime<br>62: Scorrimento dei flussi multimediali di Primetime<br>63: Il flusso multimediale Primetime mantiene vivo<br>64: Primetime media stream ad start<br>65: Annuncio multimediale Primetime chiusura<br>66: Primetime media stream e scrubbing | Stesso valore di `post_page_event` |
| Sondaggio | 40: Qualsiasi chiamata generata dal sondaggio | 80: Qualsiasi chiamata generata dal sondaggio |
| Analytics for Target | 70: L’hit include i dati dell’attività di Target | Stesso valore di `post_page_event` |
