# 💳 Subscription Manager Cards for Home Assistant

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg)](https://github.com/hacs/default)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Interactive Lovelace dashboard cards designed for the [Home Assistant Subscription Manager Integration](https://github.com/JarydX/ha-subscriptionmanager).

This repository bundles two companion cards:
1. **Subscription Manager Card** (`custom:subscription-manager-card`): Interactive subscription list with sorting, filtering, budget tracking, and cashflow forecast.
2. **Subscription Report Card** (`custom:subscription-report-card`): Interactive SVG donut breakdown by categories and payment methods.

---

## ✨ Features

- 📊 **Expense Summary**: Total monthly and yearly projected costs, along with active subscription count.
- 🔄 **Live Sorting**: Toggle sort order by Due Date (payday), Cancellation Deadline, Cost, or Name.
- 🏷️ **Category Filtering**: Pre-filter or use interactive chips to filter by categories (streaming, software, fitness, etc.).
- 💳 **Speaking Payment Methods**: Clean display of payment methods (PayPal, Credit Card, SEPA Direct Debit, Apple Pay, Google Pay, Bank Transfer, Invoice).
- 💰 **Budget & Cashflow**: Monthly budget progress bar and remaining upcoming payments forecast for the current month.
- 🍩 **Donut Expense Report**: Visual breakdown of your expenses with hover insights and monthly/yearly toggles.
- 🌐 **Multi-Language Support**: Automatically adapts to your Home Assistant language (English, German, French, Spanish).
- 🖱️ **More-Info Dialog**: Clicking any subscription item opens its detailed Home Assistant entity modal.

---

## 📦 Installation via HACS (Frontend)

1. Open **HACS** in Home Assistant -> **Frontend** (or Dashboards).
2. Click the three dots in the top-right corner -> **Custom repositories**.
3. Add this repository:
   - **Repository**: `https://github.com/JarydX/ha-subscriptionmanager-card`
   - **Type**: `Lovelace` (or Dashboard)
4. Search for **Subscription Manager Card** and click **Download**.
5. HACS automatically registers the card bundle under Dashboards -> Resources.

---

## ⚙️ Configuration & Usage

Add cards via the visual dashboard card picker or in YAML:

### 1. Subscription Manager Card

```yaml
type: custom:subscription-manager-card
title: My Subscriptions
# Optional: Pre-filter specific categories
categories:
  - streaming
  - software
# Optional: Monthly budget limit
budget: 150
show_summary: true
show_sorting: true
show_categories: true
show_cashflow: true
```

#### Options:

| Parameter | Type | Default | Description |
|---|---|---|---|
| `title` | string | `'Subscriptions'` | Card title (localized by default) |
| `categories` | list | `[]` | Filter to specific categories (e.g. `['streaming', 'software']`) |
| `budget` | number | `null` | Monthly budget with progress bar |
| `show_summary` | boolean | `true` | Displays summary bar (monthly, yearly, active count) |
| `show_sorting` | boolean | `true` | Displays sort buttons (Due date, Notice deadline, Cost, Name) |
| `show_categories` | boolean | `true` | Displays interactive category filter chips |
| `show_cashflow` | boolean | `true` | Displays upcoming remaining payments for the current month |
| `entity` | string | `sensor.subscriptions_overview_summary` | Optional: Custom summary entity |

---

### 2. Subscription Report Card (Donut Chart)

```yaml
type: custom:subscription-report-card
title: Expense Distribution
default_period: month # 'month' or 'year'
default_group_by: category # 'category' or 'payment_method'
show_period_toggle: true
show_group_toggle: true
show_legend: true
```

#### Options:

| Parameter | Type | Default | Description |
|---|---|---|---|
| `title` | string | `'Expense Report'` | Card title (localized by default) |
| `default_period` | string | `'monthly'` | Initial period: `'monthly'` or `'yearly'` |
| `default_group_by` | string | `'category'` | Initial grouping: `'category'` or `'payment_method'` |
| `show_period_toggle` | boolean | `true` | Displays month/year toggle buttons |
| `show_group_toggle` | boolean | `true` | Displays category/payment method toggle buttons |
| `show_legend` | boolean | `true` | Displays legend below donut chart |

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
