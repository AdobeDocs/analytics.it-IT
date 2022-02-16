---
description: Tabella di ricerca per determinare il tipo di hit in base al valore page_event .
keywords: Feed di dati;pagina;evento;page_event;post_page_event
title: Ricerca eventi pagina
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 6%

---

# Ricerca eventi pagina

Tabella di ricerca per determinare il tipo di hit in base al valore page_event .

| Tipo di hit | Valore `page_event` | Valore `post_page_event` |
| --- | --- | --- |
| Visualizzazioni pagina | 0: Tutte le chiamate di visualizzazione della pagina e `trackState` chiamate dagli SDK di Mobile | Stesso valore di `page_event` |
| Tracciamento dei collegamenti | 10. Collegamenti personalizzati e `trackAction` chiamate negli SDK per dispositivi mobili<br>11. Collegamenti di download<br>12. Collegamenti di uscita | 100: Collegamenti personalizzati e `trackAction` chiamate negli SDK per dispositivi mobili<br>101 Collegamenti di download<br>102 Collegamenti di uscita |
| Video Milestone | 31. Media Start<br>32. Aggiornamenti multimediali (nessuna altra elaborazione variabile)<br>33. Aggiornamenti multimediali (con altre variabili) | 76. Media Start<br>77. Aggiornamenti multimediali (nessuna altra elaborazione variabile)<br>78. Aggiornamenti multimediali (con altre variabili) |
| Video Heartbeat | 50: Inizio flusso multimediale (non Primetime)<br>51. Streaming multimediale (non Primetime)<br>52. Sfruttamento flusso multimediale (non Primetime)<br>53. Il flusso multimediale mantiene vivo (non Primetime)<br>54. Media stream ad start (non Primetime)<br>55. Annunci multimediali vicini (non Primetime)<br>56. Estrazione di annunci di flusso multimediale (non Primetime)<br>60: Inizio flusso multimediale Primetime<br>61. Streaming multimediale Primetime<br>62. Scorrimento dei flussi multimediali di Primetime<br>63. Il flusso multimediale Primetime mantiene vivo<br>64. Primetime media stream ad start<br>65. Primetime media stream e close<br>66. Primetime media stream e scrubbing | Stesso valore di `page_event` |
| Sondaggio | 40: Qualsiasi chiamata generata dal sondaggio | 80: Qualsiasi chiamata generata dal sondaggio |
| Analytics for Target | 70: L’hit include i dati dell’attività di Target | Stesso valore di `page_event` |
