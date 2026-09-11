# 💳 Subscription Manager Card for Home Assistant

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg)](https://github.com/hacs/default)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Interaktives Lovelace-Dashboard-Widget für die [Home Assistant Subscription Manager Integration](https://github.com/JarydX/ha-subscriptionmanager).

## ✨ Features
- 📊 **Kostenübersicht**: Gesamtkosten pro Monat und Jahr sowie Anzahl aktiver Verträge.
- 🎯 **Kategorie-Filter & Budget**: Pre-Filterung nach Kategorien (z. B. nur Streaming), interaktive Filter-Chips und monatliche Budget-Leiste.
- 🍩 **Donut-Diagramm Report**: Zweite Karte `custom:subscription-report-card` für grafische Auswertung der Ausgaben nach Kategorie und Zahlungsmethode.
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
5. HACS registriert die Datei automatisch unter Dashboard -> Ressourcen. In einem Bundle sind automatisch **beide** Karten enthalten!

## ⚙️ Verwendung

### 1. Übersichtskarte: `custom:subscription-manager-card`
Füge die Karte über den visuellen Editor oder per YAML zu deinem Dashboard hinzu:

```yaml
type: custom:subscription-manager-card
title: Meine Abonnements
# Optional: Nur bestimmte Kategorien vorab filtern
categories:
  - streaming
  - software
# Optional: Monatliches Budget in Euro für Fortschrittsbalken
budget: 100
# Zusätzliche Optionen
show_summary: true
show_sorting: true
show_categories: true
show_cashflow: true
```

#### Konfigurations-Optionen Übersichtskarte:
| Option | Typ | Standard | Beschreibung |
|---|---|---|---|
| `title` | string | `'Abonnements'` | Kartentitel |
| `categories` | list | `[]` | Feste Vorauswahl an Kategorien (z. B. `['streaming', 'gaming']`) |
| `budget` | number | `null` | Monatliches Budgetlimit in Euro zur Fortschrittsanzeige |
| `show_summary` | boolean | `true` | Zeigt Monats-/Jahresausgaben oben |
| `show_sorting` | boolean | `true` | Zeigt Sortier-Buttons |
| `show_categories` | boolean | `true` | Zeigt interaktive Filter-Chips für Kategorien |
| `show_cashflow` | boolean | `true` | Zeigt noch anstehende Ausgaben im laufenden Monat |

---

### 2. Donut Report Karte: `custom:subscription-report-card`
Grafische Verteilung der Ausgaben auf Basis eines interaktiven SVG-Donut-Diagramms:

```yaml
type: custom:subscription-report-card
title: Ausgaben-Verteilung
default_period: month # 'month' oder 'year'
default_group_by: category # 'category' oder 'payment_method'
show_period_toggle: true
show_group_toggle: true
show_legend: true
```

#### Konfigurations-Optionen Report Karte:
| Option | Typ | Standard | Beschreibung |
|---|---|---|---|
| `title` | string | `'Ausgaben-Report'` | Kartentitel |
| `default_period` | string | `'month'` | Standard-Ansicht: `'month'` oder `'year'` |
| `default_group_by` | string | `'category'` | Gruppierung nach `'category'` oder `'payment_method'` |
| `categories` | list | `[]` | Optional: Diagramm auf bestimmte Kategorien einschränken |
| `show_period_toggle` | boolean | `true` | Umschalter Monat / Jahr anzeigen |
| `show_group_toggle` | boolean | `true` | Umschalter Kategorie / Zahlung anzeigen |
| `show_legend` | boolean | `true` | Detaillierte Legende mit Beträgen und % unter dem Donut anzeigen |
