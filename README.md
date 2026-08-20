import os
from weasyprint import HTML

# Create a Markdown formatted text for README.md
readme_content = """# 🍲 CraveBite - Modern Web Food Ordering Application

[![License: MIT](https://img.shields.io/badge/License-MIT-orange.svg)](https://opensource.org/licenses/MIT)
[![Stack](https://img.shields.io/badge/Tech--Stack-HTML5%20%7C%20CSS3%20%7C%20JS%20%7C%20SQLite-blue)](https://github.com)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

**CraveBite** is a fast, lightweight, and modern food ordering web application designed to bring a seamless food ordering experience directly to users' browsers. Built using pure vanilla web tech combined with an **in-browser SQLite database** powered by WebAssembly (`sql.js`), CraveBite stores users, addresses, cart items, order history, and menu items directly in browser storage without requiring an external backend server!

---

## 🌟 Key Features

- 🍕 **Rich Food Menu**: Browse through 50+ dishes across multiple categories (*Meals, Snacks, Beverages, Desserts, Starters*).
- 🔍 **Real-Time Search & Filtering**: Instant search across dish names and descriptions, plus diet toggles (e.g., *Veg Only*).
- 🛒 **Interactive Shopping Cart**: Dynamic cart overlay with live price breakdown (Subtotal, GST, Delivery Fees).
- 💳 **Checkout & Payment Integration**: Multi-channel payment UI supporting Credit/Debit Cards, UPI, Net Banking, and Cash on Delivery (COD).
- 📍 **Saved Addresses**: Manage multiple delivery addresses stored directly inside local SQLite storage.
- 📜 **Order Tracking & History**: View past orders, track status updates, and keep a persistent order log.
- 💾 **Client-side SQLite Database**: Uses `sql.js` (SQLite WASM) & `localStorage` persistence — full SQL relational database capabilities running inside your browser!
- 👤 **Authentication System**: Built-in User Registration and Login flow.

---

## 🏗️ Architecture & Technology Stack

| Component | Technology | Description |
| :--- | :--- | :--- |
| **Frontend Framework** | HTML5, CSS3, Vanilla JS | Clean UI with CSS grid/flex layout, standard DOM manipulation |
| **Database** | SQLite (`sql.js` WebAssembly) | Client-side relational database running completely inside browser JS |
| **Data Persistence** | `localStorage` + Base64 Export | SQLite DB binary is exported as Base64 string and restored seamlessly |
| **Icons & Fonts** | Boxicons, Google Fonts | *DM Sans* & *Playfair Display* typography paired with crisp UI icons |

---

## 📁 Repository Structure

```text
cravebite/
│
├── index.html         # Main application landing page, food menu, cart & modal workflows
├── login.html         # Login and registration authentication page
├── styles.css         # Complete styling, dark-theme palette, animations, layout
├── script.js         # Core application logic, cart management, event listeners, UI renders
├── db.js             # SQLite initialization via sql.js, schema creation, data seeding, persistence
├── dbHelper.js       # Asynchronous SQL query helper methods (Users, Orders, Cart, Addresses)
├── data.js           # Default seeded dataset containing menu items and categories
└── README.md          # Project documentation
