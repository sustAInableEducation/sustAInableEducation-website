---
title: Fortschrittsbericht KW5
date: 28.01.2025
description: Detaillierter Bericht zu den Fortschritten in Frontend, Backend, KI-Story und KI-Quiz in den Kalenderwochen 4 bis 5. Behandelt neue Features, technische Implementierungen und konzeptionelle Entwicklungen zur Weiterführung des Projekts.
---

## Ausgangslage

Dieser Bericht umfasst die Fortschritte im Zeitraum vom 14.01.2024 bis 28.11.2024 in den Bereichen Frontend, Backend, KI-Story und KI-Quiz. Im Backend wurden neue Funktionen und Optimierungen durchgeführt, die die Datenverarbeitung und Bereitstellung der Anwendung erweitern und verbessern. Im Bereich KI-Story wurde die Bildgenerierung vollständig implementiert, ein bedeutender Wettbewerbsbericht eingereicht, und erste Arbeiten zur Verbesserung der Prompts eingeleitet. Im Bereich KI-Quiz wurde der Prototyp weiterentwickelt, eine Funktion zur Profilbildgenerierung implementiert und eine Analyse zu State-of-the-Art-Ansätzen begonnen.

## Fortschritte im Frontend

- **Voting-System in der Story**: Ein neues Voting-System wurde in die Storyansicht integriert, das es Nutzern ermöglicht, aktiv an der Bewertung einzelner Geschichtenabschnitte teilzunehmen.
- **WebSocket-Integration**: Der WebSocket wurde vollständig in die Storyansicht eingebunden, wodurch eine reibungslose Echtzeitkommunikation und Aktualisierung der Inhalte gewährleistet wird.
- **Bugfixes**: Zahlreiche Fehler in der Storyansicht wurden behoben, was die Stabilität und Benutzerfreundlichkeit deutlich verbessert hat.

## Fortschritte im Backend

- **Verbesserte Validierung**: Die Validierungsmechanismen wurden überarbeitet, um die Datenqualität zu erhöhen und Fehler zu minimieren.
- **Speicherung und Mitschicken von Story-Bildern im WebSocket**: Eine Funktion wurde implementiert, um Story-Bilder direkt in der Datenbank zu speichern und über WebSockets an die Nutzer zu übermitteln, wodurch die Darstellung von Story-Inhalten optimiert wurde.
- **Administrationsfunktionen**: Neue Funktionen für die Administration wurden hinzugefügt, die die Verwaltung der Anwendung vereinfachen und effizienter machen.
- **Docker Deployment mit Docker Compose**: Das System wurde erfolgreich auf Docker umgestellt, einschließlich der Einführung von Docker Compose. Dies erleichtert die Bereitstellung und Skalierbarkeit der Anwendung erheblich.

## Fortschritte bei der KI-Story

- **Vollständige Story-Bilder-Generierung**:
   Die Generierung von Story-Bildern wurde abgeschlossen. Die Bilder werden pro Abschnitt oder Entscheidungspunkt einer Geschichte auf Basis der vorherigen Erzählung erstellt. Für die Bildgenerierung wird das Modell *black-forest-labs/FLUX-1-dev* verwendet. Da dieses Modell nicht direkt aus der Geschichte Bilder generieren kann, werden die Prompts von *Llama 3.3* erstellt. Das Modell erzeugt auf Grundlage dieser spezifischen Prompts Bilder, die die Erzählung visuell untermalen.
   ![Beispiel-Story-Bild](/img/kw05/story-bild.jpeg) 
- **Einreichung des Jugend Innovativ Wettbewerbsberichts**:
   Der Projektbericht für den Jugend Innovativ Wettbewerb wurde erfolgreich fertiggestellt und eingereicht. Die Bekanntgabe, ob das Projekt ins Finale einzieht, erfolgt im März 2025.
- **Nächste Aufgaben**:
  - Optimierung der Prompts zur Verbesserung der Geschichtenqualität.
  - Beginn des Schreibens des Implementierungsteils der Diplomarbeit, basierend auf den Fortschritten in der Bild- und Story-Generierung.

## Fortschritte beim KI-Quiz

- **Quiz-Generierung**:
   Die Funktion zur Generierung von Quizfragen wurde erfolgreich getestet und in den Hauptzweig des Projekts integriert.
- **Profilbildgenerierung**:
   Die Implementierung der Funktion zur KI-gestützten Erstellung von Profilbildern wurde abgeschlossen. Dies ermöglicht Nutzern, individuelle und anonymisierte Avatare zu erstellen.
- **State-of-the-Art-Verbesserungen**:
   Die Arbeit an einer Verbesserung der bestehenden Ansätze im Bereich der Quiz-Generierung hat begonnen. Dabei liegt der Fokus auf der Integration moderner KI-Technologien und der Optimierung der bestehenden Lösung.

## Fazit

Die Fortschritte der letzten Woche verdeutlichen signifikante Entwicklungen in allen Bereichen. Im Backend wurden durch die Einführung neuer Funktionen und das Docker Deployment wichtige technische Meilensteine erreicht. Die vollständige Implementierung der Story-Bilder-Generierung und die Einreichung des Projektberichts für den Jugend Innovativ Wettbewerb markieren zentrale Erfolge im Bereich KI-Story. Auch das KI-Quiz konnte mit der Integration der Profilbildgenerierung und der Weiterentwicklung des Prototyps wichtige Fortschritte verzeichnen.

## Kommentar des Teams

Das Team zeigt sich hochmotiviert und gut aufgestellt für die anstehenden Aufgaben. Mit der kontinuierlichen Weiterentwicklung der Prototypen und der Optimierung der bestehenden Funktionen sind die nächsten Meilensteine greifbar. Besondere Aufmerksamkeit wird in den kommenden Wochen auf die Verbesserung der KI-generierten Inhalte und die weitere Systemstabilität gelegt. Besonders freuen wir uns darauf, das Projekt in dieser Woche bei der Veranstaltung *"Spirit-of-HIT Days"* zu präsentieren und die bisherigen Ergebnisse einem breiteren Publikum vorzustellen.
