# 💳 Subscription Manager Card for Home Assistant

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg)](https://github.com/hacs/default)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Interaktives Lovelace-Dashboard-Widget für die [Home Assistant Subscription Manager Integration](https://github.com/JarydX/ha-subscriptionmanager).

## ✨ Features
- 📊 **Kostenübersicht**: Gesamtkosten pro Monat und Jahr sowie Anzahl aktiver Verträge.
- 🔄 **Live-Sortierung**: Umschalten nach Fälligkeit (Zahltag), Kündigungsfrist, Kosten oder Name.
- 🎨 **Status-Badges**: Visuelle Warnungen vor Fristablauf (Grün, Gelb, Rot) und Anzeige der Zahlungsmethode.
- 🖱️ **Direktzugriff**: Klick auf ein Abo öffnet das More-Info-Modal in Home Assistant.

## 📦 Installation via HACS (Frontend)
1. Öffne **HACS** in Home Assistant -> **Frontend**.
2. Klicke oben rechts auf das Dreipunkt-Menü -> **Benutzerdefinierte Repositories**.
3. Trage ein:
   - **Repository**: `https://github.com/JarydX/ha-subscriptionmanager-card`
   - **Typ**: `Lovelace` (oder Dashboard)
4. Suche nach **Subscription Manager Card** und klicke auf **Herunterladen**.
5. HACS registriert die Karte automatisch unter Dashboard -> Ressourcen.

## ⚙️ Verwendung
Füge die Karte einfach über den visuellen Editor oder per YAML zu deinem Dashboard hinzu:

```yaml
type: custom:subscription-manager-card
title: Meine Abonnements
show_summary: true
show_sorting: true
```
