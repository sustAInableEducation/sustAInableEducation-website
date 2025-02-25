---
title: Fortschrittsbericht KW9
date: 25.02.2025
description: Detaillierter Bericht zu den Fortschritten in Frontend, Backend, KI-Story und KI-Quiz in den Kalenderwochen 6 bis 7. Behandelt neue Features, technische Implementierungen und konzeptionelle Entwicklungen zur Weiterführung des Projekts.
---

## Ausgangslage
Dieser Bericht umfasst die Fortschritte im Zeitraum vom 11.02.2025 bis 25.11.2024 in den Bereichen Frontend, Backend, KI-Story und KI-Quiz. Im Frontend wurden wichtige Funktionen für die Quizverwaltung implementiert und zahlreiche Fehler behoben, um die Benutzerfreundlichkeit zu verbessern. Im Backend wurden kleinere Fehler korrigiert und an der schriftlichen Dokumentation weitergearbeitet. Im Bereich KI-Story wurde das Prompting optimiert, um die generierten Story-Abschnitte präziser und kürzer zu gestalten. Das KI-Quiz wurde weiter verfeinert, insbesondere durch Verbesserungen in der Bildgenerierung, der Fehlerbehandlung und den verwendeten Prompts.  

## Fortschritte im Frontend 

- **Verbesserungen der Benutzeroberfläche** 
  - Der mobile Header wurde angepasst, um die Darstellung auf kleineren Bildschirmen zu optimieren.  
  - In der Quizübersicht wurde ein **Query-Parameter** hinzugefügt, mit dem sich ein spezifisches Quiz auswählen lässt.  
  - Ein **Button zum Starten eines Quiz** wurde in die Quizübersicht integriert.  
  - Die Quizübersicht zeigt nun **detaillierte Informationen** zu einem Quiz an, einschließlich der bisherigen Versuche.  
  - Implementierung neuer Seiten für die Anzeige und Verwaltung von Quizzen:  
    - Quizanzeige  
    - Quizübersicht  
    - Quizkonfiguration  
  - Accountinformationen werden jetzt auf der **Accountseite korrekt dargestellt**.  

- **Bugfixes und Optimierungen**  
  - **Prozentanzeige in Stories** wurde korrigiert, sodass der Fortschritt nun präzise dargestellt wird.  
  - **Fortschrittsbalken in der Storyübersicht** wurde an realistische Werte angepasst.  
  - Ein **Button zum Einklappen aller Storyteile** in der Storyübersicht wurde hinzugefügt.  
  - **Filterfunktionen** in der Storyübersicht wurden überarbeitet und funktionieren nun zuverlässig.  
  - **Korrekte Anzeige von Nutzerdaten** auf der Accountseite (/Account).  
  - **Sinnvolle Fehlermeldungen** bei der Registrierung und beim Login hinzugefügt, um den Nutzern genauere Hinweise zu geben.  
  - **Zeitübersicht in der Storykonfiguration** angepasst, um realistischere Werte anzuzeigen.  
  - Der **Benutzername wird nun korrekt im Header angezeigt**.  
  - Die **Größe des Vote-Elements** in der Spaceübersicht wurde korrigiert, sodass es einheitlich dargestellt wird.  

## Fortschritte im Backend

- **Bugfixes und Optimierungen**  
  - Fehler beim **Löschen von Quizzes** behoben.  
  - Beim **Auslesen der Quizzes** wird nun die jeweilige Quiz-ID korrekt mitgesendet.  

- **Dokumentation**  
  - Weiterarbeit am **schriftlichen Implementierungsteil** der Diplomarbeit.  

## Fortschritte bei der KI-Story

- **Dokumentation**  
  - Beginn des **schriftlichen Implementierungsteils** zur Beschreibung der KI-gestützten Storygenerierung.  

- **Optimierung des Promptings**  
  - Die **Länge der generierten Story-Abschnitte** wurde optimiert, um kürzere, präzisere Inhalte zu erstellen. Dies basiert auf Nutzerfeedback aus Tests am **GRG21**.

## Fortschritte beim KI-Quiz

- **Verbesserungen der Quizgenerierung**  
  - Erste Optimierungen für den **State-of-the-Art-Vergleich** wurden vorgenommen.  
  - Die **Bildgenerierung für Quiz-Inhalte** wurde weiter verbessert.  
  - **Prompts für die Quiz-Erstellung** wurden überarbeitet, um genauere und passendere Fragen zu erzeugen.  

- **Fehlerbehandlung**  
  - Implementierung einer **grundlegenden Fehlerbehandlung**, um die Stabilität der Quizgenerierung zu erhöhen. Einige Anpassungen sind noch in Arbeit.

## Fazit
In der letzten Woche konnten in allen Bereichen bedeutende Fortschritte erzielt werden. Die Verbesserungen im Frontend sorgen für eine deutlich optimierte Nutzererfahrung, insbesondere im Bereich Quizverwaltung. Im Backend wurden wichtige Fehler korrigiert und die Arbeit am schriftlichen Teil der Diplomarbeit fortgesetzt. Die KI-Story wurde durch gezielte Optimierungen des Promptings weiter verbessert, während das KI-Quiz durch überarbeitete Prompts, eine optimierte Bildgenerierung und eine verbesserte Fehlerbehandlung stabiler und leistungsfähiger geworden ist.

## Kommentar des Teams
Das Team ist mit den erzielten Fortschritten sehr zufrieden und motiviert, das Projekt weiterzuentwickeln. Besonders freuen wir uns darüber, dass wir das Projekt erfolgreich am **GRG21** testen konnten, wodurch wertvolles Feedback zur Optimierung der generierten Story-Abschnitte und zur Quiz-Erstellung gesammelt wurde. Mit den Verbesserungen in der Nutzererfahrung, der Fehlerbehandlung und der schriftlichen Dokumentation sind wir gut auf die nächsten Entwicklungsschritte vorbereitet und blicken gespannt auf die kommenden Herausforderungen.