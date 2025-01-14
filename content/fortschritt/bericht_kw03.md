---
title: Fortschrittsbericht KW3
date: 14.01.2025
description: Detaillierter Bericht zu den Fortschritten in Frontend, Backend, KI-Story und KI-Quiz in Kalenderwoche 2. Behandelt neue Features, technische Implementierungen und konzeptionelle Entwicklungen zur Weiterführung des Projekts.
---

## Ausgangslage

Dieser Bericht umfasst die Fortschritte im Zeitraum vom 08.01.2025 bis 14.01.2025 in den Bereichen Frontend, Backend, KI-Story und KI-Quiz. Im Frontend wurden wesentliche Seiten fertiggestellt, die das Nutzererlebnis optimieren. Im Backend wurden neue Endpunkte und Funktionalitäten hinzugefügt, die die Effizienz und Erweiterbarkeit des Systems verbessern. Im Bereich KI-Story wurden zentrale Features abgeschlossen und erste Arbeiten an zusätzlichen Funktionen begonnen. Im Bereich KI-Quiz wurde der Prototyp weiterentwickelt und konzeptionelle Arbeiten vertieft.

## Fortschritte im Frontend

- **Seite zur Konfiguration eines EcoSpaces**: Diese Seite wurde fertiggestellt und bietet Nutzern eine intuitive Möglichkeit, ihre EcoSpaces individuell zu gestalten.
- **Übersicht aller EcoSpaces eines Nutzers**: Eine neue Seite wurde entwickelt, die eine klare und übersichtliche Darstellung aller EcoSpaces eines Nutzers ermöglicht.
- **Storyansicht**: Die Storyansicht wurde finalisiert, wodurch Nutzer Geschichten einfacher lesen und interagieren können.
- **State-of-the-Art und Machbarkeit**: Die Analyse zu den modernsten Technologien und der Umsetzbarkeit wurde erfolgreich abgeschlossen.

## Fortschritte im Backend

- **Update der Passwortanforderungen**: Die Mindestlänge von Passwörtern wurde aktualisiert, um die Sicherheit zu erhöhen.
- **Docker-Integration**: Docker Compose und Dockerfile wurden hinzugefügt, um die Bereitstellung und Verwaltung des Systems zu erleichtern.
- **Neue Endpunkte**: Es wurden Endpunkte für E-Mail-Änderungen und Passwort-Änderungen implementiert.
- **Erweiterung des Story-Modells**: Das Story-Modell wurde um eine neue `TargetGroup`-Enum-Eigenschaft erweitert, und die `Prompt`-Eigenschaft wurde in `Topic` umbenannt.
- **Anpassungen im AI-Service**: Die Methode `RebuildChatMessages` generiert jetzt einen System-Prompt basierend auf der `TargetGroup`-Eigenschaft und verwendet die neue `Topic`-Eigenschaft.
- **Weitere Features**:
  - Intertitle zu StoryPart hinzugefügt.
  - Option zur Rückgabe von Titeln im IAIService integriert.
  - DeepInfra-Konfiguration in PascalCase umbenannt.
  - Story-Resultat hinzugefügt.
- **State-of-the-Art und Machbarkeit**: Abschluss der Analyse zur Umsetzbarkeit.

## Fortschritte bei der KI-Story

- **Feature /LF210/ Story generieren**: Dieses Feature wurde erfolgreich abgeschlossen.
- **Feature /LF215/ Resultat generieren**: Auch dieses Feature wurde fertiggestellt, wodurch alle Must-Have-Features des AI-Services implementiert sind.
- **Nice-To-Have-Feature Story-Bilder generieren**: Erste Arbeiten an der Generierung von Story-Bildern wurden begonnen.
- **Projektbericht**: Erstellung eines Berichts für den Jugend Innovativ Wettbewerb.
- **State-of-the-Art und Machbarkeit**: Analyse abgeschlossen.

## Fortschritte beim KI-Quiz

- **Prototyp-Verbesserungen**: Der Prototyp zur Quiz-Generierung wurde optisch und funktional überarbeitet.
- **Literaturrecherche**: Die Literaturrecherche wurde überarbeitet und erweitert.
- **State-of-the-Art und Machbarkeit**: Weiterführende Untersuchungen zur Machbarkeit wurden durchgeführt.

## Fazit

Die Fortschritte der letzten Woche zeigen deutliche Erfolge in allen Projektbereichen. Das Frontend wurde um zentrale Funktionen erweitert, die die Benutzerfreundlichkeit erheblich steigern. Im Backend wurden wichtige Verbesserungen und neue Endpunkte implementiert, die die Systemfunktionalität erweitern. Die KI-Story hat mit der Fertigstellung aller Must-Have-Features einen wichtigen Meilenstein erreicht, und die Arbeit an Nice-To-Have-Features wurde eingeleitet. Im Bereich KI-Quiz wurden der Prototyp und die konzeptionellen Grundlagen weiterentwickelt.

## Kommentar des Teams

Das Team ist motiviert, die erreichten Fortschritte weiter auszubauen und sich auf die kommenden Herausforderungen zu konzentrieren. Die nächsten Schritte umfassen die Verfeinerung bestehender Funktionen und die Einführung neuer Features, um das Projekt weiter voranzutreiben.