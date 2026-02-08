# GitHub Token Setup für CSV-Speicherung

## Problem
GitHub blockiert das Pushen von Tokens im Code aus Sicherheitsgründen. Der Token muss daher manuell nach dem Klonen hinzugefügt werden.

## Lösung

### Option 1: Token lokal hinzufügen (für lokale Entwicklung)
1. Öffne `index.html`
2. Suche nach `const GITHUB_CONFIG = {`
3. Füge den Token in das `token` Feld ein:
   ```javascript
   token: 'DEIN_TOKEN_HIER'
   ```
   (Den Token erhalten Sie aus den GitHub Developer Settings)

### Option 2: GitHub Actions mit Secret (empfohlen für GitHub Pages)
Da GitHub Pages keine serverseitige Logik unterstützt und Tokens nicht im Code sein sollten, ist die beste Lösung eine GitHub Actions Workflow, der den Token als Secret verwendet.

**Vorteile:**
- Token ist sicher als GitHub Secret gespeichert
- Funktioniert auf GitHub Pages
- Keine manuelle Konfiguration nötig

**Nachteile:**
- Erfordert eine GitHub Actions Workflow-Konfiguration

Falls Sie diese Lösung bevorzugen, kann ich eine GitHub Actions Workflow erstellen, die Registrierungen über Issues oder einen anderen Mechanismus verarbeitet.

## Aktueller Status
Die CSV-Speicherung ist implementiert, aber der Token muss manuell hinzugefügt werden, damit sie funktioniert.
