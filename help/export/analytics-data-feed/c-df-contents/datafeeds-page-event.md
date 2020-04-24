---
description: Tabella di ricerca per determinare il tipo di hit in base al valore page_event.
keywords: Data Feed;page;event;page_event;post_page_event
title: Ricerca eventi pagina
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ricerca eventi pagina

Tabella di ricerca per determinare il tipo di hit in base al valore page_event.

| Tipo di hit | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| Visualizzazioni pagina | 0: Tutte le chiamate e `trackState` le chiamate della visualizzazione pagina dall’SDK di Mobile | Stesso valore di `post_page_event` |
| Tracciamento dei collegamenti | 10: Collegamenti e `trackAction` chiamate personalizzati in Mobile SDK&#39;s<br>11: Collegamenti<br>di download 12: Collegamenti di uscita | 100: Collegamenti e `trackAction` chiamate personalizzati in Mobile SDK&#39;s<br>101: Collegamenti<br>di download 102: Collegamenti di uscita |
| Video Milestone | 31. Media start<br>32: Aggiornamenti multimediali (nessuna altra elaborazione variabile)<br>33: Aggiornamenti dei supporti (con altre variabili) | 76. Media start<br>77: Aggiornamenti multimediali (nessuna altra elaborazione variabile)<br>78: Aggiornamenti dei supporti (con altre variabili) |
| Video Heartbeat | 50: Inizio flusso multimediale (non Primetime)<br>51: Stretta del flusso multimediale (non Primetime)<br>52: Scorrimento dei flussi multimediali (non Primetime)<br>53: Il flusso multimediale mantiene vivo (non Primetime)<br>54: Inizio annuncio flusso multimediale (non Primetime)<br>55: Annuncio multimediale vicino (non Primetime)<br>56: Download di annunci multimediali (non Primetime)<br>60: Inizio<br>61 flusso multimediale Primetime: Primetime media stream close<br>62: Scorrimento<br>63 del flusso multimediale Primetime: Il flusso multimediale Primetime mantiene vivo<br>64: Primetime media stream ad start<br>65: Primetime media stream e close<br>66: Primetime media stream ad scorrimento | Stesso valore di `post_page_event` |
| Sondaggio | 40: Qualsiasi chiamata generata da Survey | 80: Qualsiasi chiamata generata da Survey |
| Analisi per Target | 70: Hit include i dati dell&#39;attività di Target | Stesso valore di `post_page_event` |
