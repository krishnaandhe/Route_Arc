<p align="center">
<img src="/docs/assets/logo.png" width="90">
</p>
<h1 align="center">Route Arc</h1>
<p align="center"><h2><em>A self-hosted **fleet management & trip booking system for organizations** — book rides, assign drivers, map routes, and rate journeys, all from a clean role-aware dashboard.</em></h2></p>

<p align="center"><img src="/docs/screenshots/banner.png" alt="Route_Arc png" /></p>
<p align="center"> <<------------x------------>> </p>
<p align="center">
  <img src="https://api.iconify.design/devicon:php.svg" alt="php" width="64" height="64" />
  <img src="https://api.iconify.design/devicon:mariadb-wordmark.svg" alt="mariadb-wordmark" width="64" height="64" />
  <img src="https://api.iconify.design/logos:leaflet.svg" alt="leaflet" width="64" height="64" />
  <img src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/i/7195e121-eded-45cf-9aab-909deebd81b2/d9ur2lg-28410b47-58fd-4a48-9b67-49c0f56c68ce.png" alt="Licence-MIT" width="64" height="64" />
  <img src="https://api.iconify.design/catppuccin:contributing.svg" alt="contributing" width="64" height="64" />
</p>


## 📖 Overview

**Route Arc** is a lightweight, self-hosted trip-booking and fleet-management platform built with **PHP 8 + MariaDB**. It gives every user tier — employees, approvers, fleet managers, drivers, and admins — a purpose-built experience, from booking a ride to assigning a driver, mapping the route live, and rating the journey both ways.

Designed to run anywhere (IIS, Apache), Route Arc ships with granular **role-based access control**, live **route mapping**, a **two-way rating system**, and persistent **in-app notifications**.

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
