# <p align="left">
  docs/assets/logo.png
</p> Route Arc

> A self-hosted **fleet management & trip booking system for organizations** — book rides, assign drivers, map routes, and rate journeys, all from a clean role-aware dashboard.

<p align="center">
  docs/screenshots/banner.png
</p>

<p align="center">
  <a href="#">BB4?logo=php&logoColor=white" alt="PHP 8.2"></a>
  <a href="#">https://img.shields.io/badge/MariaDB-11-003545?logo=mariadb&logoColor=white</a>
  <a href="#">?logo=leaflet&logoColor=white" alt="Leaflet + OSM"></a>
  <a href="#">-MIT-blue.svg" alt="License: MIT"></a>
  <a href="#">come-brightgreen.svg" alt="PRs Welcome"></a>
</p>

---

## 📖 Overview

**Route Arc** is a lightweight, self-hosted trip-booking and fleet-management platform built with **PHP 8 + MariaDB**. It gives every user tier — employees, approvers, fleet managers, drivers, and admins — a purpose-built experience, from booking a ride to assigning a driver, mapping the route live, and rating the journey both ways.

Designed to run anywhere (IIS, Apache, or Docker), Route Arc ships with granular **role-based access control**, live **route mapping**, a **two-way rating system**, and persistent **in-app notifications**.

---

## ✨ Features

### 🔐 Role-Based Access Control (RBAC)
- Granular, JSON-driven permissions map every role to allowed pages and a custom landing page.
- Five tiers: **Admin, Fleet Manager, HOD/Approver, Employee, Driver** — each sees only what they should.
- Secure by default: new pages deny access unless explicitly granted.

### 🧑‍💼 Employee Panel
- **Smart Pre-fill & Role-Aware Booking** — auto-fills user context and adapts booking options per role.
- **Book-for-Others** — approvers, HODs, and fleet managers can raise trips on behalf of their department.
- **Trip History** — searchable, filterable list of past trips with quick status filters.

### ✅ Approval Workflow
- HODs and approvers review, approve, or reject trip requests in a clean queue.
- Department-scoped visibility keeps each approver focused on their own team.
- Every action is audit-logged, email-queued, and pushed as an in-app notification.

### 🚕 Driver Panel (Mobile-First)
- Compact **440px mobile-first** layout for on-the-road use.
- **One Trip at a Time** rule — enforced on both server and UI to prevent double-booking.
- **Trip Lifecycle** states (Pending → Accepted → Ongoing → Completed) surface only the actions that make sense.
- **Admin Preview** — fleet managers/admins can inspect any driver's view via `?driver_id=X`.
- **Schema-safe** — auto-detects optional DB columns and degrades gracefully.

### 🗺️ Live Route Mapping
- **A → B pins** for pickup and destination on a **Leaflet + OpenStreetMap** view.
- Dashed route line with a **Haversine distance** estimate.
- **Navigate** button deep-links straight into Google Maps driving directions.
- Contextual display — the map appears in Accepted, Ongoing, and Active states.

### ⭐ Two-Way Rating System
- **Drivers rate passengers** (thumbs-up) and **passengers rate drivers** (5-star).
- Dual-rating card shows both scores side-by-side with feedback notes.
- Ratings appear only on completed, not-yet-rated, non-no-show trips.

### 🔔 Notifications
- Bell dropdown with three sources: new assignments, trips starting soon, and ratings received.
- **Single dismiss, clear-all, and swipe-to-dismiss** all persist across reloads (session-backed).
- Live badge counts sync across the bell, header pill, and bottom-nav.

### 🛠️ Admin Console
- Manage users, vehicles, drivers, and trips from a unified dashboard.
- **Dynamic app settings** — website title, logo, footer text, and dashboard notices, all config-driven.
- **Maintenance mode** gate locks out non-admins during scheduled downtime.

### 🎨 UI / UX
- **Dark mode** toggle across every panel.
- Shared, reusable **trip-details modal** used consistently across Employee, Driver, and Admin views.
- Clean, responsive design with a consistent header/footer shell.

### 📚 Built-in Help Center
- Discord-style, tiered help center with role-specific guides (Admin, Users, Fleet Manager, Driver).
- Interactive flow diagrams and searchable feature documentation for smooth onboarding.

---

## 🧱 Tech Stack

| Layer | Technology |
|-------|------------|
| **Backend** | PHP 8.2 |
| **Database** | MariaDB 11 (MySQL-compatible) |
| **Front-end** | HTML5, CSS3, Vanilla JS |
| **Maps** | Leaflet.js + OpenStreetMap + Nominatim |
| **Icons** | Tabler Icons |
| **Server** | IIS / Apache / Nginx (or Docker) |

---

## 🚀 Getting Started

### Prerequisites
- PHP 8.0+
- MariaDB 10.5+ (or MySQL 8+)
- A web server (IIS, Apache, or Nginx) — or Docker

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/Route_Arc.git
cd Route_Arc

# 2. Copy the sample config and fill in your details
cp config.sample.php config.php

# 3. Import the database schema
mysql -u root -p routearc < setup.sql
```

Then point your web server's document root to the `public/` folder and open the app in your browser.

### 🐳 Run with Docker (one command)

```bash
docker compose up -d
```
The app will be live at **http://localhost:8080**, with the database auto-built from `setup.sql`.

---

## ⚙️ Configuration

All environment-specific settings live in `config.php` (ignored by Git). Use `config.sample.php` as your template:

```php
<?php
return [
    'db_host' => 'localhost',
    'db_name' => 'routearc',
    'db_user' => 'your_user',
    'db_pass' => 'your_password',
    'app_name' => 'Route Arc',
];
```

> ⚠️ **Never commit real credentials.** Keep `config.php` out of version control and share only `config.sample.php`.

---

## 📸 Screenshots

| Dashboard | Route Map | Driver Panel |
|-----------|-----------|--------------|
| docs/screenshots/dashboard.png | docs/screenshots/map.png | docs/screenshots/driver.png |

---

## 🗂️ Project Structure

```
Route_Arc/
├── public/          # Entry point + app pages (index.php, panels)
├── includes/        # bootstrap.php, partials, handlers, services
├── assets/          # CSS, JS, images, Leaflet integration
├── docs/            # Help center, flow diagrams, screenshots
├── setup.sql        # Schema-only database dump
├── config.sample.php
├── docker-compose.yml
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🗺️ Roadmap

- [ ] REST API for third-party integrations
- [ ] Multi-language (i18n) support
- [ ] Analytics & reporting dashboard

---

## 🤝 Contributing

Contributions are welcome! Please fork the repo, create a feature branch, and open a pull request. See `CONTRIBUTING.md` for guidelines.

---

## 📝 About

Route Arc is the public release of an internal fleet-management platform, rebuilt as a clean, open, self-hostable app.

---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for details.

---

<p align="center">Made with ❤️ for smarter fleet management.</p>